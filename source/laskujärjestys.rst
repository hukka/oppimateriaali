Laskujärjestys
==============

Peruslaskut Racketillä
----------------------

Racketissä kaikki funktiokutsut, eli komennot, kirjoitetaan sulkujen sisään.
Ensimmäiseksi tulee aina funktion nimi ja sen jälkeen välilyönnillä erotellut argumentit,
eli funktiolle annettavat arvot.

Esimerkiksi :math:`2+3` kirjoitetaan :code:`(+ 2 3)`.

1. tehtävä
**********
Laske Racketillä:

.. math::

    \begin{gather}
    18 - 5 + 7 \\
    5 + 15 : 3 \\
    7 · 8 - 26 \\
    20 : 5 · 4 \\
    (8 - 2) : 3 \\
    27 : (3 · 3) \\
    \end{gather}

Moniosaiset laskut Racketillä
-----------------------------
Funktion parametri voi olla myös toinen funktiokutsu, jonka lopputulos on luku.

Esimerkiksi :math:`5 + 15:3` kirjoitetaan :code:`(+ 5 (/ 15 3))`.

2. tehtävä
**********
Laske:

.. math::
    \begin{gather}
    (14 + 16) · (20 : 4) \\
    (9 - 3) · (9 + 3) \\
    108 - 8 · (2 + 8) \\
    36 : 9 + 2 · 3 - 15 : 5 \\
    1 + 2 + 3 + 4
    \end{gather}

.. todo::

    Minne kasata opettajalle huomioitavia asioita, kuten (+ 1 2 3 4) tässä?


3. tehtävä
**********
Laske:

.. math::
    \begin{gather}
    [29 - 3 · (12 - 9)] : 5 \\
    15 - (10 - [12 - (4 + 6)]) \\
    ([25 - (9 + 6)]· 4 - 10) : (36 : 12)
    \end{gather}
