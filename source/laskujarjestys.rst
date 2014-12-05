Laskujärjestys
==============

Peruslaskut Racketillä
----------------------

Racketissä kaikki funktiokutsut, eli komennot, kirjoitetaan sulkujen sisään.
Ensimmäiseksi tulee aina funktion nimi ja sen jälkeen välilyönnillä erotellut :term:`argumentit <argumentti>`,
eli funktiolle annettavat arvot.

.. todo::

    "yhdistä viivalla"-tehtävä bootstrapin tapaan ja esimerkit pois

Esimerkiksi :math:`2+3` kirjoitetaan :code:`(+ 2 3)`.
Kertolaskussa käytetään symbolia :code:`*` ja
jakolaskussa :code:`/`.

.. admonition:: Tehtävä

    Laske Racketillä:

    .. math::

        \begin{gather}
        42 + 9 \\
        3 - 10 \\
        6 · 7 \\
        121 : 11 \\
        \end{gather}

.. admonition:: Tehtävä

    Keksitkö miten voisit laskea Racketillä

    .. math::

        \begin{gather}
        (8 - 2) : 3 \\
        27 : (3 · 3) \\
        18 - 5 + 7 \\
        5 + 15 : 3 \\
        (5 + 15) : 3 \\
        7 · 8 - 26 \\
        20 : 5 · 4 \\
        \end{gather}

Moniosaiset laskut Racketillä
-----------------------------
Edellisessä tehtävässä funktion :term:`argumenttina <argumentti>`
oli aina yksi luku ja yksi sellainen funktiokutsu, jonka lopputulos oli luku.

Esimerkiksi :math:`5 + 15:3` kirjoitetaan :code:`(+ 5 (/ 15 3))`
ja :math:`10 : (5 - 3)` :code:`(/ 10 (- 5 3))`.

Yleisesti ottaen minkä tahansa luvun voi korvata funktiokutsulla.
Funktiokutsuja voi olla sisäkkäin miten monta tahansa.

.. admonition:: Tehtävä

    Laske Racketillä

    .. math::
        \begin{gather}
        (14 + 16) · (20 : 4) \\
        (9 - 3) · (9 + 3) \\
        108 - 8 · (2 + 8) \\
        1 + 2 + 3 + 4 \\
        36 : 9 + 2 · 3 + 15 : 5 \\
        1 - 2 * (9 : 3) \\
        \end{gather}

.. todo::

    Minne kasata opettajalle huomioitavia asioita, kuten (+ 1 2 3 4) tässä?
    Kysymysmerkki-popup vinkkeihin, vastaus-popup vastauksiin


.. admonition:: Tehtävä

    Laske:

    .. math::
        \begin{gather}
        [29 - 3 · (12 - 9)] : 5 \\
        15 - (10 - [12 - (4 + 6)]) \\
        ([25 - (9 + 6)]· 4 - 10) : (36 : 12)
        \end{gather}


.. admonition:: Tehtävä

    Kokeile mitä tapahtuu, jos jätät alkavan sulun pois ennen komentoa.
    Entä lopettavan?
    Tai jos kirjoitat funktion nimen väärin tai annat liian vähän
    tai väärän tyyppisiä argumentteja?

    Virheellisien komentojen kokeilu on hyödyllistä,
    sillä virheitä sattuu kaikille ohjelmoijille.
    Kun tiedät mistä virheestä tapahtuu mitäkin,
    osaat myöhemmin keksiä nopeammin mistä vahingossa tehty virhe johtuu.

Kiinnostuitko?
--------------
Muita matikkafunktioita F1:llä
