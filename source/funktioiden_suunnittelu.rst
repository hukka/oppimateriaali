Funktioiden suunnittelu ja testaus
==================================

1. Mieti ja kirjoita ylös missä muodossa tieto on
-------------------------------------------------
Esimerkiksi lämpötilat, etäisyydet ja kappaleen dimensiot ovat desimaalinumeroita;
nimet ja osoitteet tekstiä; ja
kuvat kuvia.

2. Kirjoita funktion syötteet ja ulostulot, tarkoitus ja funktion yläosa
------------------------------------------------------------------------
Syötteet tulevat välein eroteltuna ensin, ja sitten nuolen jälkeen ulostulot.
Käytä Racketin tietotyyppejä kuvaamaan molempia.

Sen jälkeen kirjoita selväkielinen, lyhyt kuvaus funktion tarkoituksesta.

Lopuksi tee funktion kuvaus, joka sisältää funktion ja parametrien nimet.
Funktio voi tässä vaiheessa palauttaa minkä tahansa ulostulon tyypin arvon.

Esimerkiksi

::

    ; Number -> Number
    ; muuta asteet Celsiusta Kelvineiksi
    (define (celsius->Kelvin C)
        0)

::

    ; Number -> Image
    ; Piirrä pallo, jonka säde annetaan
    (define (piirrä-pallo säde)
        (empty-scene))

3. Mieti esimerkkejä syötteestä ja oikeasta ulostulosta, ja kirjoita ne testeiksi
---------------------------------------------------------------------------------

::

    ; Number -> Number
    ; muuta asteet Celsiusta Kelvineiksi
    (check-expect (celsius-Kelvin 0) 273.15)
    (check-expect (celsius-Kelvin -273.15) 0)
    (define (celsius->Kelvin C)
        0)

4. Hahmottele funktiota
-----------------------
Mieti mitä kaikkea funktio ainakin tarvitsee toimiakseen.
Muodosta hahmotelma, johon ne on sijoitettu.
Hahmotelmaan tulee vähintään funktion parametrit.

::

    ; Number -> Number
    ; muuta asteet Celsiusta Kelvineiksi
    (check-expect (celsius-Kelvin 0) 273.15)
    (check-expect (celsius-Kelvin -273.15) 0)
    (define (celsius->Kelvin C)
        (... C ...))

Hahmotelma ei ole oikeaoppisesti ohjelma,
joten tässä vaiheessa ohjelman suorittaminen valittaisi ongelmista.
Sen tarkoitus on auttaa miettimään ohjelman rakennetta.

5. Koodaa!
----------

::

    ; Number -> Number
    ; muuta asteet Celsiusta Fahrenheiteiksi
    (check-expect (celsius->fahrenheit 0) 32)
    (check-expect (celsius->fahrenheit 100) 212)
    (check-expect (celsius->fahrenheit -40) -40)
    (define (celsius->fahrenheit C)
        (+ 32 (* 9/5 C)))

6. Testaa
---------
Kun käytät :samp:`check-expect` funktiota,
voit helposti testata funktion toimivuuden suorittamalla ohjelman.
Jos ohjelma toimii, olet valmis.
Jos ei, ohjelmassa voi olla virhe ja sinun täytyy palata edelliseen kohtaan.
On myös mahdollista, että testeissä on virhe,
joten jos et löydä koodista ongelmia, varmista että testisi ovat oikein.

.. todo:: Ostoslista, top-down
