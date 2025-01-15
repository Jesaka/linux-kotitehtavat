# Kotitehtävä H1

### Oman Raportin kijoittaminen tiivistelmä
Raportin tulisi olla Toistettava, Täsmällinen, Helppolukuinen, Viitata lähteisiin, Sisältää vakiotekstejä.
Ideana on, että joku muu voi toistaa samat asiat, samoilla virheillä ja onnistumisilla samassa ympäristössä
lähde: https://terokarvinen.com/2006/raportin-kirjoittaminen-4/

### Free software definition 4 vapautta

"Vapaus käyttää ohjelmaa haluamallasi tavalla, mihin tahansa tarkoitukseen (vapaus 0).
Vapaus tutkia, miten ohjelma toimii, ja muokata sitä niin, että se vastaa tarpeitasi (vapaus 1). Pääsy lähdekoodiin on tämän edellytys.
Vapaus levittää ohjelman kopioita, jotta voit auttaa muita (vapaus 2).
Vapaus jakaa muokattuja versioitasi ohjelmasta muille (vapaus 3). Näin voit antaa koko yhteisön hyötyä tekemistäsi muutoksista. Pääsy lähdekoodiin on tämän edellytys."
(Lainaus käännetty ChatGpt4.0 kielimallia käyttäen)

Vapaus käyttää ohjelmaa haluamallasi tavalla tarkoittaa, että kuka tahansa voi käyttää sitä millä tahansa järjestelmällä ja mihin tahansa tarkoitukseen ilman ilmoitusvelvollisuutta.
Käytön tarkoitus määräytyy käyttäjän tarpeiden mukaan, ei kehittäjän.
Tämä vapaus ei liity ohjelman toimivuuteen tai hyödyllisyyteen. Vaikka ohjelma rajoittaisi syötteitä tai ei toimisi, se ei vie käyttäjiltä vapautta ajaa ohjelmaa.
Vapaat ohjelmistot sallivat ongelmien korjaamisen ja muokattujen versioiden jakamisen, koska vapaudet 1 ja 3 sen mahdollistavat.

Vapaus tutkia ja muokata ohjelmaa edellyttää pääsyä sen selkeään lähdekoodiin.
Laitelukitukset (eng "Tivoization") ja muut estot, jotka rajoittavat muokattujen versioiden käyttöä, tekevät vapaudesta merkityksettömän.
Lisenssin tulee sallia myös muiden vapaiden moduulien yhdistäminen ja hyväksyä kaikki muutokset, eivät vain toisten hyödyllisiksi katsomia.
Vapaus sisältää myös ohjelman poistamisen tai sen korvaamisen toisella.

Vapaus jakaa (vapaudet 2 ja 3) tarkoittaa, että voit levittää ohjelmaa muokattuna tai muokkaamattomana, maksutta tai maksua vastaan, ilman lupaa.
Voit käyttää ja muokata ohjelmaa myös yksityisesti tai julkaista muutokset vapaana ohjelmistona.
Jakamisen vapaus koskee sekä lähdekoodia että suoritettavia versioita, jos niitä on mahdollista luoda.
(Tekstien tiivistämiseen ja kääntämiseen on käytetty ChatGPT4.0 kielimallia)
Lähde: https://www.gnu.org/philosophy/free-sw.html

## RAPORTTI, DEBIAN 12 ASENNUS ORACLE VIRTUAL BOXIIN.

### Tiivistelmä
Tässä raportissa asennetaan OracvleVMVirtualboxille Debian 12 käyttävä virtuaalitietokone koulutöitä varten. Muutamia ongelmia esiintyi koneen asetuksia laittaessa, kun annoin väärät asetukset.
Terminaalin komentojen toteutus ei toiminut täysin ohjeiden mukaan, mutta uudelleen ajolla sain halutut toimenpiteet tehtyä. Jostain syystä virtuaalitietokone ei pysty Copy/Paste Host tietokoneen välillä.
Kysytään opettajalta apua seuraavan tunnin aikana.

### Lähtötilanne 
15.1.2025 klo 09:47
Tämän raportin tarkoitus on kuvata ja raportoida Debian 12 asennus windows pohjaiselle tietokoneelle Oracle VM Virtualboxia käyttäen.
Ohjeena käytetty opettajan kotitehtävään linkkaamaa nettisivua https://terokarvinen.com/2021/install-debian-on-virtualbox/
Oracle VM Virtual Box Ladattuna omalle tietokoneelle. 

