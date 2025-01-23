# H2 Komentaja Pingviini 22.1.2025 23:00


## Johdanto 


Tämän raportin tarkoituksena on vastattu Linux-palvelimet kurssin kotitehtävään h2 (Linkki kappaleen lopussa)'. Alkuun on tiivistetty opettajan materiaaleista Linuxin peruskomennot, joita suurinta osaa käytän harjoituksen tekemiseen. Raportin tarkoituksena on myös esittää Linuxin komentopääteen kometojen käyttöä ja havainnollistaa niiden toiminnallisuuksia.
https://terokarvinen.com/linux-palvelimet/


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

Huomio, tämä tiivistelmä on tehty käyttäen ChatGPT4.0 kielimallia promptilla: "Tee tiivistelmä tämän sivun (https://terokarvinen.com/2020/command-line-basics-revisited/) jokaisesta artikkelista"

### Oma idea

Sivulla voisi olla vielä artikkeli johon on listattu TOP 10 **You need this** linux ohjelmaa asennettavaksi, jotka helpottavat, on hyvä tietää, tarvitsee päivittäin tms.

https://terokarvinen.com/2020/command-line-basics-revisited/

## Lähtötilanne 
Fyysinen tietokone on sama kuin raportin https://github.com/Jesaka/linux-kotitehtavat/blob/main/h1-santeri-karttunen2.md lähtötilanteessa ja virtuaalikone one raportissa OracleVMVirtualboxiin asennettu Debian 12 XFC (Kuvassa speksit) 

<img width="365" alt="image" src="https://github.com/user-attachments/assets/85e48773-bb98-4325-a58c-2a4e1da6dfdf" />



## a) Micro. Asenna micro-editori. 22.1.2025 23:33 

Koska kyseessä on päivän ensimmäinen kerta kun avaan virtuaalitietokoneeni päivitin koneen komennolla sudo-apt get update.

<img width="472" alt="image" src="https://github.com/user-attachments/assets/8eeb3192-401f-4bff-90c6-dddb441fc3c4" />

Tämän jälkeen ajoin terminaaliin komennon `sudo apt-get install micro`. Käytännössä komento vain päivitti **micro**-ohjelman, koska olin jo asentanut ohjelman viime tunnilla. Tämän jälkeen siirryin kansioon /Documents ja loin uuden kansion nimeltä **h2**, johon tämän kotitehtävän tiedostot tallenetaan. Avasin ohjelman kirjoittamanlla terminaaliin komennon `micro`

### Pääte

<img width="473" alt="image" src="https://github.com/user-attachments/assets/16eb426b-bbdd-41df-883a-e32a0f1caeb3" />


### Tältä micro editori näyttää

<img width="470" alt="image" src="https://github.com/user-attachments/assets/4d51e7a6-2d0a-4806-80ea-1699508156ce" />

### Huomioita: 
Tehtävä a) sujui helposti, aikaa kului suhteellisen paljon, koska halusin kuvakaappauksista siistin näköisiä ja helposti ymmärettäviä 

Tehtävän a) tekeminen päättyy 23:53


## b) Apt. Asenna kolme itsellesi uutta komentoriviohjelmaa. 22.1.2025 23:55 

### Ensimmäinen ohjelma Guake 

Ensimmäinen ohjelma, jonka asensin oli edellisellä tunnilla mainittu Guake. Annoin päätteelle komennon `sudo apt-get install guake`. Ohjelma käynnistyi antamalla terminaaliin komento `guake`

<img width="473" alt="image" src="https://github.com/user-attachments/assets/8bd60044-6a5f-4b33-b5dd-372a26acda5b" />

Lopputuloksena on terminaali joka aukeaa pikanäppäimellä fn + f12

<img width="479" alt="image" src="https://github.com/user-attachments/assets/5089f6d9-575b-445e-9b62-acb51835cf30" />

Lisää tietoa Guakesta artikkelista, jonka löysin kun googlasin mitä ohjelmia haluan tehtävässä esitellä.

https://www.zdnet.com/article/5-linux-terminal-apps-that-are-better-than-your-default-and-free-to-install/

### Toinen ohjelma Cmatrix 00:25 

Toinen ohjelma, jonka asensin oli Cmatrix, jonka löysin sivulta. https://www.makeuseof.com/fun-linux-command-line-programs/

