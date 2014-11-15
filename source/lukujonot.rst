Lukujonot
=========

::

    (define (jono aloitus operaatio askel määrä)
      (cond [(= määrä 0) empty]
            [else (cons aloitus (jono (operaatio aloitus askel) operaatio askel (- määrä 1)))]))

    (check-expect (aritmeettinen-jono 0 2 5) (list 0 2 4 6 8))
    (check-expect (aritmeettinen-jono -7 3 4) (list -7 -4 -1 2))
    (define (aritmeettinen-jono aloitus askel määrä)
      (jono aloitus + askel määrä))

    (check-expect (geometrinen-jono 0 10 5) (list 0 0 0 0 0))
    (check-expect (geometrinen-jono 2 2 5) (list 2 4 8 16 32))
    (check-expect (geometrinen-jono 2 1/2 5) (list 2 1 1/2 1/4 1/8))
    (define (geometrinen-jono aloitus askel määrä)
      (jono aloitus * askel määrä))

    (check-expect (fibonacci 1) 1)
    (check-expect (fibonacci 2) 1)
    (check-expect (fibonacci 3) 2)
    (check-expect (fibonacci 4) 3)
    (define (fibonacci mones)
      (cond [(or (= mones 1) (= mones 2)) 1]
            [else (+ (fibonacci (- mones 1)) (fibonacci (- mones 2)))]))