Tietokone: HP EliteBook 830 G6

Käyttöjärjestelmä: Windows 11 pro

Suoritin	Intel(R) Core(TM) i5-8365U CPU @ 1.60GHz, 1896 Mhz, 4 ydin(tä), 8 loogista suoritinta

Asennettu fyysinen muisti (RAM)	8,00 Gt

### DEBIAN ISO kuvan lataaminen 09:52
Googlasin "Debian iso Live" google hausta löytyi sivu https://www.debian.org/CD/live/
Valitsin tässä tapauksessa xfc versio

<img width="947" alt="image" src="https://github.com/user-attachments/assets/57e507f7-1ee8-4f86-82eb-f39d93bb5f7b" />

Odotin latauksen valmistumista
### Virtuaalitietokoneen asetukset ja asentaminen 10:02
Nimetään Virtuaalikone, valitaan kansio jonne asennettu tietokone tallentaa itsensä (Käytin itse deafulttia) ja haetaan ISO kuva downloads kansiosta.
En laittanut rastia kohtaan "Skip unattended installation" Jotta pääsen useampaan asetukseen kiinni. Painoin "Next"

<img width="566" alt="image" src="https://github.com/user-attachments/assets/cf2a28d2-60ec-426f-ba7b-99945533d3b0" />

Seuraavaksi luotiin pääkäyttäjä Oma nimi ja vahva salasana. Kohta "Additional options" on jätetty tässä asennuksessa default asetuksille
Painoin "next"

<img width="569" alt="image" src="https://github.com/user-attachments/assets/0e19c5e7-b045-4a7c-a4d5-b0b0491853d8" />

Virtuaalikoneen muisti asetettiin 4GB ja prosessoreita annettiin 4
Painoin "Next"

<img width="568" alt="image" src="https://github.com/user-attachments/assets/751e7838-e5aa-403c-8278-e79231f4d07d" />

Painoin "Create virtual Hard disk" ja annetaan tietokoneelle 60GB tilaa. Opettajan muistiinpanojen mukaan enempi parempi, koska virtuaalikone käyttää vain tallennetun muistin verran
Painoin "Next"

<img width="566" alt="image" src="https://github.com/user-attachments/assets/84e38887-467e-41e2-9753-168081b5d388" />

Seuraavaksi tarkistin Summary välilehdeltä että asetukset ovat halutun laiset ja painoin "Finish"

### Virtuaalikoneen käynnistäminen ja testaaminen 10:15

Virtuaalikone tulisi näkyi Virtualboxin etusivulla, tuplaklikkaa ja käynnistä. En painanut aikaisemmin "Skip unattended install" valitsin nyt asennusmedia ja painoin "mount retry and boot".

<img width="359" alt="image" src="https://github.com/user-attachments/assets/376703da-4aba-4ef7-af9d-d895300e1433" />

Valitsin Boot Menusta Live 

<img width="323" alt="image" src="https://github.com/user-attachments/assets/3b95682b-60c0-46cc-841b-3519db9b4123" />

### Omgelmakohta "Kernel ei yhteensopiva" 10:23
Asetusten laittamisessa olin unohtanut kertoa että asennetaan 64-bittinen eikä 32-bittinen versio
Ratkaisu löytyi nopealla googlauksella täältä https://askubuntu.com/questions/308937/cannot-install-ubuntu-in-virtualbox-due-to-this-kernel-requires-an-x86-64-cpu

<img width="364" alt="image" src="https://github.com/user-attachments/assets/89e37ee3-47d0-4d0d-a37c-cc46fc185b88" />

Korjatsin ongelman Avaamalla Oraclen alkunäytön, valitsin virtuaalitietokone ja settings ja ongelma löytyy heti general sivulta, vaihdoin tilalle "Debian 12 Bookworm (64-bit)"

<img width="575" alt="image" src="https://github.com/user-attachments/assets/680fc167-f935-4bc1-9aef-ab28139cde53" />

### Virtuaalikoneen käynnistäminen ja testaaminen jatkuu 10:27
Käynnistys ja valittiin live

<img width="317" alt="image" src="https://github.com/user-attachments/assets/f74b98c8-4b25-4911-8bcd-80469b014168" />

Työpöytä aukesi live tilassa, avasin verkkoselaimen ja kokeilin toimiiko netti -> Toimii 

