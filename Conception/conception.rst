


Objectifs : conception et définition d'un  nouveau système


Modèle du domaine
=================

_que ce soit manuel ou automatisé_

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

Flux d'information
------------------

Scénarios :
Acquisition d'une valeur sur un capteur jusqu'au stockage de la donnée sur le site central



scénario autres : envoie d'une commande, mise à jour, anomalie, etc.
Régles de gestion (ex: alarmes, etc.)
structures de données/format, protocole

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

* On travaillera avec le réseau GPRS pour réaliser la communication entre les différentes sites. Comme on le sait très bien, la technologie GPRS n’est pas vraiment fiable à 100%, on fera tout le possible afin d’anticiper les éventuels difficultés qui pourraient survenir au cours de l’exploitation.

* Les ressources des systèmes embarqués sont un peu limitées, On réalisera le développement du système de tel façon qui soit optimisé pour que cette limite ne soit pas un empêchement au bon fonctionnement du logiciel.


