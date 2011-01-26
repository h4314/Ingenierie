#######################################################
Cahier des charges détaillé du sous-projet "Logistique"
#######################################################

.. contents:: Sommaire
.. sectnum::

Introduction
============
Présentation du projet 
-------------------------------
        Ce projet a pour but de réaliser la meilleur gestion des convois à utiliser pour traiter les différentes besoins et sauvegarder la trace de tout le procès.
	
Présentation du document
--------------------------------------
	Ce document est un cahier des charges détaillé, ses fonctionnalités répondront aux exigences fonctionnelles et non fonctionnelles émises par le client. Il sera important de indiquer les éléments du logiciel qui répondront aux exigences. Il ne faut pas oublier que le cahier des charges a une valeur contractuelle et que l'on s'engage à réaliser ce que l'on décrit.


Présentation du problème
========================
Objectifs, principe du logiciel
--------------------------------
	Dans le système existant, les interventions sont ponctuelles et locales. Apres la mis en place de notre système, les informations seront mises à jours très régulièrement permettant de savoir les états de chaque réservoir. Par conséquent, nous pouvons développer un logiciel pour planifier les interventions et gérer les prestataires avec les informations disponibles. D'un côté, la planification des convois de camion permettera d'augmenter l'efficacité de l'intervention et réduire le coût ainsi que l'impact sur l'environnement. De l'autre côté, une meilleur gestion de prestataires facilitera l'approvisionnement des cuves et permettra de mieux fidéliser les prestataires.

Formulation des besoins généraux
-------------------------------------------------
	Le logiciel doit proposer à l'avance des interventions potentielles à effectuer en fournissant un itinéraire intéressant, le prestataire à contacter et une démarche à suivre pour une mission. L'utilisateur peut suivre les convois et planifier les nouvelles interventions à partir de propositions du logiciel.

Portée, développement, mise en oeuvre, organisation de la maintenance
---------------------------------------------------------------------
	Les données sont extraites de la base de données au site central accédée également par d'autre applications. L'administration de cette base de données est centralisé. Le Logiciel est utilisable depuis le client Web. Le développement de l'interface Web doit respecter la norme commune prédéfinie pour la partie interface de toutes les sous-projets.

Limites
----------
 - L'application va afficher les disponibilités des différentes convois mais c'est à l'utilisateur de choisir lequel va utiliser en dépendant de la distance et de la taille du convoi.
 - L'application ne permet pas de traiter plusieurs convois au même temps, par contre elle peut afficher les donnes de tous les convois.
 - Le logiciel permettra de réaliser zoom sur la carte mais seulement dans les sites proches.

Exigences fonctionnelles
========================
Fonctions de base, performances et aptitudes
------------------------------------------------------------------
	- Lorsqu'un convoi est mis en place suite à une alarme, cette alarme passe dans le statut "en cours", après passera dans l'état "résolue" et n'apparaitra plus dans la liste des alarmes "non résolues".

    - Consulter les convois qui sont actuellement en mission et consulter les différents informations les concernant. 

	- La consultation du trajet devra se faire sur une carte. 
	- Lancer un ordre de mission: choisir le camion, son trajet, les tâches a effectuer sur chaque sites et le personnel qui a besoin.
	- Il doit être possible de consulter un inventaire des ressources disponibles: nombre de camion, chauffeurs, techniciens, etc.

Contraintes d'utilisation
---------------------------------
	
- Ce logiciel n'est utilisable que par le Responsable Logistique.


Flexibilité
--------------
Le sous-système de Logistique sera une des applications les plus flexibles du système. En effet, les utilisateurs seront guidés dans les différentes étapes du traitement de la logistique, notamment la mise en place d'un convoi.


Contraintes imposées, faisabilité technologiques et éventuellement moyens
=========================================================================

Sûreté, planning, organisation, communication
-------------------------------------------------------------------

Il faut tout d'abord obtenir les données des différentes convois afin de savoir lesquelles sont prêt. Afin de pouvoir réagir correctement à chaque demande pour gérer le trajet des camions et leurs interventions cette application ne doit pas être utilisable par n'importe quelle personne. Un niveau de sécurité minimum est donc requis. Pour lancer l'application, une identification de l'utilisateur avec mot de passe est nécessaire.

Complexité
----------------
La complexité du sous-projet de Logistique est la représentation des convois sur une carte en temps réel et pouvoir demander de différentes informations.


Configuration cible
===================

Matériel et Logiciels
-----------------------------
- Le sous-système gestion de Logistique sera sous forme d'une application web.
- Il faut disposer d'un serveur d'application sur lequel seront stockés le service web.
- Le sous-système nécessite un accès aux bases de données. La base de donnée est sur le serveur de bases de données.
- Elle sera accessible à distance, les applications web seront développés en J2EE (Java Entreprise Edition).
- Les applications web seront accessibles via navigateur web. 
- Aucune application ne sera à installer sur les postes distants.
