Funktioiden suunnittelu ja testaus
==================================

::

    ; Number -> Number
    ; muuta asteet Celsiusta Kelvineiksi

::

    ; Number -> Number
    ; muuta asteet Celsiusta Kelvineiksi
    (define (celsius->Kelvin C)
        ...)


::

    ; Number -> Number
    ; muuta asteet Celsiusta Kelvineiksi
    (check-expect (celsius-Kelvin 0) 273.15)
    (check-expect (celsius-Kelvin -273.15) 0)
    (define (celsius->Kelvin C)
        ...)


::

    ; Number -> Number
    ; muuta asteet Celsiusta Fahrenheiteiksi
    ; given 32, expected 0
    ; given 212, expected 100
    ; given -40, expected -40
    (check-expect (celsius->fahrenheit 0) 32)
    (check-expect (celsius->fahrenheit 100) 212)
    (check-expect (celsius->fahrenheit -40) -40)
    (define (celsius->fahrenheit C)
        (+ 32 (* 9/5 C)))

.. todo:: Ostoslista, top-down
