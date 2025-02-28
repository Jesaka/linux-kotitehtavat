# h6 Salataampa 28.2.2025 17:40 
## x) Lue ja tiivistä. Tiivistelmäksi riittää muutama ranskalainen viiva per artikkeli. (Tässä alakohdassa ei tarvitse tehdä testejä tietokoneella)

Tiivistelmät on tehty lukemalla sivujen sisältö ja  käyttäen apuna ChatGPT 4.0 kielimallia promptilla: Tee näiden sivujen sisällöstä tehtävänannon mukaiset tiivistelmä (Linkit ja tehtävänannot) Jonka jälkeen muistiinpanoja on tavittaessa muokattu.

### Let's Encrypt 2024: How It Works

Let's Encrypt on ilmainen ja avoin varmenteiden myöntäjä, joka helpottaa HTTPS-käyttöönottoa.

- Käyttää ACME-protokollaa, joka mahdollistaa varmenteiden automaattisen hankinnan ja uusimisen.

- Todentaa verkkotunnuksen hallinnan esim. DNS-tietueella tai verkkosivuston tiedostolla.

- Kun todistus on vahvistettu, varmenne myönnetään automaattisesti.

- Tämä vähentää manuaalista työtä ja edistää turvallisempaa internetiä.

https://letsencrypt.org/how-it-works/

### Lange 2024: Lego: Obtain a Certificate: Using an existing, running web server (vain tämä kappale, ei "Running a script afterward" tai myöhempiä)

- Web-palvelimen käyttö: Komento lego --email="you@example.com" --domains="example.com" --http run luo sertifikaatit .lego-kansioon.

- DNS-palveluntarjoaja (esim. Gandi): Käytä komentoa GANDI_API_KEY=xxx lego --dns gandi --domains "example.org" run sertifikaatin hankkimiseksi.

- Oman CSR:n käyttö: Komento lego --email="you@example.com" --http --csr="/path/to/csr.pem" run käyttää olemassa olevaa CSR:ää.
  
- Olemassa olevan web-palvelimen käyttö: Kirjoita haasteen tiedosto .well-known/acme-challenge-hakemistoon web-palvelimella.

https://go-acme.github.io/lego/usage/cli/obtain-a-certificate/index.html#using-an-existing-running-web-server

### The Apache Software Foundation 2025: Apache HTTP Server Version 2.4 [Official] Documentation: SSL/TLS Strong Encryption: How-To: Basic Configuration Example (Ei "Cipher Suites and Enforcing Strong Security" eteenpäin. Name based virtual host -tiedostossa tarvitset vain SSLEngine, SSLCertificateFile ja SSLCertificateKeyFile -asetukset)

- Apache HTTP Serverin SSL/TLS-peruskonfiguraatio vaatii mod_ssl-moduulin käyttöönottamisen.
- Pääasetukset:
SSLEngine on – Aktivoi SSL/TLS:n.

SSLCertificateFile /path/to/cert.pem – Määrittää varmenteen tiedostopolun.

SSLCertificateKeyFile /path/to/privkey.pem – Määrittää yksityisen avaimen tiedostopolun.

Näiden asetusten jälkeen palvelin tukee HTTPS-yhteyksiä määritetyllä varmenteella.

https://httpd.apache.org/docs/2.4/ssl/ssl_howto.html#configexample

## a) Let's. Hanki ja asenna palvelimellesi ilmainen TLS-sertifikaatti Let's Encryptilta. Osoita, että se toimii. 

Verkkosivulle on hankittu jo aikaisemmin ennen tehtävää TLS sertifikaatti Let´s Encryptilta, linkin takaa pääsee katsomaan Certbotin ohjeista, kuinka se toimii. https://certbot.eff.org/instructions?ws=apache&os=pip

Kuvassa varmenteen tiedot

<img width="959" alt="image" src="https://github.com/user-attachments/assets/3f88866c-4565-45b5-8d85-eab9db835d4a" />

Koska huomasin varmenteen vanhenevan hyvinkin nopeasti tarkistin certbotin uusivan varmenteen automaattisesti