Komento jota käytin oli `sudo apt install cmatrix`

<img width="478" alt="image" src="https://github.com/user-attachments/assets/16a87a51-fcd2-458e-aa20-9b8b85e5591f" />

En todella tiedä mitä hyötyä tästä on, ehkä sitä voi käyttää näytönsäästäjänä

<img width="478" alt="image" src="https://github.com/user-attachments/assets/d5f0d535-8093-487b-8bb7-aea8cb1b95e3" />

### Kolmas ohjelma steam logomotive 00:32

Kolmas ohjelma, jonka asensin oli jo kursilla vitsiksi muodostunut steam logomotive. (Opettaja ilmeisesti inhoaa tätä ohjelmaa ja hänen poikansa asentaa sen jokaiselle koneelle. Kiusa se on pienikin kiusa) 

Komento jota käytin sudo apt install `sudo apt install sl`

<img width="477" alt="image" src="https://github.com/user-attachments/assets/5928693e-ca2f-4604-ab08-cdefa9118b24" />

Ja kun ajoin terminaaliin komennon `sl` (tai kun typotan `ls` seuraavalla kerralla) puksuttaa ahkera juna paikalle.

<img width="478" alt="image" src="https://github.com/user-attachments/assets/0ccff00d-dac8-4d7f-a521-fd50fc7c1df8" />


### Huomioita
Ohjelmien asennuksessa itsessään ei ollut ongelmia, suurin osa ajasta meni ohjelmien etsimiseen verkosta. Jos ohjelmat olisi halunnut asentaa kaikki kolme kerralla, komento olisi ollu `sudo apt-get install cmatrix sl guake`.
Tehtävän (b tekeminen päättyi 23.1.2025 00:39 

## c) FHS. Esittele kansiot, jotka on listattu "Command Line Basics Revisited" kappaleessa "Important directories". 23.1.2023 10:18

### /home/santeri

Oletusasetuksena terminaali avasi tämän kansion joka kerta käynnistäessä. Jos halusin takaisin kyseiseen kansioon, pelkkä komento `cd` palauttaa tänne. Kuvassa siirryn kansioihin **Documents** ja sen sisällä kansioon **h2** ja palautan itseni takaisin **/home/santeri/** kansioon. `pwd` Näyttää missä kansiossa olen ja `ls` listaa mitä kansioita tai tiedostoja kansion sisällä om. Täältä löytyy kaikki mitä olen itse käyttäjällä luonut

<img width="476" alt="image" src="https://github.com/user-attachments/assets/b8077cd3-0716-4498-9e5f-9598b8a41fbf" />


### /home 

Home kansioon pääsin antamalla komennon `cd`, jolla siis varmistetaan että aloitan kansiosta /home/santeri `pwd` näyttää, kyllä kansio todella on se missä haluan olla.
Tämän jälkeen annoin komennon `cd ..`. Jolla "peruutan yhden kansion taaksepäin". Home on rakenteessa edellinen kansio, joten päädyin sinne.
Home kansiosta löytyy kaikki käyttäjien kansiot, minun näyttää suppealta, koska koneessa on vain oma käyttäjäni.

<img width="478" alt="image" src="https://github.com/user-attachments/assets/44f68dc5-e970-4bb6-a53c-6c0bbdf460f1" />

(HUOM: cd .. ei anna edellistä kansiota jota olet käsitellyt vaan peruuttaa taaksepäin puurakenteessa) 


### / Eli root directory

Samalla logiikalla `cd ..` pakitti kansioon **/** eli root. Tämän alta löytyy kaikki järjestelmässä oleva tieto.

<img width="475" alt="image" src="https://github.com/user-attachments/assets/c41f5632-e052-41d4-b4f5-836b3d467cad" />


Rootin alla löytyi myös loput kansiot, joita käsittelen tässä tehtävässä eli **/etc**, **/media** ja **/var/log**.

/etc alta löytyi asetuksest, jotka on ihmiselle luettavassa muodossa 

<img width="480" alt="image" src="https://github.com/user-attachments/assets/ac34dfda-6020-4cc4-bed9-7aafc632fcb9" />

Esimerkkinä komennolla `nano timezone` pääsin tarkastelemaan tätä

<img width="478" alt="image" src="https://github.com/user-attachments/assets/d873b660-9947-495b-a8c8-37f30b820755" />

/media kansion alta löytyi köyttäjäni oma kansio, joka on tyhjä koska en ole tallentanut mediaa koneella 

<img width="479" alt="image" src="https://github.com/user-attachments/assets/dbb37424-37e2-46cb-bd45-8832bf3995e2" />

/var/log kansion sisältö näytti tältä, suurin osa lokeista oli nanolla avattaessa tyhjiä. oikeanpuoleisessa kuvassa esimerkki vboxadd-setup.log

<img width="478" alt="image" src="https://github.com/user-attachments/assets/ea043f8b-8b9b-4402-8fec-f07dbb4e20ff" />

<img width="479" alt="image" src="https://github.com/user-attachments/assets/b9f1e73b-c5e3-4138-9859-64141b701fef" />

c)tekeminen päättyi 23.1.2025 11:03


