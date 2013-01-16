#########
GetKeyWep
#########

Petits scrips pour recuperer une clef wep.
J'utilise mon vieux eeepc sur debian.
Mon Eeepc a le chipset wifi suivant :
Atheros Communications Inc. AR242x 802.11abg Wireless PCI Express Adapter (rev 0)
[168c:001c (rev 01)]


INSTALLATION
============

::

    # recuperation des sources
    cd /usr/src
    mkdir software
    cd software
    git clone https://github.com/xaviermanach/getkeywep.git
    cd getkeywep
    # verifier que vous avez pas installer d'autres scripts w* dans /usr/local/sbin
    ls /usr/local/sbin/w*
    # installer
    cp w* /usr/local/sbin

DESINSTALLATION
===============

::

    # verifier que vous avez pas installer d'autres scripts w* dans /usr/local/sbin
    cd /usr/local/sbin
    rm -Rf w*

USE
===

::

    # aide
    wh

    # créer ath1 en mode monitor et lance scan global
    w1

    # Si il existe un reseau ouvert essid=REZOOPEN :
    wf REZOPEN

    # lancer l'écoute sur une console
    w2 ESSID CHANEL

    # lancer l'injection sur une autre
    w3 ESSID CHANEL
    # ou version fast injection
    w3f ESSID CHANEL 
    # ou version injection avec option
    w3b ESSID CHANEL OPTION

    # lorsque vos data atteigne 30000 (68k) ou 10000 (128k)
    # calculer la clef a partir de la capture.
    # w4

    # connexion avec la clef wep 
    wfp ESSID KEYWEP

    ## eventuel changement de mac client pour la connection
    wm <MAC>

    ## eventuel changement de mac client pour le sniff
    wms <MAC>
