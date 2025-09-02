# H2 Komentaja Pingviini

Tehtävänanto: https://terokarvinen.com/linux-palvelimet/#h2-komentaja-pingviini

## x) Tiivistys

Tein tiivistyksen sivusta: https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited.

-Komentorivin avulla päästään käsiksi hakemistoihin ja käsitellään tiedostoja.

-Komentoja käyttäen siirrytään hakemistosta toiseen. Tekstieditoreja voidaan käyttää tiedostojen käsittelyssä.

-Tärkeimmät ja keskeisimmät hakemistot ovat /, /home/, /home/ilona/, /etc/, /media/ ja /var/log/.

-Valtaosa toiminnoista tehdään ’Minimum Privilege’ käytännöllä. Korkeammalla oikeudella tehdään esim. sovellusten asennuksia ja poistoja, luodaan käyttäjiä ja hallinnoidaan oikeuksia.

-Kaikkea ei tarvitse muistaa. Terminaalissa on help-menu ja komentoterminaali osaa tarvittaessa näyttää miten komennon voi kirjoittaa loppuun tai jopa täyttää sen automaattisesti.

## a) Micron asennus

Aloitin harjoituksen avaamalla virtuaalikoneen ja ajamalla komennon sudo apt-get update. Micron asennuksen tein noudattamalla Tero Karvisen ohjeistuksia sivulta: https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited.

![Add file: Upload](2paivitys.png)

Vaikka tarvittavan paketin nimi oli tiedossa, kokeilin silti huvikseni komentoa ’Apt-cache search micro’. Terminaaliin ilmestyi pitkä lista, josta löysin halutun sovelluksen. Asensin sen käyttämällä komentoa ’sudo apt-get -y install micro’.

![Add file: Upload](2searchmicro.png)

Tämän jälkeen ajoin komennon ’dpkg - - listfiles micro’.

![Add file: Upload](2dpkg.png)

Varmistin sovelluksen toimivuuden komennolla ’micro’.

![Add file: Upload](2micro.png)

## b) Komentoriviohjelmat

Saman ohjeen lopussa oli esimerkki apt-get komennosta, jolla pystyi lataamaan useamman ohjelman kerralla.

Esimerkki: $ sudo apt-get -y install krita blender vlc tree httpie curl tmux python3-py

Ohjelmia etsiessä unohdin käyttää edellistä komentoa ja päädyin lataamaan kaikki yksittäin komennolla ’sudo apt-get -y install’. Pääsijaisesti etsin jotain pientä ja hauskaa, jolla ei ollut isompaa käyttötarkoitusta. Päädyin lataamaan nämä kolme nsnake, sl, cmatrix.

![Add file: Upload](2nsnakegameover.png)

![Add file: Upload](2sl.png)

![Add file: Upload](2cmatrix.png)

## c) FHS

Tässä tehtävässä pyydettiin listaamaan ’Important directories’-osiossa olevat kansiot ja esittelemään niissä olevan tiedoston tai kansion. Kyseiset kansiot ovat /, /home/, /home/ilona/, /etc/, /media/ ja /var/log/.

## d) The Friendly M

Aloitin syöttämällä ’man grep’ terminaaliin ja pitkä lista ilmestyi, jossa selitettiin grepin käyttö kokonaisuudessa. Löysin saman ohjeen googlesta, jota käytin lukemisen helpottamiseksi: https://man7.org/linux/man-pages/man1/grep.1.html. 

## e) Pipe

Tämä oli uusi asia, joten googletin sen ja käytin tätä sivua tämän tehtävän tekemisessä: https://www.geeksforgeeks.org/linux-unix/piping-in-unix-or-linux/. Pipe eli | merkkiä käytetään kahden komennon yhdistämisessä. Esimerkiksi ’more’-komennon kanssa

Esimerkki: ls -l | more

![Add file: Upload](2pipemore.png)

## e) Rauta

Kokeilin suoraan syöttää komennon ’sudo lshw -short -sanitize’, mutta terminaali ei löytänyt komentoa ’lshw’, joten latasin sen ja suoritin komennon uudelleen.

![Add file: Upload](2rauta.png)

![Add file: Upload](2rautatulos.png)

https://linuxhandbook.com/lshw-command/. 

’sudo lshw’ antaa kaiken tiedon koneen raudasta ja ’-short -sanitize’ muotoilee syötetyn tiedon. Komento listasi laitteet ja niiden luokan sekä lyhyen kuvauksen. Listassa oli myös H/W path, jota en entuudesta tuntenut. Löysin foorumilta vuodelta 2001 hyvän selityksen H/W pathille: https://community.hpe.com/t5/hpe-9000-and-hpe-e3000-servers/h-w-path/td-p/2555697. 

![Add file: Upload](2hwpath.png)
