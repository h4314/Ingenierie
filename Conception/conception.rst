



Objectifs : conception et définition d'un  nouveau système


Modèle du domaine
=================

que ce soit manuel ou automatisé

Architecture matérielle
=======================

Site central
------------

poste de travail, serveur, BDD etc.

Sites distants
--------------


Architecture applicative
========================

Site central
------------

Sites distants
--------------

Architecture de communication
=============================

Cette partie va détailler l'architecture de communication, en se basant sur des
scénarios (nominal ou alternatifs).

Flux d'information
------------------

Cas nominal
___________

Toute les noeuds du réseau de capteur sont en sommeil profond, consommant ainsi très peu d'énergie.
Lorsqu'un noeud se réveille, il fait l'acquisition de *n* valeurs, à raison
d'une valeur toute les *x* secondes.  Il fait alors un filtrage sur ces *n*
valeurs, et envoie au noeud *MASTER* un trame de ce type : ::

    moyenne\n
    max\n
    min\n
    ecart-type\n 

Une trame de ce type permet, sans surcharger le réseau, de rendre compte des
éventuelles erreur (min et max très différent de moyenne). Une fois que cette
trame a été envoyée, le noeud place son timer de réveil à *y* unité de temps, et
se met en sommeil (profond ou de reception, dépendant de sa place dans le réseau
maillé), pour consommer très peu.

Quand le noeud *MASTER* reçoit une trame, il peut identifier le noeud grâce à
son adresse dans le protocole ZigBee. Il envoie alors une trame de ce type, au
central, par GPRS : ::

    <SiteData id=iiii>
        <Sensor id=xxxx>
            <Record time=kkkk>
                <avg> yyyy </avg>
                <max> zzzz </max>
                <min> uuuu </min>
                <sdev> vvvv </sdev>
            </Record>
        </Sensor>
    </SiteData>

Le noeud *MASTER*, pour plus d'efficacité, procède par fenêtre de temps pour
l'envoie par GPRS. Ainsi, il attend de collecter quelque trames (le temps
pendant lequel le noeud *MASTER* attend de recevoir des trames étant
paramétrable) avant d'envoyer d'un coup tous les enregistrement.

Les raison justifiant ce comportement sont l'efficacité, et la consommation en
énergie. En effet, tout d'abord, plus nous avons de données à envoyer, plus une
compression des données sera efficace, ce qui réduira la bande passante à
utiliser, qui est un composant critique, d'autant plus que les données sont sous
format XML, donc supportant très bien la compression : pour un fichier d'environ
15000 mesure (````record````) encodé dans le format XML ci-dessus, le fichier
brut fait 1.5Mo, alors qu'il le fait plus que 60Ko une fois compressé en bzip2.
Ensuite, le coup de mise en route d'un connexion GPRS est probablement important
en terme de calcul, d'émission radio, et donc de consommation.

Cas alternatifs
_______________

Panne temporaire de réseau GPRS
    Si le noeud *MASTER* a une panne temporaire de réseau GPRS, il stock dans une mémoire de masse les données reçues par le noeud. Il ne sera pas nécessaire d'avoir une mémoire de masse trop importante, puisque les données ne sont en fait que collectés assez rarement, et, une fois compressées, prennent peu de place en mémoire.

Envoie d'une commande de changement de paramètre
    Lorsque le site central désire changer un paramètre à distance sur un noeud, il envoie une trame respectant ce format : ::

        <ParamChange>
            <Node id=xxxx>
                <Key>yyyy</Key>
                <Value>zzzz</Value>
            </Node>
        </ParamChange>

    
    Il est ainsi possible de changer les paramètre pour plusieurs capteurs à la
    fois, au sein d'un même site.


Mise à jour système
    Lorsque le site central désire changer le système d'un des noeuds, il envoie
    une trame respectant ce format : ::

        <SystemUpdate>
            <Node id=xxxx>
                <Data version=xxxx>
                    hfjOW+n70kqDj9vyHBMTVX1mNaQFUfnsUZ/Kaoo6M2sKOYE+aMAdo
                    VSea426VvtR+pggWk0mirulRRxY+aVqXn6ql3+lShV1ABiPnvaUn/
                    ZA7JdQEH6GiMw/FpNb63Z+j4+LYx8sqKOfXuW5YF70a+tuuKkiUCP
                    /FYP7o79whAqVsE3n+FP6mJkCyAZQbr+7EenOhktvCZHy83e1a/0w
                    Xa40Fdcv9YI9OTG7Fy8rF0nB1SJZ5WQ10EwHhISWxqLxNx7tn5KaF
                    B57xvhSQmLni/A8VMzT+wCcr6VEUo0pD8SzqbYEfVrhCY7jG1Wksd
                    mA0WpuOr5aHtL43X3OosVZ6Lcwtj/nYMCVVLQhaE9+Pt0W173A+bF
                    3j95FmtMf9aU/reXNx++yFANxSe1o43gu/qDRuT6AF02hX9YWVsaW
                    F/VeblQPLtcxSgFVeggLPIteIcRJBbiFgXmMqIJN0Xv2w8ZMKy6bN
                    MCvKtncT2/tgSKGzIGsvh7GkrzuDDvVEV8HrAfBhqklkbrWVscyRx
                    JTvWVwm3sL97MbPVQhPGtuCPLvxlgci4mhzP8QtYGLs/V6VK44oa4
                    QnY9Pee53aaqA7QbgIal6GOg7oYtf24u63pZYa44d7NHol88eXt+L
                    F1kKnvFhzaqVkn04il895R3Ta+NS6WmHHDa3DQYXc7Bphs3MLs0yM
                    dBNJMRXCk+9X/vpUuPLyH5H+lTPvWWqH3m6oBSbZHMPid8pUbxQIH
                    NP0JsvSv9dt27goPR3jSvhAtY6XtfXa3Y7t8NKNY1YDs51d6dwwuc
                    6oAjc4FA1JSCWDZFc4UwnJUCOOTwDlLG7XuVvDOH+BBscD3NmhuPN
                    nhnGJGj6ReDAzSzTXic0qNGROsSwravfvL2dB15jZAc1q+PqPVa2j
                </Data>
                <CheckSum type='SHA-512'>
                    b4c4cef348831c6a623fa395a3dbb47966972d33220b66ef2629d
                </CheckSum>
            </Node>
        </SystemUpdate>


    La partie entre les balises <Data> est encodée en base 64, permettant de
    transmettre des données binaires sous forme de texte. Un checksum est fourni
    pour vérifier l'intégrité des données, une mise à jour de ce type étant
    critique. Si les sommes de contrôle diffère, la mise à jour ne sera bien sûr
    pas appliquée.


Stockage
--------
stockage, volumétrie/dimensionnement


Architecture complète 
=====================

_a voir si on la déplace avant ?_

Annexes 
=======

Problématique sur la sécurité
------------------------------

sécurité, anomalies
etudes des pannes, arret urgence, erreurs, reprises sur erreur

Démarrage du système
---------------------

telechargement/lancement de l'application
mise à jour

Problématique de mise à l'échelle
----------------------------------

dimensionnement, généricité, etc.

Analyse de la complexité
-------------------------

où seront les difficultés et pourquoi ?




