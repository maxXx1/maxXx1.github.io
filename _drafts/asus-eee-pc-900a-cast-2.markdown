---
layout: post
title: Asus Eee PC 900A - Část 2
tags:
- nezarazene
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Můj Eee je již starší a má toho hodně za sebou, proto jsem se snažil práci s ním co nejvíce zefektivnit. V první řadě jsem se mu podíval „na střeva“. Zařízení se rozdělává velmi jednoduše. Po povolení 8mi šroubů ze spodní strany na Vás „vykoukne“ vyměnitelný SSD disk a modul paměti RAM. Nemusíte ani jedno vyndávat či vypojovat, dokonce pokud budete zruční, tak nemusíte odpojovat ani wifi anténu.poté např. malým zalamovacím nožem uvolníte zoubky držící klávesnici, pod klávesnicí Vás čeká ještě nekolik dobře viditelných šroubků a jeden (zhruba ve střední části) skrytý pod nelepenou pečetí. Deska je chycena pouze konektory, které po po odpojení není problém zase vrátit zpět. (jsou různé a mají různou délku přívodních kabelů).

<!--more-->

Co mě velmi překvapilo je to, že ventilátor nemá žádný&nbsp;heat pipe, ani žebrování, které by mohlo být zanesené. Je volně v prostoru. Na chipech není žádné pasivní chlazení, jen teplovodivý polštářek, který odvádí teplo do kovové podložky spojené s honím plastem nacházející se pod klávesnicí.

I když se notebook na omak zespodu zdá být horký, CPU má teplotu normální.

| [![](http://2.bp.blogspot.com/-yMMvuaNfXR0/UeVYopa_yZI/AAAAAAAADJ0/ETCIHRRkRG4/s400/ohweee.JPG)](http://2.bp.blogspot.com/-yMMvuaNfXR0/UeVYopa_yZI/AAAAAAAADJ0/ETCIHRRkRG4/s1600/ohweee.JPG) |
| Open Hardware Monitor |

Ale Eee jsem rozdělával z toho důvodu, že se mi zdálo, že uvnitř něco chrastí. Mé obavy se naplnily… Vevnitř létaly kousky platu a závit z levé i pravé horní strany, který prostě uletěl. Neřekl bych, že to bylo následkem tepla, ani že ho někdo ukroutil, protože pečeť byla neporušena. Okolní šrouby, ale plast hezky přidržely, takže kromě trochu odstáté krytky pantu v tom nevidím velký problém. V dalším díle se mrkneme na software…

**Aktualizace:** &nbsp;Tak mi to nedalo a ještě jsem spustil test pevného disku **ASUS-JM S41 SSD** , žádný vadný sektor se po reinstalaci již neobjevil… viz. HDTune v2.55.

| [![](http://3.bp.blogspot.com/-mo-Em6tk3fo/UeVmvgsPDnI/AAAAAAAADKM/XFJKnozsZkY/s320/hd1.JPG)](http://3.bp.blogspot.com/-mo-Em6tk3fo/UeVmvgsPDnI/AAAAAAAADKM/XFJKnozsZkY/s1600/hd1.JPG) |
| HDTune – Benchmark |

| [![](http://1.bp.blogspot.com/-SRkWHS04XCk/UeVmvruzYGI/AAAAAAAADKI/Kg86N5kq-78/s320/hd2.JPG)](http://1.bp.blogspot.com/-SRkWHS04XCk/UeVmvruzYGI/AAAAAAAADKI/Kg86N5kq-78/s1600/hd2.JPG) |
| HDTune – Info |

| [![](http://4.bp.blogspot.com/-onx87ltlj8k/UeVmvXnLBxI/AAAAAAAADKE/bmPG3ZraGXQ/s320/hd3.JPG)](http://4.bp.blogspot.com/-onx87ltlj8k/UeVmvXnLBxI/AAAAAAAADKE/bmPG3ZraGXQ/s1600/hd3.JPG) |
| HDTune – Health |

| [![](http://4.bp.blogspot.com/-0Rf55DcMynk/UeVmwAUNX3I/AAAAAAAADKc/5hndKUElu7s/s320/hd4.JPG)](http://4.bp.blogspot.com/-0Rf55DcMynk/UeVmwAUNX3I/AAAAAAAADKc/5hndKUElu7s/s1600/hd4.JPG) |
| HDTune – Error Scan |

<!--kg-card-end: html-->