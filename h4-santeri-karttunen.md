# h4 Maailma kuulee 6.2.2025 11:00 

Johdanto ja lähtötilanne

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

## a) Vuokraa oma virtuaalipalvelin haluamaltasi palveluntarjoajalta.

## b) Tee alkutoimet omalla virtuaalipalvelimellasi: tulimuuri päälle, root-tunnus kiinni, ohjelmien päivitys.

## c) Asenna weppipalvelin omalle virtuaalipalvelimellesi. Korvaa testisivu. Kokeile, että se näkyy julkisesti. Kokeile myös eri koneelta, esim kännykältä.

## d) Vapaaehtoinen: Laita omalle julkiselle palvelimellesi uusi Name Based Virtual Host. 







