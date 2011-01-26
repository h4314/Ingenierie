#######################################################
Cahier des charges détaillé du sous-projet "Logistique"
#######################################################

Introduction
=========
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
	Le sous-système de Logistique s'occupe principalement de répondre et traiter aux besoins du sous-système Monitoring. Il met à disposition les outils permettant de planifier les convois de camions (trajet, destinations, personnel, matériel, etc). Il va aussi se communiquer avec les sites embarqués via le module GPRS qui se charge de transmettre les données entre les deux systèmes et interagit avec la base de données pour consulter et stocker des données.
	
	Le sous-système Logistique occupe une place vraiment importante dans notre solution, en offrant la possibilité d'optimiser les convois de camions.

Formulation des besoins généraux
-------------------------------------------------
 - Proposer les différentes convois prêt pour traiter les besoins
 - Permettre au module de gestion des alarmes savoir quels camions sont les mieux placés.
 - Proposer une interface permettant de voir la trace de tous les camions.

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
=======================================================

Sûreté, planning, organisation, communication
-------------------------------------------------------------------

Il faut tout d'abord obtenir les données des différentes convois afin de savoir lesquelles sont prêt. Afin de pouvoir réagir correctement à chaque demande pour gérer le trajet des camions et leurs interventions cette application ne doit pas être utilisable par n'importe quelle personne. Un niveau de sécurité minimum est donc requis. Pour lancer l'application, une identification de l'utilisateur avec mot de passe est nécessaire.

Complexité
----------------
La complexité du sous-projet de Logistique est la représentation des convois sur une carte en temps réel et pouvoir demander de différentes informations.


Configuration cible
==============

Matériel et Logiciels
-----------------------------
- Le sous-système gestion de Logistique sera sous forme d'une application web.
- Il faut disposer d'un serveur d'application sur lequel seront stockés le service web.
- Le sous-système nécessite un accès aux bases de données. La base de donnée est sur le serveur de bases de données.
- Elle sera accessible à distance, les applications web seront développés en J2EE (Java Entreprise Edition).
- Les applications web seront accessibles via navigateur web. 
- Aucune application ne sera à installer sur les postes distants.