<img width="550" alt="image" src="https://github.com/user-attachments/assets/935fca28-3072-474e-9d14-a95640caf714" />

### Running installer 10:32

Painoin työpöydältä Debian installer

1. Welcome sivu: Valitaan kieleksi Englanti
2. Location sivu: Aikavyöhyke Europe Helsinki
3. Keyboard sivu: Finnish Keyboard (Default)
4. Partitions sivu: Erase Disk
5. Users sivu: asetetaan käyttäjätunnus ja salasana
6. Summary sivu: Tarkistetaan yhteenveto ja painetaan install
7. Odotetaan asentumisen päättyminen

 <img width="514" alt="image" src="https://github.com/user-attachments/assets/0e9fe913-a066-41cd-8ae6-415e31dd40f0" />

 Asennus valmis joten känynnistin uudelleen
 
 <img width="631" alt="image" src="https://github.com/user-attachments/assets/b82ee487-77f0-42d8-82e4-5530e9cf0686" />


 ### Asennuksen jälkeinen tarkistaminen 10:53

 Uudelleen käynnistämisen jälkeen tein päivitykset opettajan ohjeiden mukaan. Avasin terminaalin ja laitoin komennon sudo apt-get -y dist-upgrade.
 Mitään ei asennettu komennolla, tulkinta: asennetulle käyttöjärjestelmälle ei tällä hetkellä siis ole päivityksiä.
 
 <img width="407" alt="image" src="https://github.com/user-attachments/assets/a2c42043-55ef-4921-80f5-23dd91357180" />

 Tämän jälkeen asensin palomuurin ja otin sen käyttöön, käytetyt komennot sudo apt-get install ufw ja sudo ufw enable
 
 <img width="413" alt="image" src="https://github.com/user-attachments/assets/5f6b0fba-c521-474d-a9c5-b26cbe934ff1" />

 Virtuaalikone käynnistettiin uudelleen, UFW käyttöönottamiseksi

 Tämän jälkeen kokeilin vielä nettiselaimen toimivuuden, sivusto instagram.com, kaikki ok. 

 Yritin saada tietokonetta koko läppärin näytön kokoiseksi säätämällä Oraclen ikkunasta wiev kohdasta ensin full screen ja sen jälkeen windowed.
 Tämä aiheutti tilanteen jossa en voi enää säätää Oraclen asetuksia vaan näkymä on pelkkä virtuaalitietokone.

 <img width="476" alt="image" src="https://github.com/user-attachments/assets/69eb1c48-f66a-41d5-bfce-7972265a3575" />


 ### Näytön säätäminen 11:10 

 Aloitin sammuttamalla virtuaalikoneen ja käynnistämällä sen uudelleen. Oracle antoi vaihtoehdon avata skaalatussa tilassa painoin cancel ja ongelma korjautui.
 Olen taas lähtötilanteessa, jossa ikkuna on pieni ja näen asetukset Oraclen ikkunassa.

 <img width="957" alt="image" src="https://github.com/user-attachments/assets/76eff70a-2b51-4b4a-b794-afb7b806f3d4" />

 Seuraavaksi painoin Devices Oraclen ikkunasta ja "Insert guest additions CD image..."
 Tämän jälkeen avasin työpöydälle ilmestyneen CD kuvakkeen -> avaa terminaalissa -> $ sudo bash VBoxLinuxAdditions.run -> Log out ja restart

 Ensimmäisellä kerralla mitään ei tapahtunut. Uudelleenkirjautumisen jälkeen terminaali ilmoitti asennuksen olevan jo olemassaa.
 Ajoin ohjelman uudelleen ja tällä kertaa. Opettajan ohjeiden mukaiset tekstit ilmestyivät näyttöön.

 Uusi uudelleen käynnistys ja Linux näyttää siltä kun halutaan

 <img width="959" alt="image" src="https://github.com/user-attachments/assets/e4b6a0b2-b191-4cf5-930e-ff0b43ab923b" />

 Opettajan ohjeiden mukaan Host koneen ja virtuaalitietokoneen tulisi jakaa sama clipboard, mutta Terminaaliin tai verkkoselaimeen ei saanut copy pastettua tekstiä Host koneen ja Virtuaalikoneen välillä.
 Kysytään opettajalta apua seuraavalla tunnilla

 Lopetusaika 11:29 15.1.2025















