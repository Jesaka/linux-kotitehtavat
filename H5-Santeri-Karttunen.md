# h5 Nimekäs 24.2.2025 10:00

## Johdanto 

Edellinen raportti https://github.com/Jesaka/linux-kotitehtavat/blob/main/h4-santeri-karttunen.md

Tämän raportin lähtötilanne poikkeaa edellisestä raportista, koska viimeisen tunnin jälkeen innostuin domainnimestä ja kaikesta tähän asti opitusta ja tein verkkosivut katsomatta kotitehtävää ollenkaan
Raportti tulee osaltaan käsittelemään tehtävän aiheita, mutta ei mene vaihe vaiheelta siihen mitä prosesseja ja komentoja on käytettty. 
Sivu, jonka tein on https://santerikarttunen.com/


### a) Nimi. Laita julkinen nimi osoittamaan omaan koneeseesi. (Siis vastaava kuin terokarvinen.com. Nimen saattaa saada myös ilmaiseksi Github Education -paketilla. Suosittelen hankkimaan oikean nimen, mutta jos välttämättä haluat, voit myös simuloida nimen toimintaa paikallisesti hosts-tiedoston avulla.) 10:10 

Käytin nimen vuokraamiseen Namecheap palvelua, koska sitä oli käytetty esimerkkinä edellisellä tunnilla.

Nimen DNS asetukset olivat muistaakseni ainoat mihin tein muutoksia. 

Valmiina olevat asetukset on muutettu nykyiseen muotoon osoittamaan palvelimeni IP-osoitetta seuraavalla tavalla (@ ja www)


<img width="944" alt="image" src="https://github.com/user-attachments/assets/e422b4b9-4896-4280-8da1-7969592315c8" />


Sekä google verificationia varten lisäsin A-TXT recordin, Saan vielä Google Search consolesta ilmoituksia "kaikkia sivuja ei voida verifioida" joten kun pääsen sukeltamaan sivuston hakukoneoptimointiin, osaan sanoa tästä lisää.


<img width="714" alt="image" src="https://github.com/user-attachments/assets/a81b421d-a5fb-47ae-9450-36f15e71e917" />



Tämän jälkeen loin Webstormissa uuden projektin, jonne koodasin ensimmäisen julkaistun verkkosivuni: https://santerikarttunen.com/
Sivuston siirtäminen Debianin virtuaalikoneeseen tein Virtual Boxin asetuksista käyttäen graafista liittymää "Shared Folders", jolla loin kansion jaetuksi virtuaalikoneen ja raudan välille. (HUOMIO) Shared Folder ominaisuuden käyttäminen asetti kansiot Rootin omistukseen, joten ennen kansioiden siirtämistä sivuston asetuksiin on tarpeellista tarkistaa että apachen ryhmällä on tarvittavat oikeudet käytettäviin kansioihin. Käytin apuna ChatGPT:tä, joka antoi helposti ohjeet miten `chown` komennolla saatiin tarpeelliset oikeudet muokattua.

 ### b) Based. Laita Name Based Virtual Host näkymään uudessa nimessäsi. Kotisvuja pitää pystyä muokkaamaan ilman pääkäyttäjän oikeuksia.

Kuvassa näkyy palvelimen sisältä oikeudet, jotka tiedostoilla on, Santeri käyttäjä pystyy muokkaamaan tiedostoja.


<img width="378" alt="image" src="https://github.com/user-attachments/assets/5037888c-df7a-46e0-8922-1d87afdd6c72" />


### c) Kotisivu. Tee vähintään kolmen erillisen alasivun (esim. index.html, blog.html, projects.html) kotisivu ja kopioi se näkymään palvelimellesi. Sivujen muokkaamisen pitää onnistua ilman pääkäyttäjän oikeuksia, niiden kopioiminen pääkäyttäjänä testisivun paikalle ei käy. Kotisivujen ei tarvitse olla hienoja, mutta niiden tulee olla validia HTML:ää ja linkittää toisiinsa. 10:30 

