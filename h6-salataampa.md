# H6 – salataampa

Tehtävänanto: https://terokarvinen.com/linux-palvelimet/#h6-salataampa

## x) Tiivistelmät

### Let's Encrypt 2024: How It Works

-Let’s Encrypt mahdollistaa HTTPS-palvelinten luomisen ja luotettavien verkkosertifikaattien hankkimisen ilman ihmisvuorovaikutusta käyttämällä ACME-clientiä palvelimella.

-Setifikaattia varrten luodaan avainpari, jonka avulla tunnistetaan domainin haltija.

-Avainparilla myös voidaan jatkaa sertifikaattia tai peruuttaa se.

### The Apache Software Foundation 2025: Apache HTTP Server Version 2.4 [Official] Documentation: SSL/TLS Strong Encryption: How-To: Basic Configuration Example

-OCSP Stapling, eli The Online Cerrtificate Status Protocol, on mekanismi, jonka avulla selvitetään onko palvelimen sertifikaatti peruutettu vai ei.

-Sertifikaattitodennusta voidaan käyttää käyttäjäoikeuksien hallinnoimisessa.

## a) Let’s Encrypt TLS-sertifikaatti

Ensimmäiseksi avasin virtuaalikonen ja ajoin komennot:

sudo apt-get update

sudo apt-get upgrade

sudo apt-get dist-upgrade

sudo systemctl restart apache2

<img width="1008" height="160" alt="Näyttökuva 2025-09-30 150511" src="https://github.com/user-attachments/assets/eb855577-9380-4124-a188-f3cbe708d777" />

Viimeinen komento ei toiminut ja syynä oli kirjoitusvirhe: olin kirjoittanut "AliasName" enkä "ServerAlias". Korjasin tämän.

<img width="1146" height="47" alt="Näyttökuva 2025-09-30 151016" src="https://github.com/user-attachments/assets/1c6d8963-120a-4666-ae04-a255150748f3" />

Kokeilin, että oinonen.website näkyy curlilla, virtuaalikoneen selaimella ja henkilökohtaisen pc:n selaimella.

<img width="582" height="324" alt="Näyttökuva 2025-09-30 151933" src="https://github.com/user-attachments/assets/dd79e9ef-281a-4be4-85dd-b7eb2edfc337" />

<img width="932" height="321" alt="Näyttökuva 2025-09-30 152004" src="https://github.com/user-attachments/assets/88986858-3da8-42d8-901c-61c72dc43fce" />

<img width="877" height="522" alt="Näyttökuva 2025-09-30 152026" src="https://github.com/user-attachments/assets/64849304-9f6f-419c-aa09-a103f9823742" />

Käytin certbotin ohjeistuksia: https://certbot.eff.org/instructions?ws=apache&os=pip

<img width="1062" height="1251" alt="Näyttökuva 2025-09-30 161913" src="https://github.com/user-attachments/assets/86f25466-8b7d-4f2d-8222-454aaf4ac6f9" />

Kirjauduin SSH-tunnuksella sisään ja ajoin seuraavat komennot ohjeen mukaan.

sudo apt update

sudo apt install python3 python3-dev python3-venv libaugeas-dev gcc

sudo python3 -m venv /opt/certbot/

sudo /opt/certbot/bin/pip install --upgrade pip

sudo /opt/certbot/bin/pip install certbot certbot-apache

sudo ln -s /opt/certbot/bin/certbot /usr/bin/certbot

Vaihtoehtona oli antaa certbotin hoitaa konfiguraatio automaattisesti tai tehdä se itse. Päätin antaa certbotin tehdä sen.

sudo certbot –apache

echo "0 0,12 * * * root /opt/certbot/bin/python -c 'import random; import time; time.sleep(random.random() * 3600)' && sudo certbot renew -q" | sudo tee -a /etc/crontab > /dev/null

sudo /opt/certbot/bin/pip install --upgrade certbot certbot-apache

Kokeilin avata oinonen.websiten, mutta en saanut siihen yhteyttä.

<img width="1121" height="670" alt="Näyttökuva 2025-09-30 162727" src="https://github.com/user-attachments/assets/3bc1621f-a6b6-40ff-b63b-e4be315bcba0" />

En ehtinyt ratkaista tätä ongelmaa.

## b) A-rating

Käytin ehdotettua sivua tässä tehtävässä: https://www.ssllabs.com/ssltest/

Niin kuin ajattelin, raportin tulos oli tämä:

<img width="1074" height="802" alt="Näyttökuva 2025-09-30 164022" src="https://github.com/user-attachments/assets/b99887e3-4fbd-43ab-b7cb-81bd6274856c" />


