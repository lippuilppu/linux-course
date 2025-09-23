# H5 – Nimekäs

Tehtävänanto: https://terokarvinen.com/linux-palvelimet/#h5-nimekas

Hyödynsin tässä tehtävässä Susanna Lehdon blogipostausta: Teoriasta käytäntöön pilvipalvelimen avulla (h4). 

## a) Nimi

### NameCheap

Päätin vuokrata nimen NameCheapin kautta. Sitä suositeltiin tehtävänannon vinkeissä ja sitä käytettiin blogipostauksessa. 

<img width="1897" height="840" alt="Näyttökuva 2025-09-23 112206" src="https://github.com/user-attachments/assets/dd091d66-12fc-4de2-af77-e1b57ed426f8" />

Halusin vuokrata vain yhden nimen mahdollisimman halvalla hinnalla, joten valitsin täsmentävän hakusanan ’$2 or less’.

<img width="1078" height="915" alt="Näyttökuva 2025-09-23 111749" src="https://github.com/user-attachments/assets/34e0b7ea-1a6c-4f53-86fe-0f0dd8fad182" />

Päädyin ottamaan nimen oinonen.website, joka oli 0,83€ ja tilauksen uusimisen jälkeen 11,98$ vuodessa.

<img width="1056" height="358" alt="Näyttökuva 2025-09-23 111932" src="https://github.com/user-attachments/assets/42c6b401-c97e-4250-8b8e-02b14be50193" />
<img width="1312" height="791" alt="Näyttökuva 2025-09-23 112548" src="https://github.com/user-attachments/assets/747691e5-61c3-4653-bec7-d0def5108064" />

Jotta pystyisisin vahvistamaan tilauksen, minun piti luoda tili.

<img width="1354" height="893" alt="Näyttökuva 2025-09-23 112722" src="https://github.com/user-attachments/assets/17935392-5b6a-40e5-a625-dc44f49647fc" />

Tein tilin käyttäen omia henkilökohtaisia tietoja ja tilauksen loppusummaksi tuli huima 1,18$ eli 1€.

<img width="1242" height="547" alt="Näyttökuva 2025-09-23 113140" src="https://github.com/user-attachments/assets/f7a6491f-0bcd-4330-acb9-a8d54a7563ec" />

### Nimen yhdistäminen vuokrattuun virtuaalipalvelimeen

Valitsin valikosta vaihtoehdon ’Domain List’, josta löysin juuri vuokraamani nimen. Siitä valitsin ’Advanced DNS’.

<img width="1445" height="725" alt="Näyttökuva 2025-09-23 114350" src="https://github.com/user-attachments/assets/d32a0da1-1da0-4100-b85e-4e4f33833fab" />

’Host records’-listalla oli valmiiksi lisättyjä tiedostoja, jotka poistin. Loin uudet tiedostot, joiden ’value’-osioon laitoin virtuaalipalvelimeni IP-osoitteen.

<img width="1142" height="724" alt="Näyttökuva 2025-09-23 122856" src="https://github.com/user-attachments/assets/9294e9c5-f450-43aa-a5f6-868ec255ff0a" />

Kokeilin hakea uutta nimeä sekä IP-osoitetta selaimesta:

<img width="988" height="321" alt="Näyttökuva 2025-09-23 153744" src="https://github.com/user-attachments/assets/709a3c86-d38d-417d-8bfc-79df1b661369" />
<img width="1274" height="346" alt="Näyttökuva 2025-09-23 153913" src="https://github.com/user-attachments/assets/c48624fc-a177-4882-84a1-ee9ce03cd346" />
<img width="1278" height="345" alt="Näyttökuva 2025-09-23 153924" src="https://github.com/user-attachments/assets/cc6807c2-6620-42c6-96ac-7372887d366f" />

## b) Alidomain

Avasin virtuaalikoneen ja ensimmäiseksi päivitin kaiken. Edellisellä tunnilla mainittiin, että komentoa ’sudo apt-get dist-upgrade’ kannattaa käyttää, joten mielenkiinnosta ajoin sen ensimmäiseksi. Tässä meni ~5 minuuttia. Sen jälkeen ajoin ’sudo apt-get update’ ja ’sudo apt-get upgrade’-komennot.

<img width="799" height="453" alt="Näyttökuva 2025-09-23 124231" src="https://github.com/user-attachments/assets/89195962-c408-4dd9-adb4-2e9552814022" />

Loin uuden sivun nimeltä linuxkurssi.example.com.

<img width="987" height="248" alt="Näyttökuva 2025-09-23 144608" src="https://github.com/user-attachments/assets/c6db46e5-97e9-4c56-8c9d-c00817be96ad" />

## c) ’host’ ja ’dig’-komennot

Tässä tehtävässä auttoi vanhan kunnon GeeksForGeeks.


’host’-komennolla haetaan tietyn domainin IP-osoite tai toisinpäin. ’dig’, eli ’Domain Information Groper’, on komento, jolla haetaan tietoa DNS-nimipalvelimista.

’dig’-komennon asensin komennolla ’sudo apt-get install dnsutils’.

<img width="989" height="397" alt="Näyttökuva 2025-09-23 154700" src="https://github.com/user-attachments/assets/89d67c19-ba64-4414-8624-7adb878e9214" />

Kokeilin molempia komentoja oinonen.websiten kanssa.

<img width="990" height="418" alt="Näyttökuva 2025-09-23 154822" src="https://github.com/user-attachments/assets/51acc83f-e25a-4a8a-b63d-bb7bce29f63c" />

<img width="988" height="155" alt="Näyttökuva 2025-09-23 155157" src="https://github.com/user-attachments/assets/81223a11-377a-4ae2-85cb-6ba53363b918" />

## Ongelmat

Minulla loppui aika kesken, jonka takia en saanut tehtävää b ja c valmiiksi. Apachen kanssa oli myös ongelmia, jotka yritän saada ratkottua myöhemmin. 

## Lähteet:

https://terokarvinen.com/linux-palvelimet/#h5-nimekas

https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/

https://www.geeksforgeeks.org/linux-unix/host-command-in-linux-with-examples/

https://www.geeksforgeeks.org/linux-unix/dig-command-in-linux-with-examples/

