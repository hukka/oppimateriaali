.. Yläkoulun ohjelmointia master file, created by
   sphinx-quickstart on Sun Nov  2 16:08:59 2014.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Yläkoulun ohjelmointia!
=======================

.. todo:: Tehtäville voisi luoda oman komennon, jotta niistä saa oman listauksen

.. todo:: Minne mallivastaukset?

.. todo::

    Racketin builtinit saisi linkattua dokkareihin käyttämällä
    pygmentsin formatteria, joka wrappaisi lexeriltä tulevat keywordit
    anchoreiksi ja antaisi ne vasta sitten eteenpäin tavalliselle
    HtmlFormatterille.

    Mikäli haluaisi vielä viilata tarkemmin, pitäisi tehdä uusi
    lexeri, jossa keywordit ja builtinit olisi korvattu BSL:n
    vastaavilla muokkaamalla tests/examplefiles/example.rkt ulostuloa

.. todo::

    Linkit tehtävistä yms. aiheista OPS:n. Jokin systeemi,
    jolla taas OPS-osassa näkee mitkä tehtävät kattavat minkäkin kohdan,
    ja mitä jää kattamatta.

.. todo::

    Graafi, josta näkee missä järjestyksessä kappaleet pitää käydä.
    Esim. Gephi voi saattaa tehdä nättejä, jos Graphviziä ei saa säädettyä.


Ohjelmoinnin käsitteitä (esitietovaatimuksia):

.. toctree::
   :maxdepth: 2

   sanasto
   miksi-koodata
   ops2016
   perusasiat
   laskujarjestys
   ehtolauseet
   vakiot
   omat_funktiot
   funktioiden_suunnittelu
   tiedostot-1
   animaatiot-1
   structit
   interaktiivisuus
   listat
   tiedostot-2
   rekursio
   lambda_ja_funktiot_parametreina
   puut_ja_graafit
   paikalliset_maaritelmat
   muuttujat_ja_silmukat
   sivuvaikutukset
   algoritmien_vaativuus

.. todo:: Onko tiedostojen käsittely ydinkonsepti vai sovellus?

Ohjelmoinnin sovelluksia:

.. toctree::

   piirtokomennot
   animaatiot-2
   animaatiot-3
   turtles
   ympyrä
   musiikkia
   salasanat
   alkuluvut
   dataa-netista
   funktion_kuvaajat
   lukujonot


Ideoita

- Luvun ja numeron ero, 5 ja V ovat samoja lukuja, mutta eri kirjoitusjärjestelmän
  numeroita. Racketissä 42 ja "42" tarkoittavat lukua ja numeroista koostuvaa tekstiä.
- "Perehdytään lukujen jaollisuuteen ja opitaan jakamaan luku alkutekijöihin"
  Tehdään ohjelma, joka etsii alkulukuja ja jakaa lukuja tekijöihinsä
- "Vahvistetaan ymmärrystä tarkan arvon ja likiarvon erosta sekä pyöristämisestä."
  Jakolaskuja muilla kuin kahdella ja viidellä, ja sitten takaisin kertomista.
- "Opitaan neliöjuuren käsite ja käytetään neliöjuurta laskutoimituksissa"
  Pythagoras kaikissa etäisyyttä vaativissa 2D- ja 3D-animaatioissa
- Livecoding-moduuli extemporella (musiikki)
- Livecoding-moduuli fluxuksella
- Robottimoduuli EV3:lla
- binäärihaku, esimerkiksi funktion nollakohdalle
- jotain numeeristä integrointia trapezoideilla?
- Graafihaku vaikka shakkitehtävä siirroista?
- https://projecteuler.net/problems
- Vaikeaa, mutta parseri joka ymmärtää polynomeja


Indices and tables
==================

* :ref:`genindex`
