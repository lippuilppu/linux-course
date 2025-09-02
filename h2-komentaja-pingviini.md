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

Tässä tehtävässä pyydettiin listaamaan ’Important directories’-osiossa olevat kansiot ja esittelemään niissä olevan tiedoston tai kansion. Kyseiset kansiot ovat /, /home/, /home/ilona/, /etc/, /media/ ja /var/log/. En tiedä ymmärrsinkö ohjeistuksen "kuvaava esimerkki" oikein, joten toivon, että seuraavat esimerkit kelpaavat.

### / eli juurihakemisto

Koitin mennä hakemistoihin ja avata kansiot ulkomuistista, joten meni pari yritystä ennen kuin pääsin juurihakemistoon ja siellä olevaan dev-hakemistoon. Menin hakemistoon komennolla 'cd /', varmistin sijainnin komennolla 'pwd' ja komennolla 'ls /' sain esille hakemiston.

<img width="803" height="170" alt="2juuri" src="https://github.com/user-attachments/assets/bb461c0a-bc5a-4f67-b7d6-ca626b451c99" />


Samoilla komennoilla avasin juurihakemistossa olevan dev-hakemiston.

<img width="958" height="417" alt="Näyttökuva 2025-09-02 151140" src="https://github.com/user-attachments/assets/0f6a5113-ea3c-4441-87e8-5b4d5a9a954d" />


### /home/

Juurihakemistosta siiryin suoraan /home/-hakemistoon.

<img width="958" height="114" alt="Näyttökuva 2025-09-02 153836" src="https://github.com/user-attachments/assets/dfbfdbb4-b93d-4f5e-9eaa-0ebaddab303f" />


### /home/ilona/

Käytin samoja komentoja kuin ensimmäisessä, mutta en saanut näkyville mitään. Oletan tämän johtuvan siitä, että en ole itse luonut hakemistoon mitään.

<img width="960" height="111" alt="Näyttökuva 2025-09-02 152409" src="https://github.com/user-attachments/assets/5cef5468-83fd-41aa-9103-ef87d0658241" />
<img width="958" height="156" alt="Näyttökuva 2025-09-02 153128" src="https://github.com/user-attachments/assets/5b16bca9-1f08-4633-a5cb-ad8092897832" />


### /etc/

Tämä oli huomattavasti isompi hakemisto. Kokeilin aluksi avata modulesia, mutta se ei onnistunut. /etc/lynx sen sijaan onnistui ja kurkkasin, mitä sen sisällä on.

<img width="958" height="327" alt="Näyttökuva 2025-09-02 154330" src="https://github.com/user-attachments/assets/409a9c60-b3fc-4cdb-9948-eca219e9f0fd" />
<img width="959" height="114" alt="Näyttökuva 2025-09-02 154258" src="https://github.com/user-attachments/assets/fb5204ca-49d4-4eb1-a059-54ef56a6eb1f" />


### /media/

Tässäkään hakemistossa ei näkynyt mitään. Oletan sen johtuvan siitä, että siellä ei ole mitään tai, että minulla ei ole tarvittavia oikeuksia.

<img width="959" height="152" alt="Näyttökuva 2025-09-02 154709" src="https://github.com/user-attachments/assets/24b2dd5f-e0a3-47fd-b578-2e488535f471" />


### /var/log/

<img width="958" height="186" alt="Näyttökuva 2025-09-02 155056" src="https://github.com/user-attachments/assets/8592de5f-64d3-452b-8f8b-cb434935498c" />


Kokeilin avata hakemistossa olevaa README-tiedostoa, mutta en saanut sitä auki. Googlettamalla sain selville, että 'cat'-komento saattaisi toimia. Sain kuitenkin seuraavanlaisen huomautuksen.

<img width="960" height="513" alt="Näyttökuva 2025-09-02 155509" src="https://github.com/user-attachments/assets/75cce81e-5eb3-4e1e-95db-7de805147c1d" />


Kokeilin aptia ja sen avaamisessa onnistuin.

<img width="961" height="77" alt="Näyttökuva 2025-09-02 155603" src="https://github.com/user-attachments/assets/873130ca-e558-4dbc-b3c0-0db482be557f" />


## d) The Friendly M

Aloitin syöttämällä ’man grep’ terminaaliin ja pitkä lista ilmestyi, jossa selitettiin grepin käyttö kokonaisuudessa. Löysin saman ohjeen googlesta, jota käytin lukemisen helpottamiseksi: https://man7.org/linux/man-pages/man1/grep.1.html. 

Päädyin lopuksi kuitenkin hakemaan esimerkkejä täältä: https://www.geeksforgeeks.org/linux-unix/grep-command-in-unixlinux/

Ajattelin aluksi kokeilla komentoja itse, mutta edellisen tehtävän jälkeen en koe saavani hyviä tuloksia.

Sanan hakeminen tiedostosta: grep "python" notes.txt

Sanan hakeminen tiedostosta, jossa on isoja tai pieniä kirjaimia tai molempia: grep -i "UNix" geekfile.txt

Näytä vain täsmäävä string, eikä koko riviä: grep -o "unix" geekfile.txt

## e) Pipe

Tämä oli uusi asia, joten googletin sen ja käytin tätä sivua tämän tehtävän tekemisessä: https://www.geeksforgeeks.org/linux-unix/piping-in-unix-or-linux/. Pipe eli | merkkiä käytetään kahden komennon yhdistämisessä. Esimerkiksi ’more’-komennon kanssa

Esimerkki: ls -l | more

![Add file: Upload](2pipemore.png)


## f) Rauta

Kokeilin suoraan syöttää komennon ’sudo lshw -short -sanitize’, mutta terminaali ei löytänyt komentoa ’lshw’, joten latasin sen ja suoritin komennon uudelleen.

![Add file: Upload](2rauta.png)

![Add file: Upload](2rautatulos.png)


https://linuxhandbook.com/lshw-command/. 

’sudo lshw’ antaa kaiken tiedon koneen raudasta ja ’-short -sanitize’ muotoilee syötetyn tiedon. Komento listasi laitteet ja niiden luokan sekä lyhyen kuvauksen. Listassa oli myös H/W path, jota en entuudesta tuntenut. Löysin foorumilta vuodelta 2001 hyvän selityksen H/W pathille: https://community.hpe.com/t5/hpe-9000-and-hpe-e3000-servers/h-w-path/td-p/2555697. 

![Add file: Upload](2hwpath.png)


En itse valitettavasti osaa ainakaan tässä vaiheessa selittää ja analysoida listausta paremmin.
