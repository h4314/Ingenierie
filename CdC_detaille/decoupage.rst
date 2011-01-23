=========================
Découpage en sous-projets
=========================

Macro découpage
###############

La réussite du projet passera par une découpe adéquate du système global en sous-systèmes. Chaque sous-système représente un ensemble cohérent : compétences requises, technologies, importance et ordre dans le projet.
Le découpage a été réalisé de manière à ce que chaque sous-système puisse être réalisé indépendamment des autres au sein d'un sous projet. Le but est de tester le sous-système une fois qu'il est prêt et de limiter les risques en termes d'intégration.

4 sous-systèmes principaux sont dégagés :

- A - Site central
- B - Site distant
- C - Communication entre le site central et les sites distants
- D - Accompagnement de projet


Découpage détaillé
###################

A - Site central 
================

A1 - Infrastructure matérielle
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Choix, installation, configuration et interconnection des équipements matériels : serveurs webs, serveurs de base de données, serveurs de sauvegarde, pare-feux, intranet, postes de travail, etc.

A2 - Harmonisation du développement logiciel
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

L'ensemble des projets logiciels suivants ou modules (A3 à A8) doivent s'appuyer sur un référentiel unique et ce afin de de garder une cohérence (notamment au niveau des IHM) mais surtout dans un souci de réutilisabilité et de fiabilité. Il s'agit dans ce projet d'établir les grands choix en termes de développement (environnements de développements, langages, librairies, normes, etc.). Il est nécessaire, par exemple, que chaque projet suivent les mêmes pratiques aux niveaux de :
- la couche des données
- la couche applicative
- la couche de présentation. Les IHM doivent être cohérente en terme de designe et d'utilisabilité à travers les modules.

Les livrables de ce projet sont donc des outils, des méthodes, des normes et des documents (ex : PAQL).

A3 - Gestion des données
~~~~~~~~~~~~~~~~~~~~~~~~~

Problématiques de stockage, de volume, de sécurité et de traçabilité des données.

A4 - Monitoring
~~~~~~~~~~~~~~~~

Suivi en temps réel de l'activité des stations et des cuves. Gestion des évènements exceptionnels.

A5 - Commandement des sites distants
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Paramétrage et mise à jour des logiciels à distance.

A6 - Logistique
~~~~~~~~~~~~~~~~

Planification des convois de maintenance. Gestion des prestataires.

A7 - Aide à la décision
~~~~~~~~~~~~~~~~~~~~~~~~

Exploitation des données historiques pour résoudre diverses problématiques : anticipaction des incidents, amélioration continue du système, etc.

A8 - Suivi temps réel des opérations de maintenance
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Suivi géotemporel des actions de maintenance que ce soit par les camions ou les opérationnels.

B - Site distant
=================

B1 - Développement logiciel
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- Acquisition et traitement des données bruts sur noeud esclave
- Communication intra-site (entre les noeuds)
- Traitement des données collectées sur noeud maître 
- Portage des couches de présentation des modules du site central sur appareils mobiles (PDA, smartphones)

B2 - Infrastructure matérielle 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Pour chaque station :

- Installation capteurs
- Installation noeuds esclave
- Installation du noeud maître

C - Communication entre le site central et les sites distants
==============================================================

C1 - Définition du protocole de communication
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Protocoles, structures de données, exceptions, communication satellite pour zones extrêmements isolées, etc.

C2 - Interface de communication site central
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Développement des services webs et configuration sur site.

C3 - Interface de communication site distant
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Développement des services webs et configuration sur site.

D - Accompagnement de projet
==============================

Ce projet est beaucoup plus transversal que ne l'est les précédents.

D1 - Aide dans la démarche de Copevue
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Support technique dans le discours de Copevue dans l'optique de fédérer un maxiumu de pays et d'organisation d'Europe.

D2 - Projet pilote
~~~~~~~~~~~~~~~~~~~

L'enjeu du projet est de démontrer avec un échantillon que le système peut être effectué à l'échelle européenne. Cela passe par la mise en place d'un site central fonctionnel et d'un site distant. Cette cible pilote servira de base pour répliquer les méthodes de déploiement de d'alignement sur d'autres sites.


D3 - Formation
~~~~~~~~~~~~~~~

Préalabelement à la mise en exploitation du système des formations de personnels devront être effectués que ce soit du côté des futurs opérateurs du site central que des différents acteurs existants : opérationnels et prestataires. Il s'agit également de fournir des supports de documentation et d'aide appropriés.

Planning prévisionnel
######################

gantt ? estimation fin projet ?

