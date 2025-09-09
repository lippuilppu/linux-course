# H3 - Hello Web Server

Tehtävänanto: https://terokarvinen.com/linux-palvelimet/#h3-hello-web-server

## x) Tiivistelmät

### Name-based Virtual Host Support

-IP-pohjaiset virtual hostit tarvitsevat omat IP-osoitteet, nimi-pohjaiset virtual hostit pystyvät jakamaan saman IP-osoitteet.

-Apachen avulla hostien nimet pystytään konfiguroimaan oikeisiin IP-osoitteisiin.

### Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address

-Apachen avulla voidaan myös luoda uusia nimi-pohjaisia virtual hosteja.

-Tämä tehdään luomalla example.com.conf-tiedosto hakemistoon ja antamalla määritykset.

## a) Localhost

Asensin Apachen jo edellisellä tunnilla ja olin silloin varmistanut toimivuuden localhost-osoitteesta. Kokeilin varmuuden vuoksi uudelleen ja kaikki toimii yhä. 

## b) Lokin rivit

https://httpd.apache.org/docs/2.4/logs.html

Apachen lokit sain esille komennolla ’sudo tail /var/log/apache2/access.log.’

<img width="1035" height="359" alt="Näyttökuva 2025-09-09 130740" src="https://github.com/user-attachments/assets/cd3b989f-837d-409a-b35a-989884581794" />


Lokeista näkyy tiedot kaikista pyynnöistä mitä ollaan Apachella tehty. Esimerkiksi: 127.0.0.1 - - [03/Sep/2025:19:33:24 +0300] ”GET / HTTP/1.1” 200 10958 ”-” ”curl/8.14.1”

127.0.0.1 on käyttäjän IP-osoite, josta pyyntö on tehty. - - kertovat, että pyydettyä tietoa ei ole, mikä tässä tilanteessa on käyttäjätunnus. [03/Sep/2025:19:33:24 +0300] kertoo ajan ja paikan. ” ” sisällä on itse pyyntö ja sitä seuraavat numerot sisältävät serverin vastauksen pyyntöön.

## c) Etusivu uusiksi

https://github.com/johannaheinonen/johanna-test-repo/blob/main/linux-03092025.md
https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/

Käytin tunnilla käytettyjä ohjeita sekä Tero Karvisen ohjetta tässä tehtävässä. 

Tein uuden name based virtual hostin.

sudoedit /etc/apache2/sites-available/hattuexample.com.conf

Lisäsin sinne tarvittavat tiedot. 

<img width="1249" height="250" alt="Näyttökuva 2025-09-09 142734" src="https://github.com/user-attachments/assets/a90eed10-dad5-4597-9b78-2d55bd90cccd" />


Sitten lisäsin juuren hakemistoon, mihin lisäsin hieman tekstiä. Ajoin komennot ’sudo a2ensite hattu.example.com.conf’ ja ’sudo systemctl reload apache2’. Kun ajoin komentoa ’sudo systemctl reload apache2’, sen sijaan, että syöttäisin salasanan, painoin vahingossa ikkunan kiinni. Tämän jälkeen en saanut sivua toimimaan ja error.logissa luki näin.

<img width="1247" height="208" alt="Näyttökuva 2025-09-09 152736" src="https://github.com/user-attachments/assets/4a1ecc9f-e9f5-46f3-995d-caf991d85bf0" />
<img width="1280" height="632" alt="Näyttökuva 2025-09-09 161700" src="https://github.com/user-attachments/assets/80c43839-2e5a-40ab-a6bc-cda85644c882" />


Kokeilin ennen palautusta vielä uudelleen, mutta en saanut toimimaan. Palautan tämän tällaisena ja luon uuden virtuaalikoneen ennen seuraavaa tuntia.

## e) HTML5-sivu

https://terokarvinen.com/2012/short-html5-page/

Olin edellisessä tehtävässä luonut juuren hakemistoon, mihin lisäsin tekstiä. Menin takaisin kyseiseen tiedostoon ja muokkasin sinne HTML5-sivun.

<img width="823" height="156" alt="Näyttökuva 2025-09-09 164828" src="https://github.com/user-attachments/assets/240b9af2-3131-4311-91be-20afa5277ac2" />
<img width="819" height="512" alt="Näyttökuva 2025-09-09 170045" src="https://github.com/user-attachments/assets/6e6244d9-87af-4c72-8d2e-36fd898ac313" />


## f) 'curl -I' ja 'curl' -komennot

https://www.hostinger.com/tutorials/curl-command

’curl’ on komento, jolla siirretään dataa serveriltä toiselle. Esimerkiksi ’curl-L URL’ -komento seuraa uudelleenohjauksia syötetystä URL-osoitteesta ja ’curl-I URL’ antaa vain headerin syötetystä URL-osoitteesta.

<img width="797" height="410" alt="Näyttökuva 2025-09-09 171758" src="https://github.com/user-attachments/assets/08fd07f5-a77e-4dc2-8561-a6c955d9a7a7" />
<img width="1051" height="306" alt="Näyttökuva 2025-09-09 172008" src="https://github.com/user-attachments/assets/14f891a5-fa6f-447b-b9e3-cabb2c9593e0" />

