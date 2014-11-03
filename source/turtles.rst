Turtle-grafiikka
================

::

    (require graphics/value-turtles)

    (define sivun-pituus 40)
    (define ruudun-koko 150)

    (define (kulma n asteet turtle)
        (cond
              [(= n 0) turtle]
                  [else (kulma (- n 1) asteet (turn asteet (draw sivun-pituus turtle)))]))

    (define (monikulmio n)
        (kulma n (/ 360 n) (turtles ruudun-koko ruudun-koko)))

    (monikulmio 3)
    (monikulmio 4)
    (monikulmio 5)
    (monikulmio 6)
