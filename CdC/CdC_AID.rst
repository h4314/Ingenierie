###############################################################
Cahier des charges détaillé du sous-projet "Aide à la décision"
###############################################################

.. contents:: Sommaire
.. sectnum::

Introduction
=============
Présentation du projet
----------------------
	Le sous-projet "Aide à la décision"  correspond à une partie annexe dans le projet. Cette partie a pour but d'exploiter au maximum les données que possède le système et en tirer des conclusion et des améliorations. Bien qu'annexe au système mis en place, ce sous-projet reste indispensable à une exploitation efficace.

Présentation du document
------------------------
	Ce document est un cahier des charges détaillé, c'est-à-dire qu'il décrit de manière précise le système en question, afin de pouvoir aborder la phase de développement en connaissant exactement ce qu'on attend du produit.


Présentation du problème
========================
Objectifs, principe du logiciel
--------------------------------
	Le système récolte et stocke les données d'état de fonctionnement de toutes les stations. Ces données sont potentiellement très intéressantes à analyser. Ce logiciel est utilisé par l'administrateur du système et des managers au niveau décisionnel de définir des indicateurs pour surveiller le fonctionnement du système à moyen et à long terme. Par exemple, en visualisant le niveau de liquide dans une cuve sur un an, nous pouvons détecter des dysfonctionnements comme une fuite et effectuer des maintenances préventifs. Nous pouvons faire des comparaisons entre les sites afin de trouver un meilleur dimensionnement du système global.

Formulation des besoins généraux
---------------------------------
	Le programme permet de fournir une aide aux décisions prises par l'administrateur et superviseur du système au niveau opérationnel et stratégique.
	Le superviseur a besoin d'assurer le bon fonctionnement du système grâce à l'utilisation du logiciel. Il souhaite pouvoir surveiller les sites en mettant en relation les données situées sur une certaine plage de temps.
	L'administrateur du système a besoin de redimensionner et d'améliorer le système en continue. Pour cet objectif, il souhaite pouvoir comparer les sites entre eux au niveau d'efficacité, état de fonctionnement, coût etc.
	Le logiciel doit leur permettre de réaliser ces opérations et doit être simple d'utilisation.

Portée, développement, mise en œuvre, organisation de la maintenance
---------------------------------------------------------------------
	Les données sont hybergé dans la base de données au site central accédée également par d'autre applications. L'administration de cette base de données est centralisé.
	Le programme est utilisable depuis le client Web. Le développement de l'interface Web doit respecter la norme commune prédéfinie pour la partie interface de toutes les sous-projets. 
	Puisque offre aux utilisateur la possibilité de définir des indicateurs, le logiciel nécessite une maintenance particulière de manière continue assurée par un expert métier compétent en informatique afin d'étendre ses fonctionnalités et améliorer ceux existant.

Limites
--------
	Le système fournit au début quelques indicateurs prédéfinis selon les besoins initiales. Mais dans le file de temps, c'est à utilisateur de choisir des données qui les intéressent avec l'expert métier et d'en définir plus. Le logiciel se charge de présenter des données sous forme souhaité (Tableaux, Graphiques, Diagrammes etc) et fournir une aide à la décision des utilisateurs. Par contre, il n'a aucune intelligence de prendre des décision à la place des utilisateurs.

Exigences fonctionnelles
========================
Fonctions de base, performances et aptitudes
--------------------------------------------
Les fonctionnalités générales du logiciel se découpent en plusieurs parties:
 - L'expert métier crée des indicateurs en définissant le nom, les sources de données et la formule de calcul si nécessaire. ex. le niveau de liquide d'une cuve sur un an; le nombre d'interventions par station; 
 - On peut visualiser les valeurs de chaque indicateur dans les grilles de données.
 - On peut visualiser les graphiques ou les histogrammes de chaque indicateur
 - On peut générer un rapport personnalisé contenant des tableaux de valeurs et des graphiques
 
Contraintes d'utilisation
-------------------------
	Ce programme n'est utilisable que par le personnel qualifié et ayant un niveau de responsabilité suffisant. 

