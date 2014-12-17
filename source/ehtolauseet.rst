Ehtolauseet ja boolean-logiikka
===============================
Tätä kappaletta varten pitää ensin lukea :doc:`omat_funktiot`.


Liisa haluaa tilata pitsan.
Hänellä on muutama ehdoton vaatimus:
hän rakastaa homejuustoa, joten pitsassa täytyy olla aurajuustoa,
ja lisäksi hän haluaa proteiinia, joten pitsa kelpaa vain jos siinä on
joko kinkkua tai jauhelihaa.
Ananakset ja persikat kuuluvat Liisan mielestä hedelmäsalaattiin,
ei pääruokaan.

Eli Liisa suostuu syömään aura-kinkku-, aura-jauheliha-
ja aura-kinkku-jauheliha-pitsan.

Tällaisia ehtoja sanotaan matematiikassa Boolen algebraksi.
Siinä on pohjana kaksi totuusarvoa, tosi ja epätosi,
ja kolme funktiota; :samp:`JA`, :samp:`TAI` ja :samp:`EI`.
:samp:`JA` on tosi silloin kun kaikki sen argumenteista ovat tosia,
:samp:`EI` jos ainakin yksi on tosi ja
:samp:`EI` silloin kun sen ainut argumentti on epätosi.

Myös Racketissä on näille vastaavat funktiot.
Liisan vaatimus Rackettinä olisi

::

    (and onko-auraa
         (or onko-kinkkua onko-jauhelihaa)
         (not onko-ananasta)
         (not onko-persikkaa))

.. admonition:: Tehtävä

    Tee funktio, joka kertoo ovatko pitsan täytteet sellaiset,
    että sinä suostuisit syömään sen.

    Jos olet erityisen kaikkiruokainen tai kranttu,
    voit myös käyttää kaverin toiveita.

Racketissä on myös komento, jolla erilaiset ehdot johtavat
eri tuloksiin::

    (cond
      [ehtolause tuloslause]
      [toinen-ehtolause toinen-tuloslause]
      [else kolmas-tuloslause])

Ehtolause on funktio, jonka arvoksi tulee joko tosi tai epätosi.
Se voi käyttää hyväkseen Boolen funktioita,
mutta myös esimerkiksi lukujen vertailuja.
Tuloslause taas voi olla mitä tahansa.

Ehtolauseita voi olla miten monta vain
ja lisäksi viimeisenä voi olla erikoistapaus :code:`else`.
:code:`else` toteutuu aina, jos mikään edellinen ehtolause ei ole ollut tosi.

Lopuksi condin arvoksi tulee se tuloslause,
jonka parina oleva ehtolause oli tosi.

Esimeriksi jos haluaisimme muuttaa lämpötilan asteina Celsiusta
sanalliseksi kuvaukseksi, toimisi seuraavanlainen funktio::

    (define (lämpötilan-kuvaus C)
      (cond
        [(> 40 C 25) "Liian kuumaa!"]
        [(> 25 C 18) "Kelvollinen sisälämpötila"]
        [(> 18 C 0 ) "Suomen kesä"]
        [(> 0 C -30) "Taitaa olla talvi"]
        [else "Oletko edes tällä planeetalla?"]))

Elseä tarvitaan, jos muut ehdot eivät kata kaikkia vaihtoehtoja.
Jos ohjelman aikana käy niin, että mikään condin ehto ei ole tosi
eikä sillä ole else-ehtoa,
DrRacket antaa virheilmoituksen ja ohjelma pysähtyy.

Huomaa, että jos funktion lopputulos on boolean,
ei condia tarvita lainkaan.
Esimerkiksi funktio, joka kertoo syyssadetta inhoavalle
onko sää sopiva ulkoiluun,

::

    (define (voiko-mennä-ulos? C sataako?)
      (cond
        [(>= 30 C 22) true]
        [(>= 22 C 0) (not sataako?)]
        [(> 0 C -25) true]
        [else false]))

on mahdollista kirjoittaa tiiviimmin muodossa

::

    (define (voiko-mennä-ulos? C sataako?)
      (or (>= 30 C 22)
          (and (>= 22 C 0)
               (not sataako?))
          (> 0 C -25)))

.. admonition:: Tehtävä

    Tee funktio, joka piirtää annetun värisen puun.
    Mutta väri annetaanki tällä kertaa suomeksi!

    Laita funktio ymmärtämään ainakin kahta eri suomenkielistä väriä.

    Muista myös miettiä mitä tapahtuu jos funktiota kutsutaan
    jollain muulla värillä, kuin mihin olit varautunut.

.. note::

    Condin ei tarvitse olla määritellyn funktion ensimmäisellä tasolla!
    Funktiossa voi käyttää condia argumenttina aivan kuin mitä
    tahansa muutakin funktiota, koska se palauttaa jotain.
    Esimerkiksi funktion, joka ymmärtää joitain suomenkielisiä värejä
    voisi tehdä näin::

        (define (ympyrä väri)
          (circle 20 "solid"
                  (cond
                    [(string=? väri "keltainen") "yellow"]
                    [(string=? väri "sininen") "blue"]
                    [(string=? väri "punainen") "red"]
                    [else "black"])))

Kiinnostuitko?
--------------
Boolen funktiot eivät ole ainoita loogisia funktioita.
Funktioita voidaan esittää totuustaulussa.
Taulun alussa on kaksi tai useampi argumentti,
joiden arvo on joko tosi tai epätosi.
Sen jälkeen listataan kullekin funktiolle onko se tosi
vai epätosi samalla rivillä olevien argumenttien mukaan.

Tässä taulussa P ja Q ovat argumentteja,
arvot on merkitty truen ja false'in etukirjaimilla.

= = ===== ==== ====== ===== ===== ===== =====
P Q AND ∧ OR ∨ NAND | NOR ⊽ XOR ⊕ IMP ⇒ EQV ⇔
= = ===== ==== ====== ===== ===== ===== =====
T T  T    T     F      F     F     T     T
T F  F    T     T      F     T     F     F
F T  F    T     T      F     T     T     F
F F  F    F     T      T     F     T     T
= = ===== ==== ====== ===== ===== ===== =====

Miten tekisit loput funktiot Racketissä olevilla
:code:`and`, :code:`or` ja :code:`not` funktioilla?

.. admonition:: Tehtävä

    Fibonaccin lukujono muodostuu näin:

    - Ensimmäinen luku on 1
    - Toinen luku on 1
    - Muut luvut ovat kaksi edellistä lukua laskettuna yhteen

    Tee funktio, joka ottaa yhden luonnollisen luvun N argumenttina
    ja palauttaa N:n Fibonaccin luvun.

    Eli

    ::

        (= (fib 1) 1)
        (= (fib 2) 1)
        (= (fib 3) 2)
        (= (fib 4) 3)

    ja niin edelleen.

.. hint::

    Tarvitset funktioon kolmen vaihtoehdon ehtolauseen.
    Ensimmäinen kertoo vastauksen, jos argumentti on 1.
    Toinen, jos 2.
    Kolmas laskee yhteen kaksi Fibonaccin-lukua.
    Millä funktiolla saat Fibonaccin luvun?
