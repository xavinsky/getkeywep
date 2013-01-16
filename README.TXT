#########
GetKeyWep
#########

Some smalls scripts for get key wep.
I use it with my old eeepc on debian.
My Eeepc have this chipset wifi :
Atheros Communications Inc. AR242x 802.11abg Wireless PCI Express Adapter (rev 0)
[168c:001c (rev 01)]


INSTALL
=======

::

    # install sources
    cd /usr/src
    mkdir software
    cd software
    git clone https://github.com/xaviermanach/getkeywep.git
    cd getkeywep
    # verify there is not other w* program in /usr/local/sbin
    ls /usr/local/sbin/w*
    # install in /usr/local/sbin
    cp w* /usr/local/sbin

UNSTALL
=======

::

    # verify there is not other w* program in /usr/local/sbin
    cd /usr/local/sbin
    rm -Rf w*

USE
===

::

    # help
    wh

    # create ath1 with monitor mode and start global scan
    w1

    # if existe open network essid=REZOOPEN, connect with :
    wf REZOPEN

    # listen in a terminal
    w2 ESSID CHANEL

    # inject in another terminal
    w3 ESSID CHANEL
    # ou version fast injection
    w3f ESSID CHANEL 
    # ou version injection avec option
    w3b ESSID CHANEL OPTION

    # when you have enouth data 30000 (68k) or 10000 (128k)
    # calculate wep key
    w4

    # connect with key wep
    wfp ESSID KEYWEP

    ## optional : change mac for connection
    wm <MAC>

    ## optional : change mac for sniff
    wms <MAC>
