Salasanojen vahvuus
===================

::

    (require (planet mbenkard/mulkrypt:1:2/cubehash))

    (cubehash-128 #"lyhyt")
    (cubehash-128 #"salasana")
    (cubehash-128 #"pitkäsalasana")

.. note::

    planet-funktio hakee paketin `Racketin käyttäjien tekemien
    kirjastojen <http://planet.racket-lang.org/>`_ joukosta.


Tavut
-----
On erilaisia lukujärjestelmiä. Racketissä voidaan kirjoittaa numeroita
binäärinä, eli kaksikantaisena, ja heksadesimaalina, eli 16-kantaisena
laittamalla lukujen eteen liitteet :code:`#b` ja :code:`#x`.
Heksadesimaalissa yhdeksää suuremmat numerot esitetään kirjaimilla
a:sta f:n.

Tietokoneet tallentavat kaiken tietonsa sisäisesti binäärilukuina,
jonka yksittäisiä osia sanotaan biteiksi. Yleensä muisti on jaoteltu
yhden tai useamman :term:`tavun <tavu>`, eli kahdeksan bitin osiin.

Yksi tavu voi siis sisältää lukuja väliltä
:code:`#b00000000`-:code:`#b11111111`, eli 0-255.
Heksadesimaalina tavut vaativat vain kaksi merkkiä.
Heksat sisältävät siis neljän bitin verran tietoa.

Merkistökoodaukset
------------------
Koska kaikki tietokoneen sisällä oleva tieto on tavuihin jaettuja bittejä,
myös teksti täytyy esittää jollain lailla binäärinumeroina.
Sopimusta mikä numero vastaa mitäkin kirjainta sanotaan
:term:`merkistökoodaukseksi <merkistökoodaus`.

Vanhin tietokoneissa käytetty merkistökoodaus on ASCII.
Siinä jokaista kirjainta, kuten myös erikoismerkkiä,
vastasi seitsemän bittiä.
Siihen mahtuu englanninkieliseen tekstiin riittävä määrä kirjaimia,
mutta ei ääkkösiä.
Muita kieliä varten käyttöön otettiin kahdeksas bitti,
mutta yli 127:n menevät numerot tarkoittivat eri kielissä eri kirjaimia.


Hajautusalgoritmi
-----------------
eli hash-funktio.

Muuttaa minkä tahansa määrän tavuja ennaltamäärätyksi määräksi tavuja.

Pieni muutos syötteessä muuttaa ulostuloa paljon.

Hyvin hankala laskea toiseen suuntaan, eli mikä on ollut syöte jos
tiedetään ulostulo.

Käytetään salasanojen tallentamiseen,
sillä jos salasanatiedosto varastetaan,
varkaan on hyvin hankala selvittää käytettyjä salasanoja
ja kokeilla samoja myös muihin paikkoihin.

Suurin mahdollinen 128-bittinen numero on binäärinä 128 ykköstä,
eli heksadesimaalina :math:`128:4` f:ä:
:code:`#xffffffffffffffffffffffffffffffff`.
Desimaalijärjestelmässä luku on 340282366920938463463374607431768211455.

Brute force
-----------
Kokeillaan yksi kerrallaan kaikkia mahdollisia salasanoja.

Sanasto
-------
Kokeillaan valmiissa sanastossa olevia, yleisesti käytettyjä sanoja.

Sanasto muutoksilla
-------------------
Kokeillaan yhdistää sanoja, ja muuttaa niitä tietyillä yleisillä säännöillä,
kuten vaihtamalla A-kirjaimet numeroksi 4, tai E 3:ksi.
