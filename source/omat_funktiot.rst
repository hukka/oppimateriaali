Omat funktiot
=============
Omat funktiot määritellään vakioiden tapaan kirjoittamalla

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

    (define (plus x y)
        (+ x y))

laskisi kahden annetun numeron summan. Se toimisi aivan samalla lailla,
vaikka määrittelisit sen näin::

    (define (plus koira kissa)
        (+ koira kissa))

eli annetuilla nimillä ei ole väliä, kunhan käytät samoja nimiä jotka olet
antanut parametreille.

.. admonition:: Tehtävä

    Tee oma funktio, joka käyttää kolmea parametriä.
    Muista laittaa funktion ja parametrien nimien ympärille sulut,
    muuten Racket luulee sinun määrittelevän vakioita!

Funktio voi palauttaa mitä tahansa arvoja, ei pelkästään lukuja.
Esimerkiksi

::

    (define (pallo säde)
        (circle säde "solid" "yellow"))

palauttaisi annetun kokoisen, keltaisen pallon.

Kaikkia parametrejä ei ole pakko käyttää. Esimerkiksi

::

    (define (funktio1 a b)
        2)

palauttaa aina arvon :samp:`2` riippumatta siitä,
millä argumenteilla funktiota kutsutaan. Tosin
tarpeettomista parametreistä ei ole mitään hyötyä.

Kuten vakiotkin, omat funktiot määritellään DrRacketin yläosaan,
jonka jälkeen niitä voi käyttää kuten mitä tahansa muutakin funktiota.

.. note::

    Huomaa parametrin ja argumentin ero!
    Argumentti on tietoa, joka annetaan funktiolle sitä kutsuttaessa.
    Parametri on tälle tiedolle annettu nimi, jota funktio käyttää sisäisesti.
    Esimerkiksi ylempänä olevat a, b, x ja y ovat parametrejä,
    mutta funktiokutsussa :code:`(plus 10 15)` 10 ja 15 ovat argumentteja.


.. admonition:: Tehtävä

    Tee funktiot :code:`eur->usd` ja :code:`usd->eur`,
    joilla voit muuttaa euroja dollareiksi ja toisinpäin.

.. admonition:: Tehtävä

    Tee funktio

    - :samp:`kolmio`, joka antaa kuvan suorakulmaisesta kolmiosta,
      kun sille annetaan kateettien pituudet käyttäen valmista piirtofunktiota
      :code:`right-triangle`
    - :samp:`kolmion-pinta-ala`, joka laskee suorakulmaisen kolmion pinta-alan,
      kun sille annetaan kolmion kateettien pituudet.
    - :samp:`hypotenuusa`, joka laskee hypotenuusan kun
      sille annetaan kolmion kateettien pituudet (neliöjuurifunktion nimi on sqrt).

.. admonition:: Tehtävä

    Tee funktio, joka piirtää annetun värisen auton
    (esim. :code:`(piirrä-auto "red")`).
    Voit käyttää aiemman autotehtävän vastaustasi apuna.

    Jos autosta tulee musta, Racket ei ole ymmärtänyt väriäsi.
    Ts. kaikki tuntemattomat värit oletetaan mustaksi.
    Muistele, miten vakioita ja parametrejä käytetään!

.. admonition:: Tehtävä

    Tee funktio, joka antaa toisen asteen yhtälön nollakohdan
    (toinen juurista riittää tässä vaiheessa),
    kun sille annetaan argumentteina polynomin kertoimet.
