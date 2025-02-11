# h4 Maailma kuulee 6.2.2025 11:00 Päivitetty 11.2.2025 18:51

### Johdanto ja lähtötilanne
Tämän raportin tavoitteena on suorittaa virtuaalipalvelimen vuokraaminen Upcloudista ja päivittää oma pelkistetty HTML sivu julkiseen internettiin

Tietokone: HP EliteBook 830 G6

Käyttöjärjestelmä: Windows 11 pro

Suoritin Intel(R) Core(TM) i5-8365U CPU @ 1.60GHz, 1896 Mhz, 4 ydin(tä), 8 loogista suoritinta

Asennettu fyysinen muisti (RAM) 8,00 Gt

Virtuaalikone: 

<img width="368" alt="image" src="https://github.com/user-attachments/assets/5be04fbb-9a85-4251-b63e-383c7ed1f9a0" />





## x) Lue ja tiivistä. Tiivistelmäksi riittää muutama ranskalainen viiva per artikkeli. (Tässä alakohdassa ei tarvitse tehdä testejä tietokoneella)
Susanna Lehto 2022: Teoriasta käytäntöön pilvipalvelimen avulla (h4) (opiskelijan esimerkkiraportti), kohdat
a) Pilvipalvelimen vuokraus ja asennus
d) Palvelin suojaan palomuurilla
e) Kotisivut palvelimelle
f) Palvelimen ohjelmien päivitys
Karvinen 2012: First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS

### Pilvipalvelimen vuokraus ja asennus:

Vuokraa pilvipalvelin
Yhdistä palvelimeen SSH:lla ja vaihda root-salasana.
Luo uusi käyttäjä ja anna sille sudo-oikeudet.

### Palvelin suojaan palomuurilla:

Ota käyttöön UFW (Uncomplicated Firewall).
Salli vain tarvittavat portit (esim. 22 SSH:lle, 80 ja 443 HTTP/HTTPS:lle).
Aktivoi ja tarkista palomuurin asetukset.

### Kotisivut palvelimelle:

Asenna verkkopalvelinohjelmisto, kuten Nginx tai Apache.
Lataa verkkosivut palvelimelle ja määritä tarvittavat asetukset.
Varmista, että sivut näkyvät internetissä.

### Palvelimen ohjelmien päivitys:

Päivitä paketit säännöllisesti komennolla apt update && apt upgrade.
Tarkista turvapäivitykset ja asenna ne mahdollisimman pian.
Automaattisten päivitysten käyttöönotto voi lisätä turvallisuutta.

Tiivistelmä on tehty käyttäen apuna ChatGPT4.0 kielimallia promptilla: Tee näiden verkkosivujen artikkeleista Pilvipalvelimen vuokraus ja asennus, Palvelin suojaan palomuurilla, Kotisivut palvelimelle, Palvelimen ohjelmien päivitys, Tiivistelmä. Muutama ranskalainen viiva riittää.

## a) Vuokraa oma virtuaalipalvelin haluamaltasi palveluntarjoajalta. 11:10 

Palvelin vuokrattiin tässä tilanteessa sivustolta https://hub.upcloud.com. Sivustolle oli tehty aikaisemmin käyttäjä tunnin aikana ja tehtävää aloittaessa olin poistanut tunnilla tehdyn palvelimen, jotta voin kuvata raportin alusta alkaen. 

Valitsin valikosta Servers ja Deploy server

<img width="960" alt="image" src="https://github.com/user-attachments/assets/35c1b6bb-941d-4fc8-8520-b91c40381b48" />

#### Lyhyesti mitä valintoja tein palvelimelle 
(Valinnat joita en ole käsitellyt jätin sellaiseksi kun ne olivat standardiasetuksilla.)

Location: FI-HEL1 Finland

Plan: Halvin mahdollinen 1GB muistia, 10GB storagea ja hintaa 3e per kuukausi

Operating system: Debian GNU/Linux 12 (Bookworm)

Network: Public IPv4 Kyllä, Utility network Kyllä, Public IPv6 Kyllä

