###############################################################
Cahier des charges détaillé du sous-projet "Aide à la décision"
###############################################################

Introduction
=============
Présentation du projet
----------------------
	Le sous-projet "Aide à la décision"  correspond à une partie annexe dans le projet. Cette partie a pour but d'exploiter au maximum les données que possède le système et en tirer des conclusion et des améliorations. Bien qu'annexe au système mis en place, ce sous-projet reste indispensable à une exploitation efficace.

Présentation du document
------------------------
	Ce document est un cahier des charges détaillé, c'est-à-dire qu'il décrit de manière précise le système en question, afin de pouvoir aborder la phase de développement en connaissant exactement ce qu'on attend du produit.

Terminologie et abbréviations
------------------------------


Présentation du problème
========================
Objectifs, principe du logiciel
--------------------------------
	Le système récolte et stocke les données d'état de fonctionnement de toutes les stations. Ces données sont potentiellement très intéressantes à analyser. Ce logiciel est utilisé par l'administrateur du système et des managers au niveau décisionnel de définir des indicateurs pour surveiller le fonctionnement du système à moyen et à long terme. Par exemple, en visualisant le niveau de liquide dans une cuve sur un an, nous pouvons détecter des dysfonctionnements comme une fuite et effectuer des maintenances préventifs. Nous pouvons faire des comparaisons entre les sites afin de trouver un meilleur dimensionnement du système global.

Formulation des besoins généraux
---------------------------------


Portée, développement, mise en oeuvre, organisation de la maintenance
---------------------------------------------------------------------
	Les données sont hybergé dans la base de données au site central accédée également par d'autre applications. L'administration de cette base de données est centralisé.
	Le programme est utilisable depuis le client Web. Le développement de l'interface Web doit respecter la norme commune prédéfinie pour la partie interface de toutes les sous-projets. 
	Puisque offre aux utilisateur la possiblité de définir des indicateurs, le logiciel nécessite une maintenance particulière de manière continue assurée par un expert métier compétent en informatique afin d'étendre ses fonctionnalités et améliorer ceux existant.

Limites
--------
	C'est à utilisateur de choisir des données qui les intéressent et de définir certains indicateurs. Le logiciel se charge de présenter des données sous forme souhaité (Tableaux, Graphiques, Diagrammes etc) et fournir une aide à la décision des utilisateurs. Par contre, il n'a aucune intelligence de prendre des décision à la place des utilisateurs.

Exigences fonctionnelles
========================
Fonctions de base, performances et aptitudes
--------------------------------------------
Les fonctionnalités générals du logiciel se découpent en plusieurs parties:
 - L'expert métier crée des indicateurs en définissant le nom, les sources de données et la formule de calcul si nécessaire. ex. le niveau de liquide d'une cuve sur un an; le nombre d'interventions par station; 
 - On peut visualiser les valeurs de chaque indicateur dans les grilles de données.
 - On peut visualiser les graphiques ou les histogrammes des 
 
Contraintes d'utilisation
-------------------------
	Ce programme n'est utilisable que par le personnel qualifié et ayant un niveau de responsabilité suffisant.

Critères d'appréciation de la réalisation effective de la fonction
------------------------------------------------------------------
	Les critères d'appréciation de ce logiciel est la facilité d'utilisation et la possibilité infini qu'il offre à COPEVUE d'exploiter au maximum les données selon leur souhaits. Cela facilitera la prise de décisions stratégiques. 

Flexibilité, variation de coût associé
--------------------------------------
	Le logiciel est très flexible car l'utilisateur peut définir des indicateurs s'il le souhaite.


Contraintes imposées, faisabilité technologiques et éventuellement moyens
=========================================================================
Sûreté, planning, organisation, communication
----------------------------------------------
	Dans un premier temps, une personne doit récolter des besoins auprès personnes conernées du COPEVUE. Plus précisément, quel sont les indicateurs qu'elles souhaitent au départ, quels sont les formats et les objets graphiques qu'elles préfèrent pour l'affichage.
	Ensuite une équipe devra s'occuper d'écrire les spécifications fonctionnelles du logiciel, en respectant la norme commune de l'interface web et de la base de données. 
	Lorsque les spécifications seront terminées, on pourra aborder la phase de développement. Pendant ce temps, il faut communiquer avec les futurs utilisateurs régulièrement pour demander leur avis sur l'avancement du projet et si la solution développé leur convient. Quand il y a des nouveaux besoins, il faut modifier ou ajouter des fonctionnalités. On devra également présenter l'interface web aux futurs utilisateurs avant de l'intégrer au développement.
	Après intégration, viendra la phase de test. Il faut assurer la connexion entre la base de données, le noyau applicatif et l'interface web. 


Complexité
----------
	Les parties complexes du logiciel est la définition des indicateurs appropriés et l'affichage des graphiques. 

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
Le matériel relié au logiciel est le serveur et la Base de Données centrale. Le logiciel doit pouvoir être compatible avec ces derniers, et être configuré pour travailler avec.

Stabilité de la configuration
------------------------------

Interfaces
-----------

Guide de réponse au cahier des charges
=======================================
Grille d'évaluation
--------------------

