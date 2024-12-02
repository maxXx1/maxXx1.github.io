---
title: "Outline v Dockeru s ověřením Synology SSO"
date: "2024-12-02"
tags: 
  - "Synology"
  - "Selfhost"
  - "Homelab"
category: "Docker"
image: 
  path: "img/2024-12-02-outline-synology-sso/outline.jpg"
  alt: "Zdroj: Blackvoid"
---

Instalace Outline knowlge base (self-hosted) na Synology DSM 7.2 s použitím lokálního Synology SSO serveru. Jedná se o náhradu přihlášení přes Slack, která je jediná dostupná u self-hosted varianty.

# TO-DO

- [x] Outline v Dockeru (pomocí nativního Container manageru)
- [x] Přístup k datovým a databázovým souborům přímo z File Station
- [x] Přístup z internetu skrze DDNS
- [x] Náhrada Slack API za lokální Synology SSO server
- [ ] Outline a SSO na vlastní doméně
- [ ] Náhrada lokálních příloh, napojení na Synology C2 storage

# Konfigurace Synology SSO

- Nainstaluj balíček Synology SSO (Nikoliv “Synology OAuth Service")

![package](/img/2024-12-02-outline-synology-sso/package.png)
    
- Otevři balíček "Server SSO" a v Obecných nastavní nastav URL serveru a v Nastavení příhlášení Přizpůsobenou doménu.

![server_sso](/img/2024-12-02-outline-synology-sso/server_sso.png)
    
- V záložce služba povolit Server OIDC, zkopírum Well-known URL a otevři ji v nové záložce
    
    ```js
    {
        "authorization_endpoint": "https://sso.xxx.dscloud.me/webman/sso/SSOOauth.cgi",
        "claims_supported": [
            "aud",
            "email",
            "exp",
            "groups",
            "iat",
            "iss",
            "sub",
            "username"
        ],
        "code_challenge_methods_supported": [
            "S256",
            "plain"
        ],
        "grant_types_supported": [
            "authorization_code",
            "implicit"
        ],
        "id_token_signing_alg_values_supported": [
            "RS256"
        ],
        "issuer": "https://sso.xxx.dscloud.me/webman/sso",
        "jwks_uri": "https://sso.xxx.dscloud.me/webman/sso/openid-jwks.json",
        "response_types_supported": [
            "code",
            "code id_token",
            "id_token",
            "id_token token"
        ],
        "scopes_supported": [
            "email",
            "groups",
            "openid"
        ],
        "subject_types_supported": [
            "public"
        ],
        "token_endpoint": "https://sso.xxx.dscloud.me/webman/sso/SSOAccessToken.cgi",
        "token_endpoint_auth_methods_supported": [
            "client_secret_basic",
            "client_secret_post"
        ],
        "userinfo_endpoint": "https://sso.xxx.dscloud.me/webman/sso/SSOUserInfo.cgi"
    }
    ```
    {: file='.../webman/sso/.well-known/openid-configuration'}
    
- Zkopíruj endpointy do odpovídajících parametrů v Outline configu `.env` nebo přímo do `docker-compose.yaml`
    
    - `authorization_endpoint` → `OIDC_AUTH_URI`
        
    - `token_endpoint` → `OIDC_TOKEN_URI`
        
    - `userinfo_endpoint` → `OIDC_USERINFO_URI`
        
- V Server SSO vyber z levého bočního menu Aplikace a přidej novou apliakaci
    
- Vyplň jméno aplikace a její URL adresu (lze později změnit)
    
    - Název aplikace: třeba “Outline“ (je to jen pro přehlednost)
        
    - Přesměrovat URI: `https://docs.tvojedoména.xx/auth/oidc.callback`  
        Jedná se o hlavní doménu Outline apliace s `/auth/oidc.callback` na konci.  
        Pokud používáš reverzní proxy, tak použij veřejnou URL
        
- Otevři tuto nově vytvořenou “Outline” aplikaci

![sso-app](/img/2024-12-02-outline-synology-sso/sso_app.png)
    
- Zkopíruj ID a Tajný klíč apliace do tvé Outline konfigurace `.env` nebo `docker-compose.yaml`
    
    - ID aplikace → `OIDC_CLIENT_ID`
        
    - Tajný klíč aplikace → `OIDC_CLIENT_SECRET`
        
- Změň nebo přidej hodnotu
    
    - `OIDC_USERNAME_CLAIM=username` (default je `preferred_username`, která není SSO serverem podporovaná)
- Je nutné se ujistit, že všechny adresy jsou takové, jaké se zobrazují v prohlížeči, zejména URI přesměrování. Pokud chcete více adres (třeba HTTP i HTTPS), tak je můžete následně přidat.
    
- A to by mělo být ohledně SSO vše!
    

# Instalace Outline (Docker)

1.  Skrze File Station ve složce `docker` vytvoř složku `outline` a v ní další 2 pod-složky
    
    1.  `postgres-data` (Databáze)
        
    2.  `storage-data` (Přílohy)
        
2.  U složky `storage-data`:
    
    1.  Vlastnosti - Oprávnění - Pokročilé funkce - “Změnit zděděná oprávnění na výslovná“
        
    2.  Následně uprav uživatele “Everyone“ a přijdej mu oprávnění k zápisu
        
    3.  Zaklikni použít pro tuto složku i podsložky a dej uložit
        
3.  Do složky `outline` nahraj svůj nakonfigurovaný `docker-compose.yaml`
    
4.  V balíčku Container manager vytvoř projekt:
    
    1.  Název projektu `outline` (musí být malým písmem)
        
    2.  Cesta: `docker` - `outline`
        
    3.  Použit existující docker-compose.yaml
        
    4.  Pokud je zakliklý Webový portál, tak vypnout
        
5.  Jedná se o 3 kontejnery (app, redis, postgres), celé to startuje v závislosti na výkonu cca 5 minut
    

## Konfigurace

Hodnoty `SECRET_KEY` a `UTILS_SECRET` lze vygenrovat v terminálu pomocí příkazu

```bash
openssl rand -hex 32
```

> Já jsem nepoužil konfigurační `.env`, ale všechno na pevno definoval v `docker-compose.yaml`
{: .prompt-info }

```yaml
version: "3.7"
services:

  outline:
    image: outlinewiki/outline:latest
    ports:
      - "3002:3000"
    depends_on:
      - postgres
      - redis
    volumes:
      - /volume1/docker/outline/storage-data:/var/lib/outline/data
    environment:
      NODE_ENV: production
      SECRET_KEY: ###SMAZÁNO###
      UTILS_SECRET: ###SMAZÁNO###
      # HTTP
      URL: https://docs.nuf.dscloud.me
      PORT: 3000
      FORCE_HTTPS: false
      WEB_CONCURRENCY: 1
      # Rate limiter
      RATE_LIMITER_ENABLED: true
      RATE_LIMITER_DURATION_WINDOW: 60
      RATE_LIMITER_REQUESTS: 600
      # Authentication
      OIDC_CLIENT_ID: ###SMAZÁNO###
      OIDC_CLIENT_SECRET: ###SMAZÁNO###
      OIDC_AUTH_URI: https://sso.nuf.dscloud.me/webman/sso/SSOOauth.cgi
      OIDC_TOKEN_URI: https://sso.nuf.dscloud.me/webman/sso/SSOAccessToken.cgi
      OIDC_USERINFO_URI: https://sso.nuf.dscloud.me/webman/sso/SSOUserInfo.cgi
      OIDC_USERNAME_CLAIM: username
      OIDC_SCOPES: openid groups email  
      # Storage
      FILE_STORAGE: local
      FILE_STORAGE_LOCAL_ROOT_DIR: /var/lib/outline/data
      FILE_STORAGE_UPLOAD_MAX_SIZE: 26214400
      # Database
      DATABASE_URL: postgres://outline:SMAZÁNO@postgres:5432/outline
      PGSSLMODE: disable
      # Redis
      REDIS_URL: redis://redis:6379
      # Other
      LOG_LEVEL: info
      ENABLE_UPDATES: true
      DEFAULT_LANGUAGE: cs_CZ

  redis:
    image: redis:7
    expose:
      - 6379
    command: redis-server

  postgres:
    image: postgres:16
    expose:
      - 5432
    environment:
      POSTGRES_USER: outline
      POSTGRES_PASSWORD: ###SMAZÁNO###
      POSTGRES_DB: outline
    volumes:
      - /volume1/docker/outline/postgres-data:/var/lib/postgresql/data
```
{: file='docker-compose.yaml'}

## Reverzní Proxy

- Ovládací panel - Přihlašovací portál - Reverzní server proxy
    
- Vytořit - Název: Outline (jen pro přehlednost)
    
    - Zdroj
        
        - Protokol: HTTPS
            
        - Název hostitele: vaše veřejná URL nebo DDNS adresa (bez https://)
            
        - Port: 443
            
        - HSTS: zatím ne
            
    - Cíl
        
        - Protokol: HTTP
            
        - Název hostitele: localhost
            
        - Port: 3002
            
- Záložka - Vlastní záhlaví - Vytvořit - WebSocket
    

Následně by tě po zadání veřejné URL nebo DDNS adresy měl čekat SSO login portál.

![screen](/img/2024-12-02-outline-synology-sso/screenshot.png)