Login method: SSH keys (Avaimet on jo generoitu enkä käy sen tekemistä tässä raportissa läpi)

Hostname: Muutin omaksi 



Tämän jälkeen painoin deploy ja odotin että palvelin käynnistyy

<img width="960" alt="image" src="https://github.com/user-attachments/assets/1baf46e8-9d95-4eb7-9c43-9474b3fdf260" />

Kun palvelin oli käynnistynyt kirjaudun sisään root käyttäjänä komennolla `ssh root@80.69.175.196` ja vastasin `y` vastaan tulevaan fingerprint kyselyyn

Palvelimeen päästiin siälle joten tämä vaihe ok. 





## b) Tee alkutoimet omalla virtuaalipalvelimellasi: tulimuuri päälle, root-tunnus kiinni, ohjelmien päivitys. 11:36 

Ensimmäiseksi asensin tulimuurin palvelimelle komennolla `sudo apt-get install ufw`, tämän jälkeen tein `sudo ufw allow 22/tcp`jotta pääsemme ssh yhteydellä sisälle ja `sudo ufw enable` jolla tulimuuri menee päälle, `exit` ja uudelleen yhdistäminen, jotta näin pääseväni sisään vielä `ssh root@80.69.175.196`

<img width="299" alt="image" src="https://github.com/user-attachments/assets/60ece9d2-9354-4e76-a4ec-e19bd296ce56" />

### Oman käyttäjän luominen, ja rootin poistaminen 

Annoin palvelimella komennot `sudo adduser santeri` ja tein käyttäjälle salasanan ja asetukset.
Annoin komennon `sudo adduser santeri sudo` jolla lisäsin uuden käyttäjän sudo ryhmään.

Seuraavaksi kopioin ssh avaimet rootin kansiosta santeri käyttäjälle, jotta pääsemme sisään palvelimelle myös santeri käyttäjällä `cp -n -r /root/.ssh /home/santeri/` ja tarkistin vielä että avaimet ovat olemassa. (Tässä vaiheessa myös testasin santeri käyttäjää pääsenkö sisälle ja toimiihan sudo komento) 

### HUOMIOHUOMI 11:48 

Tässä vaiheessa olin unohtanut muuttaa oikeudet kopioituun ssh kansioon santeri käyttäjälle (.ssh kansion omisti vielä root eikä santeri), joten kirjautumienn epäonnistui syystä (publickey denied). 

Kirjauduin takaisin root käyttäjälle ja korjasin tilanteen näin `chwon`komennolla jolla annoin käyttäjälle santeri kansion oikeudet

<img width="555" alt="image" src="https://github.com/user-attachments/assets/8069a8ac-8009-4c01-ab76-753390d1023a" />

Vika korjattu 11:53 

Uusi yritys näytti paremmalta ja kirjautuminen onnistui, testaisin samalla sudo komennon `sudo echo moikka` joka meni läpi, jolloin käyttäjä löytyy myös sudo ryhmästä ja sudo toimii. 

<img width="960" alt="image" src="https://github.com/user-attachments/assets/acd2c0f8-e675-49c9-82a2-ec639d7b8d13" />.

Root käyttäjän lukitseminen ja ssh-avainten poistaminen tehtiin kommennoilla `sudo usermod --lock root` (Lukitsee rootin kirjautumisen) ja `sudo rm /root/.ssh -r` (Poistaa rootin ssh avaimen). Tämän jälkeen kokeilin pääseekö roottina sisään.

lopputuloksena rootilla ei enää päässyt sisään palvelimelle.

<img width="329" alt="image" src="https://github.com/user-attachments/assets/e0d91f2c-6786-441e-ac0a-b082514a13eb" />

Kun root oli lukittu ulos palvelimelta ajoin komennot `sudo apt-get update` ja `sudo apt-get upgrade`

viimeisenä valmistelin webbipalvelimen asennusta varten palomuuriin portin 80 auki komennolla `sudo ufw allow 80/tcp`


## c) Asenna weppipalvelin omalle virtuaalipalvelimellesi. Korvaa testisivu. Kokeile, että se näkyy julkisesti. Kokeile myös eri koneelta, esim kännykältä. 12:07 