Komennolla `systemctl list-timers | grep certbot` Tarkistin että certbot on asettanut ajastimen, joka tarkistaa onko varmenne vanhentumassa, Certbot oli asettanut ajastimen.

<img width="395" alt="image" src="https://github.com/user-attachments/assets/eca930e4-f6b3-44f5-97cd-1ea47503d417" />

Ja kokeilin vielä simuloitua uusimista`sudo certbot renew --dry-run
`, joka onnistui

<img width="407" alt="image" src="https://github.com/user-attachments/assets/51b669ed-62a4-4917-9e79-827ef4b7ad87" />





https://santerikarttunen.com/


## b) A-rating. Testaa oma sivusi TLS jollain yleisellä laadunvarmistustyökalulla, esim. SSLLabs (Käytä vain tavanomaisia tarkistustyökaluja, ei tunkeutumistestausta eikä siihen liittyviä työkaluja)

<img width="824" alt="image" src="https://github.com/user-attachments/assets/bcb51edb-582b-4297-9c81-cde198a701cb" />

Analysoinnin tulos näytti pääsääntöisesti hyvältä, sivusto antoi "Fatal handshake error" joiltakin vanhemmilta safarin versioilta ja chrome 49. En koe tarpeelliseksi ryhtyä toimenpiteisiin koska selaimia ei juuri käytetä

Toinen virheilmoitus tuli DNS CAA - NO.

### Mitä se tarkoittaa? 

"CAA is a type of DNS record that allows site owners to specify which Certificate Authorities (CAs) are allowed to issue certificates containing their domain names. It was first standardized in 2013, and the version we use today was standardized in 2019 by RFC 8659 and RFC 8657. By default, every public CA is allowed to issue certificates for any domain name in the public DNS, provided they validate control of that domain name. That means that if there’s a bug in any one of the many public CAs’ validation processes, every domain name is potentially affected. CAA provides a way for domain holders to reduce that risk."  https://letsencrypt.org/fi/docs/caa/

DNS CAA asettamisella voisi siis määrittää kuka voi myöntää varmenteita sivulleni, tällä hetkellä en näe toimenpiteitä tarpeelliseksi, koska sivusto sai A luokituksen testauksesta

## c) Vapaaehtoinen: Tee weppilomake, jossa on käyttäjätunnus ja salasana. Käytä salaamatonta http-yhteyttä. Sieppaa liikennettä (esim. Wireshark, ngrep). Mitä havaitset? Mitä vaikutuksia tällä on tietoturvaan?

Ngrepillä käytännössä näkee suojaamattomalta sivulta salasanat. 

Esimerkkisivu 

<img width="347" alt="image" src="https://github.com/user-attachments/assets/e32c4e32-1b2a-4a9c-b812-2566ba025fa0" />

Ngrepin teoreettinen tulos luotu ChatGPT:llä

<img width="407" alt="image" src="https://github.com/user-attachments/assets/4b1e76f5-bd7e-4b7b-b316-7967a4fdfc4f" />

- Käyttäjätunnus ja salasana näkyvät selkokielisenä siepatun liikenteen joukossa.
- Tämä tarkoittaa, että kuka tahansa verkossa voi kaapata nämä tiedot esim. avoimessa WiFi-verkossa.
- Man-in-the-Middle (MitM) -hyökkäykset ovat mahdollisia, koska tiedot eivät ole salattuja.

# Tehtävän tekeminen päättyy 18:47

Lähteet: 

https://certbot.eff.org/instructions?ws=apache&os=pip

https://go-acme.github.io/lego/usage/cli/obtain-a-certificate/index.html#using-an-existing-running-web-
server

https://httpd.apache.org/docs/2.4/ssl/ssl_howto.html#configexample

https://letsencrypt.org/fi/docs/caa/

https://letsencrypt.org/how-it-works/

https://santerikarttunen.com/

https://ssllabs.com/ssltest/analyze.html?d=santerikarttunen.com

https://terokarvinen.com/linux-palvelimet/
