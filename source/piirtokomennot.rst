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

.. admonition:: Tehtävä

    Kokeile piirtää kaikilla yläpuolella mainituilla piirtofunktioilla.

    Kokeile myös mitä tapahtuu, jos käytät :code:`"solid"` sijasta numeroa.

Monimutkaisempia kuvia voi muodostaa asettamalla kuvia päällekäin
funktiolla::

    (overlay/offset (circle 20 "solid" "red")
                    10 10
                    (circle 30 "solid" "blue"))

.. image:: _static/circle-red-blue.png

.. admonition:: Tehtävä

    Osaatko paksuntaa reunaviivaa piirtämällä ympyröitä päällekäin.

.. image:: thick-outline.png

Kokeile miten toinen ja kolmas :term:`argumentti` vaikuttaa lopputulokseen!

.. admonition:: Tehtävä

    Valitse kaksi eri maata ja piirrä niiden liput Racketillä.

.. admonition:: Tehtävä

    Piirrä peruskomentoja käyttäen yksinkertainen kuva autosta
    käyttäen alussa mainittuja piirtokomentoja.
    Vinkkinä kannattaa laittaa eri auton osat eri väreillä,
    jotta näet paremmin miten ne liikkuvat.


Kiinnostuitko?
--------------
Voit saada lisää värejä käyttöön laittamalla viimeiseksi argumentiksi
:term:`merkkijonon <merkkijono>` tilalle funktion :code:`make-color` kutsun.
Katso myös mitä muita komentoja `image.rkt -kirjastosta <http://docs.racket-lang.org/teachpack/2htdpimage.html>`_
löytyy, sekä vilkaise `piirtokomentojen opasta <http://docs.racket-lang.org/teachpack/2htdpimage-guide.html>`_.
