# h7 Maalisuora 5.3.2025 17:15 
Järjestelmän tiedot raporteissa h1-h6 kuvatut muutokset tehtnä virtuaalikoneeseen

### Rauta:
Tietokone: HP EliteBook 830 G6

Käyttöjärjestelmä: Windows 11 pro

Suoritin Intel(R) Core(TM) i5-8365U CPU @ 1.60GHz, 1896 Mhz, 4 ydin(tä), 8 loogista suoritinta

Asennettu fyysinen muisti (RAM) 8,00 Gt

### Virtuaalitietokone 


![image](https://github.com/user-attachments/assets/efd3c650-e710-474a-a445-c7e6422ad610)



## a) Kirjoita ja aja "Hei maailma" kolmella kielellä.

Päätin kirjoittaa ohjelmat kielillä bash, python ja perl. (Perl Ohjelman kirjoittamiseen on käytetty ChatGPT4.0 kielimallia prompt: Tehtävänanto, anna vaihtoehtoja kielistä joita voi ajaa suoraan linuxin terminaalissa. (Vaihtoehdot tuotettu chatgpt:llä). Kirjoita Perlillä.) 


<img width="308" alt="image" src="https://github.com/user-attachments/assets/e38232a1-0155-43c5-ac8a-a9e8dc5096a8" />


Kun ohjelmat oli kirjoitettu muutin tiedostojen oikeudet siten että kaikilla on oikeus suorittaa ohjelma komennolla `sudo chmod ugo+x hello.sh hello.py hello.pl`
ja tarkistin että oikeudet ovat oikein komennolla `ls -l `


<img width="299" alt="image" src="https://github.com/user-attachments/assets/4f745cf1-316d-4bad-952f-a632480c225a" />

Kun oikeudet oli tarkistettu, siirsin kirjoitetut ohjelamt kansioon /usr/local/bin/ jotta ne voidaan suorittaa pelkällä tiedostonimellä
`sudo mv hello.sh hello.py hello.pl /usr/local/bin/` 

!Huomio! Tässä kohtaa olisi ollut fiksumpi käyttää komentoa `sudo cp hello.sh hello.py hello.pl /usr/local/bin/`

koska nyt jouduin vielä mennä kansioon vaihtamaan ohjelmien oikeudet rootille, ettei muokkausoikeus jää käyttäjälle itselleen. (Oikeudet tulee poistaa käyttäjältä ettei käyttäjä voi muokata ohjelmaa käyttöönoton jälkeen)


<img width="533" alt="image" src="https://github.com/user-attachments/assets/2e5ed50a-2603-46f7-95ac-3b8a50bc7337" />


Ja nyt ohjelmia voi ajaa vaikka omasta kotihakemistosa käsin 


<img width="530" alt="image" src="https://github.com/user-attachments/assets/6ed41047-942d-47a8-bc41-8e81cb07c22f" />





## b) Lähdeviitteet. Tarkista ja tarvittaessa lisää lähdeviitteet kaikkiin raportteihisi h1 alkaen. Tarkista, että olet viitannut lähteisiin: tehtäväsivuun, kurssiin, muiden opiskelijoiden raportteihin, man-sivuihin, kotisivuihin ja ylipäänsä kaikkiin käyttämiisi lähteisiin. Lähdeviite tulee olla jokaisessa raportissa tai sivussa, jossa lähdettä on käytetty. Kaikki tehtävät perustuvat tämän sivun tehtävänantoihin, joten ainakin tämä viite on syytä löytyä. (Tästä alakohdasta ei tarvitse kirjoittaa vaiheittaista raporttia)

Lähdeviitteet tarkistettu 5.3.2025

## c) Laita Linuxiin uusi, itse tekemäsi komento niin, että kaikki käyttäjät voivat ajaa sitä.

Ohjelma tehtiin samoilla vaiheilla kun tehtävässä a) 

Tältä ohjelma näyttää sisältä ja ajettuna 


<img width="524" alt="image" src="https://github.com/user-attachments/assets/1b35971a-1572-4e8e-9f10-10262a04a771" />


### d) Ratkaise vanha arvioitava laboratorioharjoitus soveltuvin osin.

Arvioitava laboratorioharjoitus – Linux palvelimet ict4tn021-4 tiistai – alkusyksy 2017 – 5 op

## NinjaTietokanta - Haluamme tehdä palvelun, jossa listataan ninjaliikkeitä makeuden, tyylisuunnan ja muiden keskeisten ominaisuuksien suhteen.
Kehittäjämme haluavat käyttää LAMP (Linux Apache MySQL PHP) -pinoa. Asenna tarvittavat ohjelmistot ja tee tietokantaa käyttävä esimerkkiohjelma.

Ohitettu, kurssilla ei ole opetettu tietokantojen tekemistä

## Etätyötä - Haluamme työskennellä etäältä (kuin ninjat piiloistaan).

Kuvassa on otettu yhteys ssh yhteydellä palvelimeen 


<img width="406" alt="image" src="https://github.com/user-attachments/assets/28edeb18-ef89-42c2-b7d6-4488b6bdb472" />



## Käyttäjät - Työntekijämme ovat toimitusjohtaja Nakke Nertola, Håkan Värs, Einari Mikkonen, Einari Öljysaari ja Eija Vähäkäähkä. Tee kaikille käyttäjille esimerkkikotisivut.


<img width="292" alt="image" src="https://github.com/user-attachments/assets/7f02af54-6a9d-4f78-a0a6-327714868594" />
<br>

<img width="321" alt="image" src="https://github.com/user-attachments/assets/dede94f7-1af7-4a14-8457-cd9f7e1af96d" />

<br>

Tässä esimerkki Naken sivuista 
<img width="953" alt="image" src="https://github.com/user-attachments/assets/c6e896f9-56d8-410a-a3a9-2e3056b15ba6" />

<br>

## Suuri muuri - Suojaa kone tulimuurilla.

<img width="255" alt="image" src="https://github.com/user-attachments/assets/065ebd5d-b483-4aaf-b4df-87e1ad79629c" />


## WhoWhere - Tee kaikkien käyttäjien käyttöön komento, joka tulostaa Ninjamaisen tervehdyksen “Hello Ninja”, koneen IP-osoitteen ja komentoa ajavan käyttäjän nimen.
Etsitkö haasteita? Tähtäätkö huipputulokseen? Juuri sitä varten meillä on tarjolla:


<img width="266" alt="image" src="https://github.com/user-attachments/assets/1ee7d44e-2bfc-4e34-9dde-4dc704a89c5e" />

VANHAN LABORATORIOHARJOITUKSEN TEKEMINEN PÄÄTTYY.

## Raportin kirjoittaminen päättyy 19:40 







## Lähteet: 

https://terokarvinen.com/2017/arvioitava-laboratorioharjoitus-linux-palvelimet-ict4tn021-4-tiistai-alkusyksy-2017-5-op/
https://www.geeksforgeeks.org/hello-world-program-in-perl/
https://terokarvinen.com/linux-palvelimet/