Tein kopiot tiedostosta index.html
`cp index.html contact.html`
`cp index.html trivia.html`

 ja kirjoitin koodiin rivit, jotka luovat headeriin uudet painikkeet kuten home painike on luotu
 

 <img width="441" alt="image" src="https://github.com/user-attachments/assets/2330f2c5-8b1e-48d2-b99f-2322184c573d" />
 

 Ja muut sivut näyttävät tältä ja niiltä pääsee takaisin vain kotisivulle. (Alisivut on poistettu sivulta ja ne on tehty vain demostroidakseen tämän tehtävän tekeminen)
 

 <img width="856" alt="image" src="https://github.com/user-attachments/assets/c4dd31d3-1b0d-44dd-b5c8-1db5927943be" />
 

### d) Alidomain. Tee kaksi uutta alidomainia, jotka osoittava omaan koneeseesi. Esimerkiksi palvelu on example.com -> linuxkurssi.example.com. Alidomainit ovat tyypillisesti ilmaisia, kun sinulla on päädomain (example.com). Tässä tehtävässä riittää, että alidomainit avaavat saman sivun kuin päädomain. (Vapaaehtoinen bonus: Tee toinen alidomain A-tietueella ja toinen CNAME-tietueella. Vapaaehtoinen bonus: tee alidomainiin oma erillinen name based virtual host.) 10:37 

Koska tehtävässä riittää että alidomain osoittaa samalle sivulle kävin tekemässä seuraavat CNAME tietueet Namecheapin domain asetuksiin.


<img width="734" alt="image" src="https://github.com/user-attachments/assets/ad95b89b-7881-459c-a1c4-49df28c2edf3" />


Ja tässä miltä lopputulos näytti. Jos olisin halunnut tehdä kokonaan uudensivun samaan domainiin olisin voinut luoda uuden sivun ja Name Based Hostin kuten aikaisemmissa tehtävissä on kuvattu. (HUOMIO) Tässä tapauksessa sivusto näyttää ei turvallinen, koska alidomaineille ei ole haettu sertifikaattia jolloin sivu näkyy HTTP, eikä HTTPS)


<img width="944" alt="image" src="https://github.com/user-attachments/assets/66e440bd-a418-4600-9632-3d9b1c41a11d" />


<img width="947" alt="image" src="https://github.com/user-attachments/assets/47a2e9dc-d68f-4432-a2e7-d54132176a6d" />


### e) Tutki jonkin nimen DNS-tietoja 'host' ja 'dig' -komennoilla. Käytä kumpaakin komentoa kaikkiin nimiin ja vertaa tuloksia. Katso man-sivulta, miten komennot toimivat - esimerkiksi miten 'dig' näyttää kaikki kentät. Analysoi tulokset, keskity nimipalvelimelta tulleisiin kenttiin (dig näyttää paljon muutakin tietoa). Etsi tarvittaessa uusia lähteitä haastaviin kohtiin. Sähköpostin todentamiseen liittyvät SPF ja DMARC -tietojen yksityiskohdat on jätetty vapaaehtoiseksi lisätehtäväksi. Tutkittavat nimet: 10:58

Kun yritin ajaa komentoa host omalle sivulleni linux antoi ilmoituksen command not found. Annoin päätteeseen seuraavat komennot
`sudo apt update` `sudo apt install dnsutils -y`

Tämän jälkeen ajoin komennot `dig` ja `host` omalle sivulleni santerikarttunen.com


<img width="770" alt="image" src="https://github.com/user-attachments/assets/393a5135-f1c9-44f3-ac4e-0bdcd7fea42a" />


Toisena sivuna käytin sivua https://ossikallio.com (muokattu 25.2 klo 13:57)


<img width="758" alt="image" src="https://github.com/user-attachments/assets/0a2a355b-61f1-4deb-a7f0-28998a163a36" />


Ison palvelun esimerkkinä käytin instagram.com


<img width="758" alt="image" src="https://github.com/user-attachments/assets/2ac2ad0c-bb93-4f1d-9422-1d58ad2fc10e" />


En osaa itse analysoida tullutta dataa, mutta ChatGPT analysoi tulokset seuraavasti (Käytetty prompt, Tehävänanto ja kaikkien kolmen sivun HOST ja DIG komentojen tulokset + Tee tästä kysymykseen vastaava tiivistelmä) Omat komentit ja Uusien termien selitykset on merkitty (OMA KOMENTTI ALKAA/PÄÄTTYY)