Aloitin asentamalla apchen webbipalvelimeen komennolla `sudo apt-get -y install apache2`

Tämän jälkeen korvasin standardina olevan sivun omalla sivulla, jolla lukee vain default `echo "Default"|sudo tee /var/www/html/index.html`

Nyt sivu näyttää tältä 

<img width="960" alt="image" src="https://github.com/user-attachments/assets/7b51a856-e77c-4838-ae13-465b19421093" />

Ja nytkun palvelimella oli tehty kaikenlaista reboottasin järjestelmän komennolla `sudo systemctl reboot`

Tämän jälkeen pidin tauon, tauko alkoi 12:23 


## d) Vapaaehtoinen: Laita omalle julkiselle palvelimellesi uusi Name Based Virtual Host. 12:40 
Aloitin tekemällä conf tiedoston verkkosivun nimellä seuraavilla komennoilla.

`sudoedit /etc/apache2/sites-available/santerikarttunen.fi.conf`
(teki tiedoston johon pääsin kirjoittamaan)

`cat /etc/apache2/sites-available/santerikarttunen.fi.conf`
(Tarkistin terminaalissa vielä miltä tiedosto näyttää)

<img width="376" alt="image" src="https://github.com/user-attachments/assets/274f29f1-35c3-4f06-89e1-cd183c30b37b" />


tämän jälkeen laitoin sivun päälle `sudo a2ensite santerikarttunen.fi`
ja otin defaultin pois `sudo dissite 000-default.conf `

# TÄSSÄ KOHTAA ON TEHTY VAARALINEN TOIMENPIDE ÄLÄ TOISTA VIRHETTÄ ÄLÄ MUUTA ASETUKSIA KUTEN ALLA ON MUUTETTU (Päivitys 11.2.2025)
## VIRHE POISTUI TARKASTAMALLA SITES-AVAILABLE CONFIGISTA KIRJOITUSVIRHE POIS 
Sivusto ei vielä toiminut tässä vaihessa ja sain error koodia joka ilmoitti ettei apache pääse hakemaan sivua. (AH01630: client denied by server configuration: /home/santeri/publicsites/santerikarttunen.fi/) 

Ongelma ratkesi hakemall Apachen asetukset `sudo nano /etc/apache2/apache2.conf` ja muuttamalla kohdan 

<Directory />

   Options FollowSymLinks
    
   AllowOverride None
    
   Require all denied -> Require all granted 
    
</Directory>

(Jos tämä aiheuttaa tietoturvauhan antakaa palautetta) 

# VAARALLINEN TOIMEPIDE PÄÄTTYY (Päivitetty osio päättyy)
lopputuloksena sivu näkyy näin 

<img width="960" alt="image" src="https://github.com/user-attachments/assets/e4238206-a59d-42d4-be9a-5a8a55c154c9" />

Tässä vielä index.html oikeudet 

<img width="329" alt="image" src="https://github.com/user-attachments/assets/c156891f-b403-4cc2-a241-74abe13bdb44" />


Domain nimi ei näy vielä oikein, luulen että siihen saa vastauksia seuraavalla tunnilla! 


Raportti päättyy 13:34 

## Lähteet: 
https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/

https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/

https://serverfault.com/questions/1041060/solving-apache-search-permissions-are-missing-on-a-component-of-the-path-issue

https://httpd.apache.org/docs/2.4/vhosts/name-based.html

https://github.com/Jesaka/linux-kotitehtavat/blob/main/H3-Santeri-karttunen.md

ChatGPT prompt: Apacheen laitettu sivusto ei lataa chromessa ja antaa seuraavan virhekoodin, mitä voin tehdä? AH00035: access to / denied (filesystem path '/home/santeri/publicsites') because search permissions are missing on a component of the path 

ChatGPT prompt: Tee näiden verkkosivujen artikkeleista Pilvipalvelimen vuokraus ja asennus, Palvelin suojaan palomuurilla, Kotisivut palvelimelle, Palvelimen ohjelmien päivitys, Tiivistelmä. Muutama ranskalainen viiva riittää.










