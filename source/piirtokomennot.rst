Piirtokomennot
==============
Jotta Racketillä voisi piirtää omia kuvia, ohjelman täytyy
ladata käyttöön uusi :term:`kirjasto` kirjoittamalla yläruutuun::

    (require 2htdp/image)

Kirjaston lataaminen ei pelkästään vielä tee mitään,
mutta se antaa käytettäväksi joukon uusia funktioita, kuten
:code:`circle`, :code:`ellipse`, :code:`line`, :code:`rectangle` ja :code:`triangle`.
Esimerkiksi punaisen ympyrän saa piirrettyä funktiokutsulla::

    (circle 20 "solid" "red")

.. image:: _static/circle-red.png

Toinen :term:`argumentti` voi olla joko :code:`"solid"`, :code:`"outline"`
tai luku 0 ja 255 välillä.

.. note::

    Laita :code:`require` funktion kutsu yläosaan ja paina :samp:`Run`,
    jotta saat piirtofunktiot käyttöön.

.. admonition:: Tehtävä

    Kokeile piirtää kaikilla yläpuolella mainituilla piirtofunktioilla.

    Kokeile myös mitä tapahtuu, jos käytät :code:`"solid"` sijasta numeroa.

Monimutkaisempia kuvia voi muodostaa asettamalla kuvia päällekäin
funktiolla :code:`overlay/offset`, jonka tulos on yksi yhdistetty kuva::

    (overlay/offset (circle 20 "solid" "red")
                    10 10
                    (circle 30 "solid" "blue"))

.. image:: _static/circle-red-blue.png

Kokeile miten toinen ja kolmas :term:`argumentti` vaikuttavat lopputulokseen!

.. admonition:: Tehtävä

    Osaatko paksuntaa reunaviivaa piirtämällä ympyröitä päällekäin tähän tapaan:

    .. image:: _static/thick-outline.png

.. admonition:: Tehtävä

    Valitse kaksi eri maata ja piirrä niiden liput Racketillä.

.. admonition:: Tehtävä

    Piirrä peruskomentoja käyttäen yksinkertainen kuva autosta
    käyttäen alussa mainittuja piirtokomentoja.

    Vinkki: kannattaa laittaa eri auton osat aluksi eri väreillä,
    jotta näet paremmin miten ne liikkuvat suhteessa toisiinsa.
    Monimutkaisempia kuvia kannattaa myös rakentaa ylempään ruutuun,
    jossa on helppo muokata aikaisempia käskyjä.
    Alemmassa ruudussa joudut joko kopioimaan ja liittämään vanhoja käskyjä,
    tai painamaan :kbd:`Ctrl-nuoli ylös`.


Kiinnostuitko?
--------------
Voit saada lisää värejä käyttöön laittamalla viimeiseksi argumentiksi
:term:`merkkijonon <merkkijono>` tilalle funktion :code:`make-color` kutsun.
Voit katsoa esimerkkejä kirjoittamalla :samp:`make-color`, laittamalla kursorin sen päälle,
ja painamalla :kbd:`F1`.

Katso myös mitä muita komentoja `image.rkt -kirjastosta <http://docs.racket-lang.org/teachpack/2htdpimage.html>`_
löytyy, sekä vilkaise `piirtokomentojen opasta <http://docs.racket-lang.org/teachpack/2htdpimage-guide.html>`_.
