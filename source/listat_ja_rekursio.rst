Listat ja rekursio
==================

.. figure:: _static/Singly-linked-list.svg

   A singly linked list of three numbers.

.. todo::

    Esimerkki listan summasta ja kertomasta: Tyhjän listan tapaus eri!
    Listan neliöiden summa. Listan konkatenointi.
    Listan koon laskeminen. Filteröinti (eri tehtävissä erilailla?).
    Listan muuttaminen kuvaksi.

::

    (require 2htdp/image)

    (check-expect (summa (list 1 2 3 4)) 10)
    (define (summa lista)
      (cond [(empty? lista) 0]
            [else (+ (first lista) (summa (rest lista)))]))

    (check-expect (kertoma (list 1 2 3 4)) 24)
    (define (kertoma lista)
      (cond [(empty? lista) 1]
            [else (* (first lista) (kertoma (rest lista)))]))

    (check-expect (neliöt (list 1 2 3 4)) 30)
    (define (neliöt lista)
      (cond [(empty? lista) 0]
            [else (+ (expt (first lista) 2) (neliöt (rest lista)))]))

    (check-expect (konkatenoi (list "Moi" "," " " "maailma"))
                  "Moi, maailma")
    (define (konkatenoi lista)
      (cond [(empty? lista) ""]
            [else (string-append (first lista) (konkatenoi (rest lista)))]))

    (check-expect (koko (list 1 2 3 4)) 4)
    (define (koko lista)
      (cond [(empty? lista) 0]
            [else (+ 1 (koko (rest lista)))]))

    (check-expect (yli-kolme (list 1 2 3 4 5)) (list 4 5))
    (define (yli-kolme lista)
      (cond [(empty? lista) empty]
            [(> (first lista) 3) (cons (first lista)
                                       (yli-kolme (rest lista)))]
            [else (yli-kolme (rest lista))]))

    (check-expect (helmet (list 1 2))
                  (beside (circle 1 "solid" "blue")
                          (circle 2 "solid" "blue")))
    (define (helmet lista)
      (cond [(empty? lista) empty-image]
            [else (beside (circle (first lista) "solid" "blue")
                          (helmet (rest lista)))]))


Kiinnostuitko?
--------------
.. todo:: Puut onkin nyt oma kappaleensa... tarvitsee muuta

.. figure:: _static/Binary_tree.svg

   A binary tree.
