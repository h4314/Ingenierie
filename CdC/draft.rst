====================================
Spécifications Technique des besoins
====================================


Axes d'amélioration
####################

Ce document a pour objectif de détailler les besoins du nouveau système. Ces exigences sont basées sur les axes d'améliorations provenant de l'analyse de l'existant. 

L'objectif premier est d'effectuer des économies en termes de coûts directs car le système doit être appliquer massivemnt à travers l'Europe.

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

Exigences fonctionnelles 
########################

FO-1 Monitoring à distance
==========================

Un des enjeux majeur de ce nouveau système est sa capacité à surveiller et contrôler à distance l'état des sites. Cette surveillance sera donc possible à partir du site central mais aussi via d'autres plateforme décentralisés que ce soit des postes fixes ou des appareils mobiles de type smartphone utile pour les opérationnels.

FO-1-a Monitoring de l'état des cuves
``````````````````````````````````````

Il est possible de connaître l'état de chaque cuve d'une station distante, c'est à dire d'être capable de lire en temps réel les valeurs de chacun de ses capteurs.

FO-1-b Monitoring des anomalies
````````````````````````````````

Les sites distants doivent informer le site central de toute anomalie encourue. Les anomalies peuvent être liées à différents types de dysfonctionnement :

 - un capteur ne fonctionne plus
 - un capteur renseigne des valeurs incohérentes
 - une cuve ne transmet plus d'information au noeud maître

De plus le site central doit être capable de détecter une perte de communication avec un site distant.

FO-1-c Localisation géographique
````````````````````````````````

Les stations doivent être localisable géographiquement tout comme les cuves. La majorités des cuves étant immobiles, cette fonctionnalité sera facile à mettre en place. Cependant certaines cuves pourraient potentiellemnt être mobiles et ce cas devrait donc être pris en compte. 

FO-2 Maintenance à distance
===========================

La partie logicielle doit pouvoir être maintenu depuis le site central, c'est à dire qu'il ne sera pas nécessaire d'envoyer du personnel pour effectuer une mise à jour du logiciel, le paramétrer ou bien pour analyser son fonctionnement.

Concernant la partie matérielle, bien qu'impossible d'être maintenue à distance, elle doit comporter des mécanismes d'alarmes et d'indicateurs qui peuvent maintenir informé le site central de toute anomalie encourue ou bien de lorsque des problèmes peuvent être anticipés.

FO-3 Maintenance sur site
=========================

Chaque site doit posséder des moyens de connexion au système pour qu'un opérationnel puisse monitorer le fonctionnement sur place. Il pourra à la fois lire les informations circulant sur le réseau interne (données des capteurs, état des cuves, état du réseau, etc.) et effectuer des opérations de maintenance : relance du système, paramaétragen mise à jour logicielle ou maintenance matérielle. Dans ce dernier cas il convient de rendre le matériel facilement accessible.


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

 - Gestion des fournisseurs externes
 - Gestion de la disponibilité des opérationnels

FO-4-c Suivi en temps réel des interventions
`````````````````````````````````````````````

Les interventions que ce soit par les camions 

FO-4-d Aide à la décision
```````````````````````````

statistiques
améliorations
anticipations des problèmes

FO-5 Traitements sur station
============================

FO-5-a Relevé des capteurs
````````````````````````````

FO-5-b Uniformisation des données
``````````````````````````````````

FO-5-c Circulation de l'information sur le réseau interne
`````````````````````````````````````````````````````````

FO-5-d Communication de l'information vers le site central
```````````````````````````````````````````````````````````

FO-5-e Optimiser la gestion de l'énergie
``````````````````````````````````````````

FO-6 Traçabilité
================

Le système doit archiver tout un ensemble d'évènements :

- arrivée d'informations provenant des sites distants : données de capteur, anomalies, rapport de maintenance sur site distant etc.
- ensemble des actions prises par les différents acteurs : opérations de maintenance, ravitaillement/enlèvement du contenu d'une cuve, etc.


Priorisation des exigences fonctionnelles##########################################

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

Ces fonctionnalités pourront être implémentées dans un deuxième temps car elles ne sont pas vitales pour la création d'un système fonctionnelle. Elles sont souvent complexes et donc longues à mettre en place. De plus elles ne répondent que faiblement aux axes d'amélioration.

 - FO-1 Monitoring à distance
 	- FO-1-c Localisation géographique
 - FO-4 Traitements sur site central
 	- FO-4-c Suivi en temps réel des interventions
	- FO-4-d Aide à la décision
 - FO-5 Traitements sur station
	- FO-5-e Optimiser la gestion de l'énergie

Exigences non fonctionnelles############################


 * _reprendre les exigences non fonctionnelles de l'AO et les classer_
 * ne pas oublier les besoins d'interfaces, de communication et de stockage


1) Intégration de l'existant Nous devons communiquer avec les exploitants qui s'occupent de l'entretien des stations. Il s'agit donc d'optimiser leurs interventions en rationnalisant la surveillance.2) Robustesse Les stations doit être protégées correctement pour supporter des conditions climatiques extrêmes dans certaines régions. Le système embarqué doit pouvoir revenir à un état stable en cas de reprise.3) Fiabilité On doit éviter toute intervention humaine vis à vis du système. Il doit disposer de mécanismes garantissant leur fonctionnement en continu.4) Evolutivité et maintenabilité Le système peut être amené à évoluer au niveau dimentionnel, fonctionnel et matériel. Il faut donc veiller à l'organiser en sous-systèmes, au comportement normalisé, et qui pourront donc être ajouté, modifiés, ou retiré par la suite sans impacter le système global. Il faut définir les couches lors du développement de l'application pour faire en sorte que le système soit le plus indépendant possible du matériel. 5) Limitations technologiques Le système repose sur certaines technologies dont nous ne maîtrisons pas le fonctionnement (par exemple, le GSM). Il faut donc considérer la différence entre les technologies internes et externes.6) Généricité Notre système doit être conçu à pouvoir décliner à moindre coût pour d'autre applications de type surveillance. Les applications sont nombreuses, mais le fonctionnement global est souvent proche. L'organisation de notre solution doit donc faire abstraction du domaine d'application. Nous pouvons prévenir certains modules changeables.7) Réutilisation Les techniques emplyées ne sont pas fondamentalement nouvelles, nous pouvons donc en profiter pour réutiliser des composants qui ont fait leur preuve. Symétriquement, il faut que les composants de notre propre système puissent être réutilisés à leur tour.8) Ergonomie Le système s'adresse à des non informaticiens, il faut donc que l'interface s'adapte à l'utilisateur et que ce soit facile et convivial pour exploiter le système. Le besoin d'apprentissage doit être minimisé. Il faut aussi assurer la qualité de l'interface sur un appareil portable de type PDA, afin de faciliter son utilisation sur le terrain.9) Traçabilité Le serveur central, qui est en communication avec l'ensemble du système, doit garder une trace de toutes les informations qui transitent et les états de fonctionnement de chaque station. Du côté des stations, les systèmes embarqués doivent également assurer une traçabilité indépendante du serveur en cas de communications impossible ou d'erreurs graves."scale"; value: u'50%')


Fonctionnement global du système
##################################

_ TODO: faire un schema global du systeme _

Bilan des améliorations
#########################

Au final le nouveau système présente l'avantage de répondre en grande partie aux axes d'améliorations selectionnés en collaboration avec Copevue. Il répondra donc aux exigences de centralisation de la gestion des sites, de réduction des coûts et d'augmentation de la qualité du monitoring.





