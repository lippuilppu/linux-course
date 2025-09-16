# H4 – Maailma kuulee

Tehtävänanto: https://terokarvinen.com/linux-palvelimet/#h4-maailma-kuulee

## x) Tiivistelmät

### Teoriasta käytäntöön pilvipalvelimen avulla (h4)

-Palvelimia ja domainnimiä voidaan vuokrata netin kautta.

-Palomuurin asennus komennolla ’sudo apt-get install ufw’ ja käyttöönotto komennoilla ’sudo ufw allow 22/tpc’ ja ’sudo ufw enable’.

-Asenna vuoratulle virtuaalikoneelle Apache-webbipalvelin ja korvaa testisivu uudella kotisivulla.

-Ohjelmien päivitys tapahtuu näiden komentojen avulla: ’sudo apt-get update’, ’sudo apt-get upgrade’ ja ’sudo apt-get dist-upgrade’.

### First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS

-Luo uusi virtuaaliserveri DigitalOceanin kautta.

-Asenna palomuuri ja luo uusi sudo-käyttäjä.

-Lukitse juurikäyttäjä ja kytke SSH:n sisäänkirjautuminen pois päältä.

-Päivitä: ’sudo apt-get update’ ja ’sudo apt-get upgrade’.

-Käytä DNS-nimeä IP-osoitteen sijaan.

## a) Virtuaalipalvelimen vuokraus

Olin edellisellä viikolla kipeänä, jonka takia jätin oppitunnin väliin, joten käytin apuna kyseistä ohjetta. 

https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/

En saanut varmennettua opiskelijastatusta, joten en käyttänyt GitHub Education-pakettia. Otin DigitalOceanin käyttöön GitHub-tunnuksen avulla. Tämä ei vaatinut sisäänkirjautumista, vaan DigitalOcean automaattisesti yhdistyi GitHub-tiliin. 

<img width="1893" height="783" alt="Näyttökuva 2025-09-16 130531" src="https://github.com/user-attachments/assets/ebb517b4-c43c-45a1-aedd-ba8701a8d1d0" />


Create Droplets-osiosta loin uuden virtuaalipalvelimen. Valinnat tein ohjeen mukaisesti:

-Datakeskukseksi valitsin Amsterdamin

-Käyttöjärjestelmäksi uusimman version Debianista

-Salasanan SSH-avaimen sijaan

-Toiseksi halvimman CPU-peruspaketin, jossa oli yksi CPU, SSD:n kovalevy 25 GB ja siirtodataa 1000 GB (sama kuin ohjeessa)

-Hostnimeksi vain Debian

<img width="1683" height="440" alt="Näyttökuva 2025-09-16 131443" src="https://github.com/user-attachments/assets/0dd1dd8b-99ca-4db1-b424-def773780cab" />
<img width="1235" height="304" alt="Näyttökuva 2025-09-16 131855" src="https://github.com/user-attachments/assets/2221a7f4-bc5a-4c86-8c92-c6e0b8ef281a" />

## b) Alkutoimet

Avasin terminaalin ja koitin ottaa yhteyden luomaani virtuaalikoneeseen komennolla ’ssh root@64.225.78.135’, mutta salasanani ei toiminut. Menin takaisin DigitalOceaniin ja valitsin Access-osiosta ’Reset root password’. Kokeilin kirjautua uudelleen ja vaihdoin salasanan onnistuneesti terminaalissa.

<img width="820" height="232" alt="Näyttökuva 2025-09-16 141249" src="https://github.com/user-attachments/assets/252830e1-7c4f-4b8a-ae41-3916a2a53f35" />


Päivitin komennolla ’sudo apt-get update’.

<img width="824" height="191" alt="Näyttökuva 2025-09-16 141432" src="https://github.com/user-attachments/assets/6b17a365-5179-4f5c-8dc8-dbcbb220e417" />


Asensin palomuurin komennolla ’sudo apt-get install ufw’.

<img width="876" height="550" alt="Näyttökuva 2025-09-16 141611" src="https://github.com/user-attachments/assets/d17be39a-652f-42ce-8cf3-53aeed0a3923" />


Tein reiän ja kytkin palomuurin päälle komennoilla ’sudo ufw allow 22/tcp’ ja ’sudo ufw enable’. Tehtävänannon vinkeissä oli komento ’sudo ufw allow 80/tcp’, joten syötin myös sen.

<img width="860" height="190" alt="Näyttökuva 2025-09-16 141919" src="https://github.com/user-attachments/assets/b70464c4-a62e-493b-964f-08eff1d29a47" />


Loin uuden käyttäjän komennolla ’sudo adduser ilona’. Tietoihin laitoin ainoastaan oikean nimen ja muut kohdat jätin tyhjiksi. Annoin käyttäjällä sudo-oikeudet komennolla ’sudo adduser ilona sudo’.

