====================================
Spécifications Technique des Besoins
====================================


1. Axes d'amélioration
#######################

Ce document a pour objectif de détailler les besoins du nouveau système. Ces exigences sont basées sur les axes d'améliorations provenant de l'analyse de l'existant. 

L'objectif premier est d'effectuer des économies en termes de coûts directs car le système doit être appliquer massivement à travers l'Europe.

   * Centralisation de la surveillance : économies d'échelle.
   * Une meilleure logistique, notamment en termes de transport.
   * Des ressources humaines mieux utilisées. Les opérationnels doivent passer moins de temps à la surveillance (faible valeur ajoutée) pour se concentrer sur leur métier.

Un deuxième objectif se situe aux niveau de la des réductions de coûts indirects par une qualité de surveillance accrue.

   * Un meilleur contrôle des risques environnementaux
   * Un gaspillage des ressources réduit au minimum (énergie, déchets, contenant des cuves)
   * Anticipation des problèmes
   * Automatisation de la surveillance, fiabilité augmentée
   * Une meilleure traçabilité des opérations
   * Une aide à la décision à partir des données collectées

2. Exigences fonctionnelles 
############################

FO-1 Monitoring à distance
==========================

Un des enjeux majeur de ce nouveau système est sa capacité à surveiller à distance l'état des sites. Cette surveillance sera donc possible à partir du site central mais aussi via d'autres plateformes décentralisées que ce soit des postes fixes ou des appareils mobiles de type smartphone utile pour les opérationnels.

FO-1-a Monitoring de l'état des cuves
``````````````````````````````````````

Il est possible de connaître l'état de chaque cuve d'une station distante, c'est à dire d'être capable de lire en temps réel les valeurs de chacun de ses capteurs. Les lectures de données doivent être facilitées par la mise à disposition de valeurs de références : valeur minimale, valeur maximale, seuils d'alertes, type de mesure, date de la dernière mise à jour, etc.

FO-1-b Monitoring des anomalies
````````````````````````````````

Les sites distants doivent informer le site central de toute anomalie encourue. Les anomalies peuvent être liées à différents types de dysfonctionnement :

 - un capteur ne fonctionne plus
 - un capteur renseigne des valeurs incohérentes
 - une cuve ne transmet plus d'informations au noeud maître

De plus le site central doit être capable de détecter une perte de communication avec un site distant.

FO-1-c Localisation géographique
````````````````````````````````

Les stations doivent être localisable géographiquement tout comme les cuves. La majorités des cuves étant immobiles, cette fonctionnalité sera facile à mettre en place. Cependant certaines cuves pourraient potentiellemnt être mobiles et ce cas devrait donc être pris en compte. 

FO-2 Maintenance à distance
===========================

La partie logicielle doit pouvoir être maintenu depuis le site central, c'est à dire qu'il ne sera pas nécessaire d'envoyer du personnel pour effectuer une mise à jour du logiciel, le paramétrer ou bien pour analyser son fonctionnement.

Concernant la partie matérielle, bien qu'impossible d'être maintenue à distance, elle doit comporter des mécanismes d'alarmes et d'indicateurs qui peuvent maintenir informé le site central de toute anomalie encourue ou bien lorsque des problèmes peuvent être anticipés (exemple : niveau de batterie faible).

FO-3 Maintenance sur site
=========================

Chaque site doit posséder des moyens de connexion au système pour qu'un opérationnel puisse monitorer le fonctionnement sur place. Il pourra à la fois lire les informations circulant sur le réseau interne (données des capteurs, état des cuves, état du réseau, etc.) et effectuer des opérations de maintenance : relance du système, paramétrage, mise à jour logicielle ou maintenance matérielle. Dans ce dernier cas il convient de rendre le matériel facilement accessible.

FO-4 Traitements sur site central
=================================

FO-4-a Aggrégation des données provenant des sites centraux
``````````````````````````````````````````````````````````` 

Le site central doit pouvoir stocker de manière structurée l'ensemble des données émises par les sites distants.

FO-4-b Planification des interventions
```````````````````````````````````````

A partir des données relevées, le système doit pouvoir générer des plannings d'intervention. Les interventions peuvent être de type :

 - affectation d'un opérationnel pour une maintenance logicielle ou matérielle 
 - envoi d'un camion pour effectuer un ravitaillement ou un enlèvement sur un ou plusieurs sites

L'objectif ici est d'optimiser la logistique, notamment grouper les opérations pour rentabiliser les déplacements au maximum : ravitailler plusieurs sites en un trajet et essayer d'optimiser les chargements d'un camion. Dans l'idéal un camion doit transporter sa charge maximale et l'utiliser totalement. Certains camions pourraient également être toujours pleins, que ce soit à l'aller et au retour dans le cas où les ravitaillement et enlèvement peuvent être compatibles.

La planification est donc basée sur la posibilité de définir des routes de maintenance entre diverses cuves et zones homogènes.

La planification inclut des sous fonctionnalités :

 - Gestion des prestataires : fournisseurs externes
 - Gestion de la disponibilité des opérationnels

FO-4-c Suivi en temps réel des interventions
`````````````````````````````````````````````

Les interventions doivent être localisables en temps réel : il est possible de connaître la position géographique exacte des opérationnels et des camions, ces derniers ayant bien souvent un système de balise GPS intégré.

FO-4-d Aide à la décision
```````````````````````````

