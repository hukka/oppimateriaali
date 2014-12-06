Ensimmäiset askeleet
====================
Racketin ottaminen käyttöön
---------------------------
Tämän materiaalin ohjelmointiharjoitukset tehdään ohjelmassa :program:`DrRacket`.
Lataa omalle käyttöjärjestelmällesi sopiva versio `Racketin sivuilta <http://racket-lang.org/download/>`_.

Kun DrRacket avataan ensimmäisen kerran, ohjelmointikieltä ei ole vielä valittuna.
Tämän näkee alaosan punaisesta viestistä :samp:`No language chosen`.
Kieli valitaan ylhäältä valikosta :menuselection:`&Language --> Choose language`
tai painamalla :kbd:`Ctrl-l`. Klikkaa tekstiä :samp:`Beginning Student` ottaaksesi kielen käyttöön.
Kun olet sulkenut kielivalintaikkunan, paina vielä lopuksi ylhäältä :samp:`Run`-nappulaa.

Samasta valikosta voit myös vaihtaa kieltä myöhemmin, mikäli harjoitus niin vaatii.

Arvot ja funktiot
-----------------
DrRacketissä on kaksi erilaista aluetta.
Yläosaan kirjoitetaan kaikki tallennettava ja
alaosaan voi laittaa nopeita kokeiluja.
Yläosan koodi suoritetaan vasta, kun yläällä olevaa :samp:`Run`-nappulaa painetaan.
Alaosassa taas riittää, kun painaa :kbd:`Enter`.

Kokeile kirjoittaa alaosaan::

    42
    1/3
    0.3
    "Moi!"
    true
    false

Voit myös liittää kuvia leikepöydältä suoraan DrRackettiin.

.. hint::

    Saat kopioitua kuvan webbisivulta leikepöydälle klikkaamalla
    kuvaa oikealla hiiren näppäimellä (mäkeillä pitää klikata :kbd:`Ctrl` pohjassa)
    ja valitsemalla valikosta :samp:`Kopioi kuva` tai vastaava komento
    (komennon tarkka kirjoitusasu riippuu selaimesta).

    DrRacketissä voi liittää kuvia klikkaamalla oikealla hiiren näppäimellä
    ja valitsemalla :samp:`Paste`, painamalla :kbd:`Ctrl+v` (mäkeillä :kbd:`Cmd+v`)
    tai valikoiden kautta :menuselection:`Edit-->Paste`.

.. image:: _static/kitten.jpg

Nämä kaikki olivat :term:`arvoja <arvo>`.
DrRacket antaa aina jokaisen komennon jälkeen takaisin lopputuloksen arvon,
joka tässä tapauksessa on se mitä itse kirjoitit.

Kokeile seuraavaksi näitä komentoja::

    (+ 1 2)
    (/ 1 3)
    (string-length "Moi")
    (string-length "Heippa, kaikki!")
    (= 10 10)
    (> 1/3 0.5)

DrRacket ei enää anna takaisin täsmälleen samaa,
vaan se laskee annetun komennon arvon.
Ohjelmoinnissa tällasia komentoja sanotaan :term:`funktiokutsuiksi <funktiokutsu>`.
Ne alkavat aina sululla, jonka jälkeen tulee funktion nimi.
Seuraavaksi niille annetaan välilyönnillä toisistaan erotettuja argumentteja,
eli jotain tietoja, joita funktio käyttää.
Viimeisen argumentin jälkeen tulee sulkeva sulku.

Argumentit ovat yksinkertaisimmillaan suoraan kirjoitettuja arvoja.
Mutta koska funktiokutsujen lopputulos on aina arvo,
argumenteiksi voi laittaa myös muita funktiokutsuja, jopa saman funktion kutsuja!
Esimerkiksi jakolaskufunktion argumenttina voi olla toinen jakolasku.

.. note::

    Saat apua kaikista funktioista laittamalla kursorin funktion
    nimen päälle ja painamalla :kbd:`F1`.
    Myös osa nimestä riittää, jos et esimerkiksi muista funktion koko nimeä.
    Jos käytät kannettavaa tietokonetta, voi olla että joudut painamaan myös
    :kbd:`Fn`-näppäintä saadaksesi F1:n.

Arvot ovat aina jotakin :term:`tyyppiä <tyyppi>`.
Ylempänä olevat esimerkit olivat :term:`numeroita <numero>`,
:term:`merkkijonoja <merkkijono>` eli tekstiä,
:term:`booleaneja <boolean>` eli loogisen päättelyn vastaus kyllä tai ei (tosi ja epätosi)
ja kuvia.
Huomaa, että numero :samp:`42` ja merkkijono :samp:`"42"` ovat eri asioita!
Ensimmäinen on matemaattinen käsite, toinen kaksi :term:`merkkiä <merkki>`.

Funktioiden argumenttien pitää olla tiettyä tyyppiä.
Esimerkiksi koska :code:`+` käsittelee numeroita,
mutta ei tiedä mitä tehdä tekstille,
:code:`(+ 1 2)` toimii, mutta :code:`(+ "1" "2")` ei.

Rationaaliluvut voidaan ilmoittaa Racketissä kahdella lailla.
Oletuksena DrRacket käyttää desimaalimuotoa,
jonka toistuvan osuuden päälle piirretään viiva
(eli Racket muistaa rationaaliluvut tarkasti).
Samasta valikosta, mistä käytetty kieli valitaan,
voi valita myös rationaalimuodon (:menuselection:`&Language --> Choose language --> Show details --> Fraction style --> Mixed fractions`).
