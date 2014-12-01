Omat funktiot
=============
Omat funktiot määritellään kirjoittamalla

::

    (define (funktion-nimi parametri toinen-parametri)
        ...)

Pisteiden tilalle tulee lause,
jonka loppuarvo on myös funktiokutsun loppuarvo.
Sekä funktion että parametrien nimet voivat olla mitä tahansa.
Parametrejä tulee olla vähintään yksi, mutta niitä ei ole pakko käyttää.
Ne toimivat niminä funktiokutsussa annetuille arvoille.

Esimerkiksi funktio::

    (define (funktio1 a b)
        2)

palauttaa aina kaksi riippumatta millä arvoilla funktiota kutsutaan.
Funktio::

    (define (plus x y)
        (+ x y))

laskisi kahden annetun numeron summan.


.. admonition:: Tehtävä

    Tee funktio

    - :samp:`kolmio`, joka antaa kuvan suorakulmaisesta kolmiosta,
      kun sille annetaan kateettien pituudet
    - :samp:`kolmion-pinta-ala`, joka laskee suorakulmaisen kolmion pinta-alan,
      kun sille annetaan kolmion kateettien pituudet.
    - :samp:`hypotenuusa`, joka laskee hypotenuusan kun
      sille annetaan kolmion kateettien pituudet.
    - :samp:`kuvan-luokittelu` joka palauttaa tekstin "korkea",
      jos sille annettu kuvan korkeus on suurempi kuin leveys;
      "neliö", jos ne ovat yhtäsuuret
      ja muussa tapauksessa "leveä".


.. todo::

    Pitäisikö tehtävien olla matemaattisesti helpompia,
    jotta niitä voisi käyttää jo aikaisemmilla luokka-asteilla?
    Tai kokonaan epämatemaattisia,
    esimerkiksi merkkijonojen ja kuvien käsittelyä?
