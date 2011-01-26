#######################################################
Cahier des charges détaillé du sous-projet "Logistique"
#######################################################

Introduction
=============
Présentation du projet 
----------------------
	Le COPEVUE souhaite étudier un système de surveillance à distance de sites isolés ou difficilement accessibles pour des raisons géographiques ou climatiques qui permettrait de surveiller des objets critiques sans avoir besoin de l'intervention humaine. Actuellement la surveillance de ces lieux est assurée par le propriétaire du lieu de travail qui en fonction du niveau du liquide qu'il constate, il appelle aux responsables de la société chargée de s'occuper du réservoir pour qu'ils viennent à la remplir en envoyant des camions.
	
	Ce système pourrait aussi bien être utilisé pour la prévention des incendies ou le contrôle et la surveillance d'un parc de réservoirs en Norvège. La solution à mettre en place devra faire preuve d'autonomie et de robustesse. 
	

Présentation du document
------------------------
	Ce document est un cahier des charges détaillé, ses fonctionnalités répondront aux exigences fonctionnelles et non fonctionnelles émises par le client. Il sera important de indiquer les éléments du logiciel qui répondront aux exigences. Il ne faut pas oublier que le cahier des charges a une valeur contractuelle et que l'on s'engage à réaliser ce que l'on décrit.


Présentation du problème
========================
Objectifs, principe du logiciel
--------------------------------
	Le sous-système de Logistique s'occupe de traiter les alarmes envoyées par le système embarqué. Il met à disposition les outils permettant de planifier les convois de camions (trajet, destinations, personnel, matériel, etc). Il communique avec les sites embarqués via le module GPRS qui se charge de transmettre les données entre les deux systèmes et interagit avec la base de données pour consulter et stocker des données.
	
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
--------
	Le système fournit au début quelques indicateurs prédéfinis selon les besoins initiales. Mais dans le file de temps, c'est à utilisateur de choisir des données qui les intéressent avec l'expert métier et d'en définir plus. Il n'a aucune intelligence de prendre des décision à la place des utilisateurs.

Exigences fonctionnelles
========================
Fonctions de base, performances et aptitudes
------------------------------------------------------------------
	- Le sous-système GPRS reçoit les différentes alarmes et les transmet au sous-système de Logistique qui va les analyser avant de les stocker.
	- Lorsqu'un convoi est mis en place suite à une alarme, cette alarme passe dans le statut "en cours", après passera dans l'état "résolue" et n'apparaitra plus dans la liste des alarmes "non résolues".
        - Consulter les convois qui sont actuellement en mission et consulter les différents informations les concernant. 
	- La consultation du trajet devra se faire sur une carte. 
	- Lancer un ordre de mission: choisir le camion, son trajet, les tâches a effectuer sur chaque sites et le personnel qui a besoin.
	- Il doit être possible de consulter un inventaire des ressources disponibles: nombre de camion, chauffeurs, techniciens, etc.

Contraintes d'utilisation
---------------------------------
	Le système de surveillance de sites peut être utilisé dans de nombreuses situations: surveillance de réservoirs, détection d'incendies, etc.
	Ainsi, le nombre d'utilisateurs potentiel du système peut varier fortement. Le sous-système Logistique devra être toujours réactif et utilisable avec autant d'utilisateurs connectés. On peut considerer le logiciel utilisable et réactif s'il prends moins de 5 secondes pour charger une page.

	Le sous-système de Logistique sera une des applications les plus ergonomiques du système. En effet, les utilisateurs seront guidés dans les différentes étapes du traitement de la logistique, notamment la mise en place d'un convoi. 
	

Flexibilité, variation de coût associé
--------------------------------------
	Dans un soucis de réduction des coûts de transport, on cherchera à optimiser les déplacements des convois. Ainsi, un convoi sortira rarement du parking pour effectuer une mission sur un seul site. En général, il sortira pour certaines missions sur des sites différents. 


Contraintes imposées, faisabilité technologiques et éventuellement moyens
=======================================================

Sûreté, planning, organisation, communication
-------------------------------------------------------------------
Le sous-système de Logistique permet de gérer le trajet des camions et leurs interventions. Cette application ne doit pas être utilisable par n'importe quel technicien. Un niveau de sécurité minimum est donc requis. Pour lancer l'application de gestion des interventions, une identification de l'utilisateur avec mot de passe est nécessaire.
De la même façon, permet d'avoir accès à des données qui pourraient être confidentielles, comme la position stratégique de sites. Alors, il est essentiel de protéger l'accès à ces informations.

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