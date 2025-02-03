# h3 Hello Web Server 3.2.2025 11:10 

## Lähtötilanne 11:11 

Rauta:
Tietokone: HP EliteBook 830 G6

Käyttöjärjestelmä: Windows 11 pro

Suoritin Intel(R) Core(TM) i5-8365U CPU @ 1.60GHz, 1896 Mhz, 4 ydin(tä), 8 loogista suoritinta

Asennettu fyysinen muisti (RAM) 8,00 Gt

Virtuaalitietokone: 

<img width="365" alt="image" src="https://github.com/user-attachments/assets/85e48773-bb98-4325-a58c-2a4e1da6dfdf" />

Apache2 on asennettuna ja ensimmäinen sivu konfiguroitu oppitunnintunnin aikana, sivuston ulkoasu on vielä hyvin minimaalinen. 


### a) Testaa, että weppipalvelimesi vastaa localhost-osoitteesta. Asenna Apache-weppipalvelin, jos se ei ole jo asennettuna. 11:14 

<img width="260" alt="image" src="https://github.com/user-attachments/assets/e950884c-d3ee-4bfe-b309-f164cd5a2d29" />

### b) Etsi lokista rivit, jotka syntyvät, kun lataat omalta palvelimeltasi yhden sivun. Analysoi rivit (eli selitä yksityiskohtaisesti jokainen kohta ja numero, etsi tarvittaessa lähteitä). 11:16 

Access log ei päivitynyt apachessa jostain syystä, mutta other_vhost_acces.log päivittyy, kuvakaappaus on siis otettu sieltä komennolla `sudo cat /var/log/apache2/other_vhosts_access.log | tail -n 20`. Tulkittavaksi on otettu 2 viimeistä riviä

<img width="958" alt="image" src="https://github.com/user-attachments/assets/06c13841-c9ce-466f-93d7-84fb43f2806b" />


En osannut itse selittää lokirivejä, joten ChatGpt auttoi käytetty prompt: Analysoi lokirivit ja selitä mitä ne tarkoittavat: (copy paste lokirivit) 

<img width="412" alt="image" src="https://github.com/user-attachments/assets/d6b57862-10f4-4e44-8744-7cd34edc850c" />

<img width="405" alt="image" src="https://github.com/user-attachments/assets/ac9a30bd-31dc-46ac-afb2-59debb03f3be" />

### c) Etusivu uusiksi. Tee uusi name based virtual host. Sivun tulee näkyä suoraan palvelimen etusivulla http://localhost/. Sivua pitää pystyä muokkaamaan normaalina käyttäjänä, ilman sudoa. Tee uusi, laita vanhat pois päältä. Uusi sivu on hattu.example.com, ja tämän pitää näkyä: asetustiedoston nimessä, asetustiedoston ServerName-muuttujassa sekä etusivun sisällössä (esim title, h1 tai p). 11:52 

Aloitin tekemällä uuden conf tiedoston komennolla `sudoedit hattu.example.com.conf`. Konffaukset opettajan ohjeiden mukaiseksi. 

<img width="336" alt="image" src="https://github.com/user-attachments/assets/664ae7cc-9e87-434a-9c14-463fd2b3672a" />


<img width="467" alt="image" src="https://github.com/user-attachments/assets/e8d2165f-eb48-456e-a506-dbe788137de1" />

Seuraavaksi asetin sivuston päälle ja disenablesin vanhan sivuni pois.

<img width="470" alt="image" src="https://github.com/user-attachments/assets/72653f9d-8fda-4823-9c5e-80aa42bef5c0" />

Tämän jälkeen `sudo systemctl restart apache2`

Sivun uudelleen lautauksessa tulee virheilmoitus, uudet asetukset ovat siis perillä, nyt pitää enään luoda sivu kansioon, jonka päästä conf tiedosto sen hakee

<img width="476" alt="image" src="https://github.com/user-attachments/assets/63b66052-1097-45da-bd4d-ce417f8614e0" />

annoin komennon `echo hattu > //home/santeri/publicsites/hattu.example.com/index.html`

tämän jälkeen uudelleen käynnistin apache2 päivitin selaimessa sivun.

tadaa!

<img width="347" alt="image" src="https://github.com/user-attachments/assets/2c0254b9-7aa4-4911-8ead-38ee9aa7fb92" />





## Lähteitä 
https://stackoverflow.com/questions/18392741/apache2-ah01630-client-denied-by-server-configuration

https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/ 

https://httpd.apache.org/docs/2.4/vhosts/name-based.html
