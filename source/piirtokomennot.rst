Piirtokomennot
==============
Jotta Racketillä voisi piirtää omia kuvia, ohjelman täytyy
ladata käyttöön uusi :term:`kirjasto`::

    (require 2htdp/image)

Kirjaston lataaminen tuo käytettäväksi joukon uusia funktioita, kuten
:code:`circle`, :code:`ellipse`, :code:`line`, :code:`rectangle` ja :code:`triangle`.
Esimerkiksi punaisen ympyrän saa piirrettyä funktiokutsulla::

    (circle 20 "solid" "red")

.. image:: _static/circle-red.png

Toinen :term:`parametri` voi olla joko :code:`"solid"`, :code:`"outline"`
tai luku 0 ja 255 välillä.
Kokeile mitä nämä eri vaihtoehdot tekevät!

Monimutkaisempia kuvia voi muodostaa asettamalla kuvia päällekäin
funktiolla::

    (overlay/offset (circle 20 "solid" "red")
                    10 10
                    (circle 20 "solid" "blue"))

.. image:: _static/circle-red-blue.png

Kokeile miten toinen ja kolmas :term:`parametri` vaikuttavat lopputulokseen!
Entä mitä tekee funktio :code:`overlay/xy` samoilla parametreillä?


.. admonition:: Tehtävä

    Piirrä peruskomentoja käyttäen yksinkertainen kuva autosta.

.. todo:: Olisiko hyvä olla kuva esimerkkiautosta?

.. admonition:: Tehtävä

    Valitse kaksi eri maata ja piirrä niiden liput Racketillä.


Kiinnostuitko?
--------------

Voit saada lisää värejä käyttöön laittamalla viimeiseksi parametriksi
:term:`merkkijono`\n tilalle funktiokutsun :code:`make-color`.
Katso myös mitä muita komentoja `image.rkt -kirjastosta <http://docs.racket-lang.org/teachpack/2htdpimage.html>`_
löytyy, sekä vilkaise `piirtokomentojen opasta <http://docs.racket-lang.org/teachpack/2htdpimage-guide.html>`_.