L'objectif, ici, est d'utiliser les connaissances accumulées depuis la mise en service du système afin d'améliorer son efficacité : accroissement de la qualité de service et réduction des coûts. Il s'agit donc de générer des statistiques globales, par sites et par cuves sur lesquelles les opérationnelles pourront se baser pour prendre des décisions. Mais il s'agit d'aller plus loin : proposer aux opérationnels des axes d'améliorations en mettant en relief les dysfonctionnements, les goulets d'étranglement ainsi que des moyens d'anticiper les problèmes.

FO-5 Traitements sur station
============================

FO-5-a Relevé des capteurs
````````````````````````````

Chaque cuve doit posséder au minimum un capteur d'acquisition de données lié au contenu de la cuve (exemple : niveau de profondeur). 

FO-5-b Uniformisation des données
``````````````````````````````````

Les données relevées sur par les capteurs doivent être uniformisées sous un protocole fixé.

FO-5-c Circulation de l'information sur le réseau interne
`````````````````````````````````````````````````````````

Les données des noeuds esclaves doivent circuler de noeud en noeud jusqu'au noeud maître.

FO-5-d Communication de l'information vers le site central
```````````````````````````````````````````````````````````

Le noeud maître se chargera de transformer puis communiquer les données de l'ensemble des cuves de la station au site central.

FO-5-e Optimisation de la gestion de l'énergie
```````````````````````````````````````````````

Chaque élément du site distant : capteur, noeud esclave et maître devront comprendre des moyens d'optimisation de l'énergie : mise en veille provisoire, etc.


FO-6 Traçabilité
================

Le système doit archiver tout un ensemble d'évènements :

- arrivée d'informations provenant des sites distants : données de capteur, anomalies, rapport de maintenance sur site distant etc.
- ensemble des actions prises par les différents acteurs : opérations de maintenance, ravitaillement/enlèvement du contenu d'une cuve, etc.


3. Priorisation des exigences fonctionnelles

Certaines fonctionnalités sont à prévoir immédiatement tandis que d'autres peuvent être considérées comme moins prioritaires car complexes ou impactant faiblement les axes d'améliorations. Il convient donc de les classer en deux lots.

Lot 1 - Besoins immédiats
==========================

Ces fonctionnalités doivent être implémentées dès la première version du système car elles sont considérées vitales pour un fonctionnement global. De plus elles prennent en compte fortement les axes d'amélioration retenus.

 - FO-1 Monitoring à distance
	- FO-1-a Monitoring de l'état des cuves
 	- FO-1-b Monitoring des anomalies
 - FO-2 Maintenance à distance
 - FO-3 Maintenance sur site
 - FO-4 Traitements sur site central
 	- FO-4-a Aggrégation des données provenant des sites centraux
 	- FO-4-b Planification des interventions
 - FO-5 Traitements sur station
	- FO-5-a Relevé des capteurs
	- FO-5-b Uniformisation des données
	- FO-5-c Circulation de l'information sur le réseau interne
	- FO-5-d Communication de l'information vers le site central
 - FO-6 Traçabilité
  
Lot 2 - Besoins à long terme
=============================

Ces fonctionnalités pourront être implémentées dans un deuxième temps car elles ne sont pas vitales pour la création d'un système fonctionnel. Elles sont souvent complexes et donc longues à mettre en place. De plus elles ne répondent que faiblement aux axes d'amélioration.

 - FO-1 Monitoring à distance
 	- FO-1-c Localisation géographique
 - FO-4 Traitements sur site central
 	- FO-4-c Suivi en temps réel des interventions
	- FO-4-d Aide à la décision
 - FO-5 Traitements sur station
	- FO-5-e Optimiser la gestion de l'énergie

4. Exigences non fonctionnelles

Sont définies ci-après les besoins non fonctionnelles classés par ordre d'importance. Ils proposent la mises en place de contraintes et de bonnes pratiques à appliquer sur les fonctionnalités énoncées ci-dessus. Dans un deuxième temps, il conviendra d'établir un tableau croisé des fonctionnalités et des contraintes non fonctionnelles à respecter pour chacune d'elles.

4.1. Intégration de l'existant 
==============================

================

===============

Les aquisitions faites par les capteurs des cuves doivent être sures. Il conviendra donc d'effectuer une série de mesures pour déterminer la valeur réelle de la mesure captée et donc d'éviter la prises en compte de valeurs extraordinaires.
===================================

================================

De plus, afin d'éviter ces problèmes de maîtrise, les équipements seront choisis chez des fournisseurs de confiance et les technologies devront généralement être open source avec une forte communauté. L'objectif est de garder un maximum de contrôle tout en évitant de voir la technologie et donc son support disparaître.
================

Les données provenant des mesures effectuées par les capteurs seront uniformisées au plus tôt, dès le noeud esclave pour garantir une communication de données homogènes à travers le réseau interne et pour éviter les impacts aux couches supérieurs : noeud maître et site central. Il en va de même pour les communications longues distantes, celles-ci devront utiliser des protocles standards et des structures de données génériques. Le site central et les stations distantes devront fournir des interfaces de communication définies et génériques, abstraites du système sous-jacent. Globalement le développement tiendra compte de ces contraintes par la systémisation d'une architecture en couches et en modules interchangeables. A visée européenne, le logiciel devra être disponible sous l'ensemle des langues des pays concernés.
==================

===============

=================



Fonctionnement global du système
##################################

_ TODO: faire un schema global du systeme _

Bilan des améliorations
#########################

Au final le nouveau système présente l'avantage de répondre en grande partie aux axes d'améliorations selectionnés en collaboration avec Copevue. Il répondra donc aux exigences de centralisation de la gestion des sites, de réduction des coûts et d'augmentation de la qualité du monitoring.