## d) The Friendly M. Näytä 2-3 kuvaavaa esimerkkiä grep-komennon käytöstä. Ohjeita löytyy 'man grep' ja tietysti verkosta. 23.1.2025 11.04

### Esimerkki 1 

Tässä esimerkissä käytin komentoa `grep -r ".txt"`. Oletukseni oli, että grep löytäisi tiedoston, jonka nimi on "a-tehtava.txt", mutta komento ilmoittikin toisen tiedoston "a-tehtava" sisältävän tekstipätkän ".txt" ja tulosti rivin jolla kyseien haku esiintyi.

<img width="476" alt="image" src="https://github.com/user-attachments/assets/60aa3453-ac9e-454d-9d13-57352f1723af" />

### Esimerkki 2 
Tässä esimerkissä käytin komentoa grep `--color=always "skipping" fontconfig.log`
Komennon tarkoitus oli korostaa värillä tietty sana fontconfig.log tiedostosta. Komento toimi juuri kuin halusin. 

(d tekeminen päättyi 23.1.2025 11:26 

<img width="476" alt="image" src="https://github.com/user-attachments/assets/1ee0a63d-ebf1-4a65-92d8-2fbf7aed3586" />

## e) Pipe. Näytä esimerkki putkista (pipes, "|"). 23.1.2025 11:27 

Putkittaminen oli vaikea ymmärtää tunnilla, mutta ChatGPT selitti mitä se tarkoittaa hyvin yksinkertaisesti "Linuxin putkia (|) käytetään yhdistämään komentoja siten, että yhden komennon tuloste ohjataan seuraavan komennon syötteeksi."
Tässä esimerkissä putkitin äsköisen grep komennon syötteeksi komennolle `wc -1`, joka laskee kuinka monta riviä grep löysi

<img width="479" alt="image" src="https://github.com/user-attachments/assets/56c85f9b-f8f4-4115-b89b-b5c362fcee40" />

e) tekeminen päättyi 23.1.2025 11:30 

## f) Rauta. Listaa testaamasi koneen rauta (‘sudo lshw -short -sanitize’). Asenna lshw tarvittaessa. Selitä ja analysoi listaus. 23.1.2025 11:32 

Itse en ymmärrä tietokoneiden raudasta kovin paljon, joten pyysin ChatGPT:tä tekemään tiivistelmän tärkeimmistä osista promptilla "selitä ja analysoi lyhyesti komennolla lshw tekemäni listaus (listaus)".

<img width="479" alt="image" src="https://github.com/user-attachments/assets/6b12afb4-a80c-448d-aa57-7420e70a9268" />

Virtuaalinen ympäristö:
Järjestelmä ajetaan VirtualBox-virtuaalikoneessa.

Suoritin:
Intel Core i5-8365U @ 1.60GHz (virtuaalinen).

Muisti:
4 GiB RAM.

Tallennus:
64 GB virtuaalinen kiintolevy (EXT4-pääosio ja Linux swap).
CD-ROM-asema käytössä.

Näyttö:
SVGA II Adapter (virtuaalinen näyttöohjain).

Verkko:
82540EM Gigabit Ethernet Controller (virtuaalinen verkkokortti).

Ääni ja syöttölaitteet:
AC'97 Audio Controller (virtuaalinen äänikortti).
VirtualBox-hiiri ja -näppäimistö.

Yhteenvetona: kyseessä on perusvirtuaalikone, jossa on virtuaalinen prosessori, muisti, tallennustila ja verkkoyhteydet.

(f tekeminen päättyy 23.1.2025 11:39 