Critères d'appréciation de la réalisation effective de la fonction
------------------------------------------------------------------
	Les critères d'appréciation de ce logiciel est la facilité d'utilisation et la possibilité infini qu'il offre à COPEVUE d'exploiter au maximum les données selon leur souhaits. Cela facilitera la prise de décisions opérationnelles et stratégiques. 

Flexibilité, variation de coût associé
--------------------------------------
	Le logiciel est très flexible car l'utilisateur peut définir des indicateurs s'il le souhaite et choisir le format d'affichage de données. Le rapport est personnalisable.
	Il est relativement facile d'ajouter des modules pour des formats d'affichages supplémentaires ou de nouveaux type de fichier rapport.


Contraintes imposées, faisabilité technologiques et éventuellement moyens
=========================================================================
Sûreté, planning, organisation, communication
----------------------------------------------
	Dans un premier temps, une personne doit récolter des besoins auprès personnes concernées du COPEVUE. Plus précisément, quel sont les indicateurs qu'elles souhaitent au départ, quels sont les formats et les objets graphiques qu'elles préfèrent pour l'affichage.
	Ensuite une équipe devra s'occuper d'écrire les spécifications fonctionnelles du logiciel, en respectant la norme commune de l'interface web et de la base de données. 
	Lorsque les spécifications seront terminées, on pourra aborder la phase de développement. Pendant ce temps, il faut communiquer avec les futurs utilisateurs régulièrement pour demander leur avis sur l'avancement du projet et si la solution développé leur convient. Quand il y a des nouveaux besoins, il faut modifier ou ajouter des fonctionnalités. On devra également présenter l'interface web aux futurs utilisateurs avant de l'intégrer au développement.
	Après intégration, viendra la phase de test. Il faut assurer la connexion entre la base de données, le noyau applicatif et l'interface web. 


Complexité
----------
	Les parties complexes du développement de logiciel est la l'affichage des graphiques et génération de rapport en plusieur type de fichier.

Compétences, moyen et règles
----------------------------
	Nous avons besoins d'un expert métier compétent en informatique pour établir une bonne communication entre les personnels de COPEVUE et les développeurs. Il doit se charger de trouver des indicateurs efficaces qui permettent de détecter des dysfonctionnements et aider à la prise de décisions stratégiques. Il faut trouver une librairie, de préférence open source, pour générer des graphiques.
	
documentation
--------------
	La documentation, entièrement numérique, devra être mise à jour à chaque évolution du système, pour informer les utilisateurs des évolutions et des éventuelles modifications.
	Elle sera disponible en stand-alone sur un site dédié, et proposera des outils de recherche pour trouver la rubrique d'aide voulue. 

Configuration cible
====================
Matériel et logiciels
----------------------
Le matériel relié au logiciel est le serveur et la base de données centrale. Le logiciel doit pouvoir être compatible avec ces derniers, et être configuré pour travailler avec.
L'utilisateur se connecte avec un client web sur un autre poste disposé d'un navigateur web.

Interfaces
-----------
	L'interface du logiciel est composé de quatre onglets.	

- Gestion de l'indicateur : permet d'effectuer des opérations de création, MAJ et suppression des indicateurs
- Affichage de valeurs dans les grilles :  permet d'afficher les valeurs des indicateurs sous forme de tableau
- Affichage de graphiques ou histogrammes : permet d'afficher les graphiques ou les histogrammes
- Génération de rapport : permet de constituer et personnaliser un rapport 
	

Guide de réponse au cahier des charges
=======================================
Grille d'évaluation
--------------------
Le logiciel possède 4 fonctionnalités : gestion des indicateurs, affichage de valeurs, affichage de graphiques, génération de rapport

+------------------------+---------------------+----------------+
| Fonction               | Priorité            | Complexité     |
+========================+=====================+================+
| gestion des indicateurs| Haute               | Petite         |
+------------------------+---------------------+----------------+
| affichage de valeurs   | Haute               | Petite         |
+------------------------+---------------------+----------------+
| affichage de graphiques| Moyenne             | Grande         |
+------------------------+---------------------+----------------+
| génération de rapport  | Basse               | Grande         |
+------------------------+---------------------+----------------+


