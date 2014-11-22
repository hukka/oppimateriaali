Puut ja graafit
===============
::samp::`raco pkg install graph`

BSL with list abbreviations

Pitää olla quote selitettynä

Solmu, kaari, graafi, sykli, syklitön (puu)

Suunnattu ja suuntaamaton

Painotettu ja painottamaton

::

    (require graph)
    (define g (weighted-graph/undirected
               '((178 Helsinki Tampere)
                 (168 Helsinki Turku)
                 (162 Turku Tampere)
                 (104 Helsinki Lahti)
                 (63 Kouvola Lahti)
                 (127 Lahti Tampere)
                 (487 Oulu Tampere)
                 (287 Oulu Kuopio)
                 (320 Oulu Vaasa)
                 (242 Vaasa Tampere)
                 (335 Vaasa Turku)
                 (290 Lahti Kuopio)
                 (292 Kuopio Tampere)
                 (377 Kuopio Vaasa)
                 (267 Kuopio Kouvola))))
    (get-vertices g)
    (get-edges g)
    (edge-weight g 'Helsinki 'Lahti)

Lyhyimmän matkan etsiminen kahden kaupungin välillä
---------------------------------------------------

Leveyshaku
**********

Syvyyshaku
**********

Djikstra
********

Kauppamatkustajan ongelma
-------------------------
