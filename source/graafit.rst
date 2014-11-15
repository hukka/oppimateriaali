Funktioiden piirtäminen graafeiksi
==================================

Vaatii :samp:`Intermediate Student`-kielen.

Vaatii :doc:`paikalliset_maaritelmat`.

::

    (require 2htdp/universe)
    (require 2htdp/image)

    (define WIDTH 600)
    (define HEIGHT 600)
    (define MAX_Y 1.4)
    (define MAX_X 5)


    (define (draw world)
        (local ((define (f x) (sin (+ x world))))
               (plot f (- MAX_X) 0.2 (empty-scene WIDTH HEIGHT))))

    (define (plot function start step scene)
        (cond
            [(> (+ step start) MAX_X) scene]
            [else (plot function (+ start step) step
                        (add-line
                            scene
                            (scale-x start)
                            (scale-y (function start))
                            (scale-x (+ step start))
                            (scale-y (function (+ step start)))
                            "black"))]))

    (define (scale-x value)
        (+ (* (/ value 2 MAX_X) WIDTH)
        (/ WIDTH 2)))

    (define (scale-y value)
        (+ (* (/ value 2 MAX_Y) HEIGHT)
        (/ HEIGHT 2)))

    (define (step world)
        (+ world 0.1))

    (big-bang 0
        [to-draw draw]
        [on-tick step])
