Mitä tehdä, jos DrRacket antaa virheilmoituksia
===============================================

.. contents:: :local:

X: this function is not defined
-------------------------------
Virheen ensimmäinen sana riippuu siitä,
minkä nimistä funktiota olet yrittänyt kutsua.
Virhe voi johtua kahdesta syystä:
joko olet kirjoittanut funktion nimen väärin,
tai olet unohtanut käyttää :code:`require`-funktiota ohjelman alussa.
Esimerkiksi DrRacket ei löydä piirtokomentoja ennenkuin ohjelmassa on
:code:`(require 2htdp/image)`.

Jos kutsut omaa funktiotasi,
tarkista myös että olet kirjoittanut funktion nimen oikein määritelmässä!
DrRacket ei ymmärrä mitkä sanat ovat oikeaa suomea (tai englantia),
vaan tarkastaa ainoastaan että määritelmässä annettu ja kutsussa käytetty nimi täsmäävät.


define: expected only one expression after the variable name X, but found 1 extra part
--------------------------------------------------------------------------------------------
Tämä virhe toi tulla määritellessä funktioita, jos unohdit laittaa sulut
funktion ja parametrien nimien ympärille.
Racket luulee, että yrität nimetä vakiota, mutta hämääntyy kun nimen jälkeen tuleekin monta asiaa.

Esimerkiksi

::

    (define lisääjä luku
      (+ luku 1))

aiheuttaa tämän virheilmoituksen.
DrRacket myös maalaa punaisella ylimääräiset osat, yhden parametrin tapauksessa
funktion sisällön. Oikein kirjoitettu funktio olisi

::

    (define (lisääjä luku)
      (+ luku 1))


function call: expected a function after the open parenthesis, but found a part
-------------------------------------------------------------------------------
Tässä quote:`open parenthesis` ei tarkoita ylimääräistä tai sulkematonta sulkua,
vaan yleensä aloittavaa sulkua.
Racketissä aloittavan sulun jälkeen pitää tulla aina funktion nimi.
Esimerikssi funktiokutsussa

::

    ((circle 10 "solid" "red"))

Ongelmana on kutsun ympärillä olevat ylimääräiset sulut.
Oikein kirjoitettu kutsu on

::

    ((circle 10 "solid" "red"))

Monimutkaisemmassa esimerkissä

::

    (overlay/offset
     (overlay/offset ((circle 10 "solid" "red") 10 10 (circle 10 "solid" "red"))
                     20 20
                     (rectangle 20 40 "solid" "blue")))

Ongelmana on väärään paikkaan lipsahtanut alkava sulku,
ja aivan ohjelman loppuun tullut ylimääräinen sulku.
Jos annat Racketin sisentää koodisi automaattisesti, kuten esimerkissä,
kolmas ja neljäs rivi sisentyvät samaan kohtaan kuin ensimmäinen circle-kutsu.
Tämä tarkoittaa, että DrRacket pitää näitä kaikkia sisemmän overlay/offsetin argumentteina.

Asian voi myös varmistaa viemällä kursori viimeisen rivin loppuun,
jolloin DrRacket maalaa koko koodin harmaalla.
Tämä tarkoittaa, että aivan ensimmäinen alkava ja viimeinen sulkeva sulku vastaavat toisiaan
(eli kaikille muille alkaville suluille on löytynyt pariksi aiempi sulkeva sulku).
Jos kursoria vie nyt yhden kirjaimen vasemmalle, toiseksi viimeiseen sulkevaan sulkuun,
DrRacket maalaa koko sisemmän kutsun.
Eli ulommalla overlay/offsetillä on liian vähän argumentteja,
ja sisemmällä liian paljon.

Itse virheilmoitus tulee ensimmäistä circleä edeltävästä tuplasulusta,
joista toinen pitää poistaa.
Samoin aivan viimeinen sulkeva sulku pitää poistaa,
jotta sulkuja olisi oikea määrä.
Jos nyt maalaat hiirellä koko koodin ja painat :kbd:`tab`-näppäintä
(:kbd:`Q`-näppäimen vasemmalla puolen),
DrRacket sisentää koodin uudelleen::

    (overlay/offset
     (overlay/offset (circle 10 "solid" "red") 10 10 (circle 10 "solid" "red"))
     20 20
     (rectangle 20 40 "solid" "blue"))

Nyt kolmas ja neljäs rivi rivittyvät sisemmän overlay/offsetin tasolle,
eli ne kaikki ovat argumentteja ulommalle overlay/offsetille.


define: expected only one expression for the function body, but found 1 extra part
----------------------------------------------------------------------------------
Funktiomääritelmässäsi on liikaa osia, esimerkiksi::

    (define (lisääjä x)
      (+ x 1)
      (- x 1))

Funktio yrittää siis tehdä kahta asiaa, sekä lisätä että vähentää annetusta parametrista yhden.
Virheen korjataksesi sinun täytyy poistaa jompikumpi,
tai ehkä tarkoituksesi oli antaa nämä vielä jollekin kolmannelle funktiolle argumenteiksi.
