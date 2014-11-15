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


Ohjelmoinnin käsitteitä (esitietovaatimuksia):

.. toctree::
   :maxdepth: 2

   sanasto
   miksi-koodata
   ops2016
   perusasiat
   laskujarjestys
   omat_funktiot
   animaatiot-1
   ehtolauseet
   suunnittelu
   structit
   interaktiivisuus
   listat
   rekursio
   paikalliset_maaritelmat


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
   graafit


Ideoita

- Luvun ja numeron ero, 5 ja V ovat samoja lukuja, mutta eri kirjoitusjärjestelmän
  numeroita. Racketissä 42 ja "42" tarkoittavat lukua ja numeroista koostuvaa tekstiä.
- "Perehdytään lukujen jaollisuuteen ja opitaan jakamaan luku alkutekijöihin"
  Tehdään ohjelma, joka etsii alkulukuja ja jakaa lukuja tekijöihinsä
- "Vahvistetaan ymmärrystä tarkan arvon ja likiarvon erosta sekä pyöristämisestä."
  Jakolaskuja muilla kuin kahdella ja viidellä, ja sitten takaisin kertomista.
- "Opitaan neliöjuuren käsite ja käytetään neliöjuurta laskutoimituksissa"
  Pythagoras kaikissa etäisyyttä vaativissa 2D- ja 3D-animaatioissa
- "Syvennetään oppilaan taitoa tutkia ja muodostaa lukujonoja."
  Fibonacci
- Livecoding-moduuli extemporella (musiikki)
- Livecoding-moduuli fluxuksella
- Robottimoduuli EV3:lla
- binäärihaku, esimerkiksi funktion nollakohdalle
- jotain numeeristä integrointia trapezoideilla?
- Jokin graafi ja siinä haku? Vaikka paikkakuntien etäisyydet ja reitin etsintä.
  Tai graafinmuodostusta jopa... vaikka shakkitehtävä siirroista?
- https://projecteuler.net/problems


Indices and tables
==================

* :ref:`genindex`
