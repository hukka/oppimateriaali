.. highlight:: racket

Musiikkia
=========

::

    (require rsound)
    (require rsound/piano-tones)

    (rs-draw (assemble (list
                         (list (piano-tone 60) 0)
                         (list (piano-tone 64) 44100)
                         (list (piano-tone 67) 22050))))