1. host- ja dig-tulosten vertailu
🔹 host-komento:

Näyttää yksinkertaisen vastauksen IP-osoitteista ja mahdollisista sähköpostipalvelimista.
Esimerkiksi santerikarttunen.com palautti IP-osoitteen 80.69.175.196 sekä viisi sähköpostipalvelinta (MX).
ossikallio.com palautti kolme eri IP-osoitetta, mikä viittaa kuormantasaukseen (OMA KOMMENTTI ALKAA " Kuormantasaus. Kuormantasaus on tekniikka jolla useampi WWW-palvelin kytketään yhteen vastaamaan optimaalisesta verkkosivujen toiminnasta kovankin rasituksen alaisena. Samalla suorituskyky ja luotettavuus pystytään maksimoimaan kaikissa tilanteissa." Lähde https://www.osoite.fi/lisapalvelut/. OMA KOMMENTTI PÄÄTTYY)
🔹 dig-komento:

Antaa enemmän teknistä tietoa, kuten kyselyn keston (Query time) ja DNS-palvelimen vastauksen.
santerikarttunen.com vastasi IP-osoitteella 80.69.175.196 (täsmää host-tuloksen kanssa).
ossikallio.com palautti samat kolme IP-osoitetta, mutta dig kertoi myös TTL-arvon (OMA KOMMENTTI ALKAA " Time to Live (TTL) on termi, jota usein käytetään kuvaamaan jonkin verkon yli lähetettävän tai muun datan elinaikaa. TTL voi kuvata konkreettista kellolla mitattavaa aikaa tai jäljellä olevien reititinhyppyjen lukumäärää. Kun aika on kulunut umpeen, datapaketti pudotetaan eli tuhotaan." https://fi.wikipedia.org/wiki/Time_to_Live OMA KOMMENTTI PÄÄTTYY) (3593 sekuntia, eli noin tunti).
instagram.com palautti IPv4- ja IPv6-osoitteet sekä MX-tietueet, jotka liittyvät sähköpostipalvelimiin.
2. Huomionarvoiset seikat
🔸 Palvelinongelmat (communications error to 10.0.2.3#53: timed out)

Joissakin kyselyissä näkyy "timed out" -virheilmoitus, mikä viittaa ongelmaan käytettävän DNS-palvelimen kanssa (10.0.2.3). Tämä voi johtua siitä, että VirtualBoxin verkkoasetukset eivät ole kunnolla määritetty DNS-kyselyitä varten.
🔸 Kuormantasaus (ossikallio.com)

Tämä domain palauttaa kolme eri IP-osoitetta, mikä tarkoittaa, että liikennettä jaetaan useamman palvelimen kesken. Tämä parantaa skaalautuvuutta ja varmistaa palvelun saatavuuden.
🔸 Sähköpostipalvelimet (MX-tietueet)

santerikarttunen.com ja instagram.com palauttivat sähköpostipalvelinten tiedot.
santerikarttunen.com käyttää eforward.registrar-servers.com -palvelimia sähköpostin välittämiseen.
instagram.com käyttää Proofpointin tarjoamaa suodatusta (mxa-00082601.gslb.pphosted.com), mikä viittaa roskapostin torjuntaan ja tietoturvatoimiin.

3. Johtopäätös
✔️ host on nopea ja yksinkertainen, mutta antaa vain perustiedot.
✔️ dig tarjoaa yksityiskohtaisempia tietoja, kuten kyselyajan ja DNS-palvelimen vastauksen.
✔️ Kuormantasaus (useita IP-osoitteita) on käytössä ossikallio.com-domainissa.
✔️ MX-tietueet kertovat, mitkä palvelimet käsittelevät sähköpostiliikennettä.
✔️ Timeout-virheet viittaavat mahdolliseen DNS-palvelimen ongelmaan VirtualBoxin asetuksissa.

# Tehtävän tekeminen päättyy 24.2.2025 11:25


## Lähteet 
https://www.osoite.fi/lisapalvelut/

https://fi.wikipedia.org/wiki/Time_to_Live

https://terokarvinen.com/linux-palvelimet/



