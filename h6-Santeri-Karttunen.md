# h6 Salataampa 28.2.2025
## x) Lue ja tiivistä. Tiivistelmäksi riittää muutama ranskalainen viiva per artikkeli. (Tässä alakohdassa ei tarvitse tehdä testejä tietokoneella)
### Let's Encrypt 2024: How It Works

Let's Encrypt on ilmainen ja avoin varmenteiden myöntäjä, joka helpottaa HTTPS-käyttöönottoa.

- Käyttää ACME-protokollaa, joka mahdollistaa varmenteiden automaattisen hankinnan ja uusimisen.

- Todentaa verkkotunnuksen hallinnan esim. DNS-tietueella tai verkkosivuston tiedostolla.

- Kun todistus on vahvistettu, varmenne myönnetään automaattisesti.

- Tämä vähentää manuaalista työtä ja edistää turvallisempaa internetiä.

### Lange 2024: Lego: Obtain a Certificate: Using an existing, running web server (vain tämä kappale, ei "Running a script afterward" tai myöhempiä)

- Lego on ACME-asiakasohjelma, jota käytetään Let's Encrypt -varmenteiden hankintaan.
- Jos käytössä on jo käynnissä oleva verkkopalvelin, Lego voi käyttää "standalone"-tilaa varmenteen hakemiseen.
- Tämä edellyttää, että verkkopalvelin pysäytetään hetkeksi tai että käytetään DNS- tai verkkopalvelintodennusta (kuten HTTP-01-haastetta).
- Kun varmenne on hankittu, se voidaan ottaa käyttöön verkkopalvelimessa normaalisti.

### The Apache Software Foundation 2025: Apache HTTP Server Version 2.4 [Official] Documentation: SSL/TLS Strong Encryption: How-To: Basic Configuration Example (Ei "Cipher Suites and Enforcing Strong Security" eteenpäin. Name based virtual host -tiedostossa tarvitset vain SSLEngine, SSLCertificateFile ja SSLCertificateKeyFile -asetukset)

- Apache HTTP Serverin SSL/TLS-peruskonfiguraatio vaatii mod_ssl-moduulin käyttöönottamisen.
- Pääasetukset:
SSLEngine on – Aktivoi SSL/TLS:n.
SSLCertificateFile /path/to/cert.pem – Määrittää varmenteen tiedostopolun.
SSLCertificateKeyFile /path/to/privkey.pem – Määrittää yksityisen avaimen tiedostopolun.
Näiden asetusten jälkeen palvelin tukee HTTPS-yhteyksiä määritetyllä varmenteella.

## a) Let's. Hanki ja asenna palvelimellesi ilmainen TLS-sertifikaatti Let's Encryptilta. Osoita, että se toimii.
## b) A-rating. Testaa oma sivusi TLS jollain yleisellä laadunvarmistustyökalulla, esim. SSLLabs (Käytä vain tavanomaisia tarkistustyökaluja, ei tunkeutumistestausta eikä siihen liittyviä työkaluja)
## c) Vapaaehtoinen: Tee weppilomake, jossa on käyttäjätunnus ja salasana. Käytä salaamatonta http-yhteyttä. Sieppaa liikennettä (esim. Wireshark, ngrep). Mitä havaitset? Mitä vaikutuksia tällä on tietoturvaan?
