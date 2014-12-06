Musiikkia
=========
:samp:`raco pkg install rsound`

::

    (require rsound)
    (require rsound/piano-tones)

    (define (piano-list number-list time)
      (cond [(empty? number-list) empty]
            [else (cons (list (piano-tone (first number-list))
                              (* 22050 time))
                        (piano-list (rest number-list)
                                    (+ time 1)))]))

    (play
     (assemble
      (piano-list
       (list 60 60 60 64 62 62 62 65 64 64 62 62 60) 0)))