<img width="863" height="266" alt="Näyttökuva 2025-09-16 142704" src="https://github.com/user-attachments/assets/4d39838d-b472-4793-a9d0-8318ed71d338" />


Kopioin root.n ssh-asetukset näillä komennoilla, jotka olivat vinkit-osiossa: ’sudo cp -rvn /root/.ssh/ /home/jurpo/’ ja ’sudo chown -R jurpo:jurpo /home/jurpo/’. Tämän jälkeen palasin paikalliselle koneelle.

<img width="861" height="153" alt="Näyttökuva 2025-09-16 143753" src="https://github.com/user-attachments/assets/469a5928-15ce-4898-9cb8-af6fa3f124b5" />


Kirjauduin uudelleen sisään komennolla ’ssh ilona@64.225.78.135’.

<img width="858" height="230" alt="Näyttökuva 2025-09-16 144226" src="https://github.com/user-attachments/assets/e58eac9a-7b96-458f-8fa7-0d07e69ffd1f" />


Suljin root-tunnuksen komennoilla: ’sudo usermod --lock root’ ja ’sudo mv -nv /root/.ssh /root/DISABLED-ssh/’.

<img width="858" height="96" alt="Näyttökuva 2025-09-16 144421" src="https://github.com/user-attachments/assets/bff0dfce-4759-4195-933d-1b2d5bd774d0" />


Hoidin päivitykset komennoilla ’sudo apt-get update’, ’sudo apt-get upgrade’ ja ’sudo apt-get dist-upgrade’.

<img width="859" height="420" alt="Näyttökuva 2025-09-16 144807" src="https://github.com/user-attachments/assets/bab6a3aa-8936-495e-81c6-46f7032608d0" />




## c) Weppipalvelimen asennus

Asensin Apache-palvelimen komennolla ’sudo apt-get install apache2’.

<img width="861" height="271" alt="Näyttökuva 2025-09-16 145029" src="https://github.com/user-attachments/assets/5305877e-ebd7-4284-92ec-683bb2aa1b6b" />


Varmistin statuksen komennolla ’sudo systemctl status apache2’.

<img width="898" height="265" alt="Näyttökuva 2025-09-16 145120" src="https://github.com/user-attachments/assets/1eb9e46c-f9da-40f3-b645-a4506e111f6d" />


Hain selaimesta IP-osoitteen ja Apachen sivu tuli esiin onnistuneesti. Korvasin sivun komennolla 'echo Hello world! |sudo tee /var/www/html/index.html'.

<img width="1278" height="502" alt="Näyttökuva 2025-09-16 145312" src="https://github.com/user-attachments/assets/89f23104-f98b-4630-a983-f510947bdac3" />
<img width="1276" height="306" alt="Näyttökuva 2025-09-16 145655" src="https://github.com/user-attachments/assets/85195116-9993-4cb9-b837-4f640294ca4c" />


Otin userdir-moduulin käyttöön ja käynnsitin palvelimen uudelleen komennoilla: ’sudo a2enmod userdir’ ja ’sudo service apache2 restart’.

<img width="897" height="113" alt="Näyttökuva 2025-09-16 145843" src="https://github.com/user-attachments/assets/d9fa4829-01f1-425e-801b-294ade5e5f42" />


Loin julkisen kansion.

<img width="900" height="149" alt="Näyttökuva 2025-09-16 145958" src="https://github.com/user-attachments/assets/eafc18e6-1cec-4d9b-a9ca-7ed8c2b0abe4" />


Avasin SSH-yhteyden ja asensin Micro:n.

<img width="903" height="335" alt="Näyttökuva 2025-09-16 150129" src="https://github.com/user-attachments/assets/37a703c1-f66b-4336-8fe8-2207a95bf7a7" />


Loin Microlla tiedoston index.html, johon tein lyhyen sivun.

<img width="904" height="400" alt="Näyttökuva 2025-09-16 151150" src="https://github.com/user-attachments/assets/fa98d048-4f61-41bc-9b8c-d2eacc3913dd" />


En saanut tätä näkyviin, joten menin /var/www/html/ kansioon ja muokkasin index.html tiedostoa micro:lla. Sain curl-komennolla muokatun sivun näkyviin terminaaliin ja tarkistin, että se näkyi myös selaimen kautta.

<img width="899" height="455" alt="Näyttökuva 2025-09-16 154751" src="https://github.com/user-attachments/assets/cd26147b-65f2-4098-9b24-96c256821e18" />
<img width="1275" height="441" alt="Näyttökuva 2025-09-16 154808" src="https://github.com/user-attachments/assets/7dc9cdab-fcce-4adc-87cf-97d07ef35570" />
