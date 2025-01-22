# H2 Komentaja Pingviini 22.1.2025 23:00
## X Lue ja tiivistä Karvinen 2020: Command line basics revisited ja lisää oma kysymys tai idea

### Liikkuminen ja ympäristön tarkastelu:


`pwd` näyttää nykyisen työhakemiston.

`ls` listaa tiedostot nykyisessä hakemistossa.

`cd` hakemisto/ vaihtaa hakemistoa.

`cd ..` siirtyy ylöspäin hakemistohierarkiassa.

`less tiedosto.txt` näyttää tiedoston sisällön sivu kerrallaan.

### Tiedostojen käsittely:


`nano TIEDOSTO.TXT` avaa tiedoston muokattavaksi nano-editorissa.

`mkdir UUSIHAKEMISTO` luo uuden hakemiston.

`mv VANHANIMI UUSINIMI` siirtää tai nimeää uudelleen tiedoston tai hakemiston.

`cp -r ALKUPERÄINEN KOPIO` kopioi tiedoston tai hakemiston.

`rm TIEDOSTO` poistaa tiedoston.

`rm -r HAKEMISTO` poistaa hakemiston ja sen sisällön.


### Etäyhteydet SSH:n avulla:


`ssh käyttäjä@esimerkki.com` avaa suojatun etäyhteyden.

`scp -r HAKEMISTO` käyttäjä@esimerkki.com:public_html/ kopioi hakemiston etäkoneelle.


### Apu ja ohjeet:


`man` komento näyttää komennon manuaalisivun.

komento `--help` tai komento -h antaa lyhyen ohjeen komennosta.


Historia ja automaattinen täydennys:


`Sarkain-näppäin (Tab)` täydentää komentoja ja tiedostonimiä.

`Nuolinäppäimet` selaavat komentohistoriaa.

`history` näyttää aiemmin suoritetut komennot.


### Tärkeitä hakemistoja:


`/home/käyttäjä/`  sisältää käyttäjän kotihakemiston.

`/etc/` sisältää järjestelmän asetustiedostot.

`/var/` sisältää muuttuvat tiedot, kuten lokit.

`/usr/` sisältää käyttäjän asentamat ohjelmat ja kirjastot.

### Oma idea

Sivulla voisi olla vielä artikkeli johon on listattu TOP 10 **You need this** linux ohjelmaa asennettavaksi, jotka helpottavat, on hyvä tietää, tarvitsee päivittäin tms.

https://terokarvinen.com/2020/command-line-basics-revisited/



## a) Micro. Asenna micro-editori.

