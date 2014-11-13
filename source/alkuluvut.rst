Tekijöihin jako ja alkuluvut
============================

::

    (define (tekijä luku jakaja)
      (cond
        [(= luku 1)
         empty]
        [(= (modulo luku jakaja) 0)
         (cons jakaja (tekijä (/ luku jakaja) 2))]
        [else
         (tekijä luku (+ jakaja 1))]))

    (check-expect (etsi-tekijät 10) (list 2 5))
    (check-expect (etsi-tekijät 11) (list 11))
    (check-expect (etsi-tekijät 300) (list 2 2 3 5 5))
    (define (etsi-tekijät luku)
      (tekijä luku 2))

    (check-expect (alkuluku? 2) #true)
    (check-expect (alkuluku? 3) #true)
    (check-expect (alkuluku? 11) #true)
    (check-expect (alkuluku? 4) #false)
    (check-expect (alkuluku? 15) #false)
    (define (alkuluku? luku)
        (= (length (etsi-tekijät luku)) 1))

    (check-expect (etsi-alkuluvut 0 100) empty)
    (check-expect (etsi-alkuluvut 1 2) (list 2))
    (check-expect (etsi-alkuluvut 7 2) (list 2 3 5 7 11 13 17))
    (check-expect (etsi-alkuluvut 1 15) (list 17))
    (define (etsi-alkuluvut kuinka-monta aloitus)
      (cond
        [(= kuinka-monta 0)
         empty]
        [(alkuluku? aloitus)
         (cons aloitus (etsi-alkuluvut (- kuinka-monta 1) (+ aloitus 1)))]
        [else
         (etsi-alkuluvut kuinka-monta (+ aloitus 1))]))

.. todo:: Kommentoitu versio ja vertailu helppolukuisuudesta

.. todo:: Nopeampi versio, joka tarkistaa vain neliöjuureen asti,
          ja kolmas joka tarkistaa jakamalla aikaisemmilla alkuluvuilla

.. todo:: Katsoa wikipediasta oikeasti nopea algoritmi

.. todo:: Vertailu kertolaskun ja tekijöiden etsimisen nopeudesta: RSA
