Tiedon hakeminen suoraan Internetistä
=====================================
::

    (require racket)
    (require net/url)
    (require json)

    (define JSON
      "{\"coord\":{\"lon\":25.47,\"lat\":65.01},\"sys\":{\"type\":1,\"id\":5036,\"message\":0.1024,\"country\":\"FI\",\"sunrise\":1415255105,\"sunset\":1415281107},\"weather\":[{\"id\":800,\"main\":\"Clear\",\"description\":\"Sky is Clear\",\"icon\":\"01n\"}],\"base\":\"cmc stations\",\"main\":{\"temp\":262.15,\"pressure\":1023,\"humidity\":92,\"temp_min\":262.15,\"temp_max\":262.15},\"wind\":{\"speed\":2.6,\"deg\":150},\"clouds\":{\"all\":0},\"dt\":1415283600,\"id\":643492,\"name\":\"Oulu\",\"cod\":200}")

    (hash-ref
      (hash-ref
        (string->jsexpr JSON)
        'main)
      'temp)

    (hash-ref
      (hash-ref
        (string->jsexpr
          (bytes->string/utf-8
            (port->bytes
              (get-pure-port
                (string->url "http://api.openweathermap.org/data/2.5/weather?q=Oulu,fi")))))
        'main)
      'temp)
