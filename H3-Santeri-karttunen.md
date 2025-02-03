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

Access log ei päivitynyt apachessa jostain syystä, mutta other_vhost_acces.log päivittyy, kuvakaappaus on siis otettu sieltä komennolla ´sudo cat /var/log/apache2/other_vhosts_access.log | tail -n 20`

<img width="955" alt="image" src="https://github.com/user-attachments/assets/46c3cf25-9b0a-4472-a877-f3b7690c5471" />




## Lähteitä 
https://stackoverflow.com/questions/18392741/apache2-ah01630-client-denied-by-server-configuration

https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/ 

https://httpd.apache.org/docs/2.4/vhosts/name-based.html
