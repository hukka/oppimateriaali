Vakiot
======
Racketissä on mahdollista antaa nimiä eri arvoille.
Tämä vähentää toistoa, jos arvo on laskettu pitkällä ja monimutkaisella
funktiokutsulla.
Se helpottaa myös ohjelman muuttamista: nimetty arvo tarvitsee muuttaa vain kerran,
eikä jokaisessa paikassa, missä sitä käytetään.
Nimeämistä sanotaan :term:`määritelmäksi <määritelmä>` ja
nimettyä arvoa :term:`vakioksi <vakio>`.
Nimi annetaan komennolla :code:`define`::

    (define nimi arvo)

Vakion nimi voi olla lähes mitä tahansa:
merkit (, ), [, ], {, }, ",  ', \`, ,; ,# ,| ,\\ ja itse pilkku ovat kiellettyjä.
Lisäksi nimi ei saa näyttää numerolta.

Esimerkiksi kahden ympyrän kuvalle voi antaa nimen näin::

    (require 2htdp/image)
    (define ympyrät
      (overlay (circle 20 "solid" "red")
               (circle 30 "solid" "blue")))

.. note::

    Määritelmät täytyy kirjoittaa DrRacketin yläosaan!

Kun olet kirjoittanut määritelmän, voit käyttää sitä määritelmän alapuolella olevassa koodissa, sekä suoraan alaosassa.
:code:`define` ei ole varsinaisesti funktio, sillä se ei palauta mitään.
Jos siis esimerkiksi määrittelet kuvan, se ei tule näkyviin ennenkuin
kirjoitat sille antamasi nimen ikäänkuin kirjoittaisit numeroita,
merkkijonoja tai kopioisit kuvia.
Vakioita voi laittaa myös funktioiden argumenteiksi,
aivan kuten arvoja.

.. note::

    Huomaa, että vakio ei ole funktiokutsu, eli sen ympärille ei tule sulkuja!
    Se ei myöskään ole tekstiä, joten sen ympärille ei tule lainausmerkkejä.
    Eli jos vakio :code:`pekka` olisi määritelty

    ::

        (define pekka "kissanhiekka")

    niin :code:`pekka` antaisi sanan "kissanhiekka" ja :code:`"pekka"` sanan "pekka".

Esimerkiksi kuvan metsästä voisi tehdä vaikka näin::

    (require 2htdp/image)
    (define latva
      (overlay/align/offset
       "middle" "top"
       (triangle 20 "solid" "green")
       0 10
       (triangle 30 "solid" "green")))
    latva

    (define runko (rectangle 10 10 "solid" "brown"))
    runko

    (define kuusi
      (above latva runko))
    kuusi

    (define metsä
      (beside kuusi kuusi kuusi kuusi kuusi))
    metsä

.. image:: _static/vaalea-metsa.png

Nyt jos kuusien väriä halutaan muuttaa,
tarvitsee muutos tehdä vain vakion määritelmään::

    (define latva
      (overlay/align/offset
       "middle" "top"
       (triangle 20 "solid" "darkgreen")
       0 10
       (triangle 30 "solid" "darkgreen")))

.. image:: _static/tumma-metsa.png

.. admonition:: Tehtävä

    Piirrä lehtipuu, anna sille nimi, ja piirrä metsä jossa on sekä
    kuusia, että lehtipuita.
