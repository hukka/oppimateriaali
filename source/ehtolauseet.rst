Ehtolauseet ja boolean-logiikka
===============================
Pitsa on ok, jos siinä on aurajuustoa JA joko kinkkua TAI jauhelihaa.
Eli aura-kinkku-, aura-jauheliha- ja aura-kinkku-jauheliha-pitsa ovat
kaikki kelvollisia.

::

    (and onko-auraa (or onko-kinkkua onko jauhelihaa))

::

    (define (lämpötilan-kuvaus C)
      (cond
        [(> 40 C 25) "liian kuumaa!"]
        [(> 25 C 18) "kelvollinen sisälämpötila"]
        [(> 18 C 0 ) "Suomen kesä"]
        [(> 0 C -30) "Taitaa olla talvi"]
        [else "Oletko edes tällä planeetalla?"]))


Jos funktion lopputulos on boolean, ei condia tarvita lainkaan::

    (define (voiko-mennä-ulos? C sataako?)
      (cond
        [(>= 30 C 22) true]
        [(>= 22 C 0) (not sataako?)]
        [(> 0 C -25) true]
        [else false]))

    (define (voiko-mennä-ulos? C sataako?)
      (or
        (>= 30 C 22)
        (and (>= 22 C 0) (not sataako?))
        (> 0 C -25)))

.. note::

    Condin ei tarvitse olla määritellyn funktion ensimmäisellä tasolla!
    Funktiossa voi käyttää condia, koska se palauttaa jotain.
    Voit siis käyttää condia myös argumenttina toisen funktiokutsun sisällä::

        (define (ympyrä väri)
          (circle 20 "solid"
                  (cond
                    [(string=? väri "keltainen") "yellow"]
                    [(string=? väri "sininen") "blue"]
                    [(string=? väri "punainen") "red"]
                    [else "black"])))

Kiinnostuitko?
--------------
= = === == ==== === ===
P Q AND OR NAND NOR XOR
= = === == ==== === ===
T T  T  T   F    F   F
T F  F  T   T    F   T
F T  F  T   T    F   T
F F  F  F   T    T   F
= = === == ==== === ===

.. admonition:: Tehtävä

    Fibonaccin lukujono muodostuu näin:

    - Ensimmäinen luku on 1
    - Toinen luku on 1
    - Muut luvut ovat kaksi edellistä lukua laskettuna yhteen

    Tee funktio, joka ottaa yhden luonnollisen luvun N argumenttina
    ja palauttaa N. Fibonaccin luvun.

    Eli

    ::

        (= (fib 1) 1)
        (= (fib 2) 1)
        (= (fib 3) 2)
        (= (fib 4) 3)

.. hint::

    Tarvitset funktioon kolmen vaihtoehdon ehtolauseen.
    Ensimmäinen kertoo vastauksen, jos argumentti on 1.
    Toinen, jos 2.
    Kolmas laskee yhteen kaksi Fibonaccin-lukua.
    Millä funktiolla saat Fibonaccin luvun?
