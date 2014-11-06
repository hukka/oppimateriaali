.. Yläkoulun ohjelmointia master file, created by
   sphinx-quickstart on Sun Nov  2 16:08:59 2014.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Yläkoulun ohjelmointia!
=======================

.. todo:: Tehtäville voisi luoda oman komennon, jotta niistä saa oman listauksen

.. todo:: Minne mallivastaukset?

.. todo::

    Racketille oma Sphinx-domain, jotta peruskomennot linkittyisi suoraan docs.racket-lang.orgiin:
    (http://docs.racket-lang.org/search/index.html?q=scene%20O:{%20L:lang/htdp-beginner%20M:2htdp%20}).
    https://bitbucket.org/klorenz/sphinxcontrib-domaintools varmaankin auttaa.
    Voi olla, että vaatii ctags-tuen Racketille pygmentsin kautta.

Ohjelmoinnin käsitteitä (esitietovaatimuksia):

.. toctree::
   :maxdepth: 2

   sanasto
   miksi-koodata
   ops2016
   perusasiat
   laskujärjestys
   omat_funktiot
   animaatiot-1
   ehtolauseet
   testaus
   structit
   interaktiivisuus
   listat
   rekursio


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
- Jonkinlainen tehtävä, jossa ohjelma hakee automaattisesti dataa webistä


Indices and tables
==================

* :ref:`genindex`
