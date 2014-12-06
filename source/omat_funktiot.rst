Omat funktiot
=============
Omat funktiot määritellään kirjoittamalla

::

    (define (funktion-nimi parametri toinen-parametri)
        ...)

Tässä suluissa oleva ensimmäinen "argumentti" näyttää funktiokutsulta,
mutta ei oikeasti ole sitä, eikä edes argumentti:
:code:`define` on Rackettiin tehty poikkeustapaus
(siksi se ei myöskään palauta mitään arvoa, kuten vakioihin tutustuttaessa huomattiin).

Pisteiden tilalle tulee joko arvo tai funktiokutsu,
jonka lopputulos on myös uuden, tässä määritellyn funktion lopputulos.
Sekä funktion että parametrien nimet saa päättää samoilla säännöillä  kuin vakioidenkin nimet.

Parametrejä tulee olla vähintään yksi, mutta niitä ei ole pakko käyttää
(tällöin on tosin parempi käyttää funktion sijaan vakiota).
Ne toimivat niminä funktiokutsussa annetuille arvoille,
ikäänkuin ne olisivat vakioita, jotka toimivat vain funktion sisällä.

Esimerkiksi funktio

::

    (define (funktio1 a b)
        2)

palauttaa aina arvon :samp:`2` riippumatta siitä,
millä argumenteilla funktiota kutsutaan.
Funktio

::

    (define (plus x y)
        (+ x y))

laskisi kahden annetun numeron summan, ja

::

    (define (pallo koko)
        (circle koko "solid" "yellow"))

piirtäisi annetun kokoisen, keltaisen pallon.

Kuten vakiotkin, omat funktiot määritellään DrRacketin yläosaan,
jonka jälkeen niitä voi käyttää kuten mitä tahansa muutakin funktiota.

.. note::

    Huomaa parametrin ja argumentin ero!
    Argumentti on tietoa, joka annetaan funktiolle sitä kutsuttaessa.
    Parametri on tälle tiedolle annettu nimi, jota funktio käyttää sisäisesti.
    Esimerkiksi ylempänä olevat a, b, x ja y ovat parametrejä,
    mutta funktiokutsussa :code:`(plus 10 15)` 10 ja 15 ovat argumentteja.


.. admonition:: Tehtävä

    Tee funktio

    - :samp:`kolmio`, joka antaa kuvan suorakulmaisesta kolmiosta,
      kun sille annetaan kateettien pituudet
    - :samp:`kolmion-pinta-ala`, joka laskee suorakulmaisen kolmion pinta-alan,
      kun sille annetaan kolmion kateettien pituudet.
    - :samp:`hypotenuusa`, joka laskee hypotenuusan kun
      sille annetaan kolmion kateettien pituudet.

.. admonition:: Tehtävä

    Tee funktiot :code:`eur->usd` ja :code:`usd->eur`,
    joilla voit muuttaa euroja dollareiksi ja toisinpäin.

.. admonition:: Tehtävä

    Tee funktio, joka piirtää annetun värisen auton
    (esim. :code:`(piirrä-auto "red")`).

.. admonition:: Tehtävä

    Tee funktio, joka antaa toisen asteen yhtälön nollakohdan
    (toinen juurista riittää tässä vaiheessa),
    kun sille annetaan argumentteina polynomin kertoimet.
