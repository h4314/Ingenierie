#######################################################
Cahier des charges d�taill� du sous-projet "Logistique"
#######################################################

Introduction
=============
Pr�sentation du projet 
----------------------
	Le COPEVUE souhaite �tudier un syst�me de surveillance � distance de sites isol�s ou difficilement accessibles pour des raisons g�ographiques ou climatiques qui permettrait de surveiller des objets critiques sans avoir besoin de l'intervention humaine. Actuellement la surveillance de ces lieux est assur�e par le propri�taire du lieu de travail qui en fonction du niveau du liquide qu'il constate, il appelle aux responsables de la soci�t� charg�e de s'occuper du r�servoir pour qu'ils viennent � la remplir en envoyant des camions.
	
	Ce syst�me pourrait aussi bien �tre utilis� pour la pr�vention des incendies ou le contr�le et la surveillance d'un parc de r�servoirs en Norv�ge. La solution � mettre en place devra faire preuve d'autonomie et de robustesse. 
	

Pr�sentation du document
------------------------
	Ce document est un cahier des charges d�taill�, ses fonctionnalit�s r�pondront aux exigences fonctionnelles et non fonctionnelles �mises par le client. Il sera important de indiquer les �l�ments du logiciel qui r�pondront aux exigences. Il ne faut pas oublier que le cahier des charges a une valeur contractuelle et que l'on s'engage � r�aliser ce que l'on d�crit.


Pr�sentation du probl�me
========================
Objectifs, principe du logiciel
--------------------------------
	Le sous-syst�me de Logistique s'occupe de traiter les alarmes envoy�es par le syst�me embarqu�. Il met � disposition les outils permettant de planifier les convois de camions (trajet, destinations, personnel, mat�riel, etc). Il communique avec les sites embarqu�s via le module GPRS qui se charge de transmettre les donn�es entre les deux syst�mes et interagit avec la base de donn�es pour consulter et stocker des donn�es.
	
	Le sous-syst�me Logistique occupe une place vraiment importante dans notre solution, en offrant la possibilit� d'optimiser les convois de camions.

Formulation des besoins g�n�raux
---------------------------------
	Consulter les convois qui sont actuellement en mission et consulter les diff�rents informations les concernant. 
	La consultation du trajet devra se faire sur une carte. 
	Lancer un ordre de mission: choisir le camion, son trajet, les t�ches a effectuer sur chaque sites et le personnel qui a besoion.
	Il doit �tre possible de consulter un inventaire des ressources disponibles: nombre de camion, chauffeurs, techniciens,... 

Port�e, d�veloppement, mise en oeuvre, organisation de la maintenance
---------------------------------------------------------------------
	Les donn�es sont extraites de la base de donn�es au site central acc�d�e �galement par d'autre applications. L'administration de cette base de donn�es est centralis�. Le Logiciel est utilisable depuis le client Web. Le d�veloppement de l'interface Web doit respecter la norme commune pr�d�finie pour la partie interface de toutes les sous-projets.

Limites
--------
	Le syst�me fournit au d�but quelques indicateurs pr�d�finis selon les besoins initiales. Mais dans le file de temps, c'est � utilisateur de choisir des donn�es qui les int�ressent avec l'expert m�tier et d'en d�finir plus. Il n'a aucune intelligence de prendre des d�cision � la place des utilisateurs.

Exigences fonctionnelles
========================
Fonctions de base, performances et aptitudes
--------------------------------------------
	Les syst�mes embarqu�s l�vent un certain nombre d'alarmes : pannes mat�rielles, d�passement d'un seuil, etc.

	Le sous-syst�me GPRS re�oit les diff�rentes alarmes et les transmet au sous-syst�me de Logistique qui va les analyser avant de les stocker.
	
	Lorsqu'un convoi est mis en place suite � une alarme, cette alarme passe dans le statut "en cours", apr�s passera dans l'�tat "r�solue" et n'apparaitra plus dans la liste des alarmes "non r�solues".
 

Contraintes d'utilisation
-------------------------
	Le syst�me de surveillance de sites peut �tre utilis� dans de nombreuses situations: surveillance de r�servoirs, d�tection d'incendies, etc.
	Ainsi, le nombre d'utilisateurs potentiel du syst�me peut varier fortement. Le sous-syst�me Logistique devra �tre toujours r�actif et utilisable avec autant d'utilisateurs connect�s. On peut considerer le logiciel utilisable et r�actif s'il prends moins de 5 secondes pour charger une page.

	Le sous-syst�me de Logistique sera une des applications les plus ergonomiques du syst�me. En effet, les utilisateurs seront guid�s dans les diff�rentes �tapes du traitement de la logistique, notamment la mise en place d'un convoi. 
	

Flexibilit�, variation de co�t associ�
--------------------------------------
	Dans un soucis de r�duction des co�ts de transport, on cherchera � optimiser les d�placements des convois. Ainsi, un convoi sortira rarement du parking pour effectuer une mission sur un seul site. En g�n�ral, il sortira pour certaines missions sur des sites diff�rents. 


Contraintes impos�es, faisabilit� technologiques et �ventuellement moyens
=========================================================================

S�ret�, planning, organisation, communication
----------------------------------------------
	
Le sous-syst�me de Logistique permet de g�rer le trajet des camions et leurs interventions. Cette application ne doit pas �tre utilisable par n'importe quel technicien. Un niveau de s�curit� minimum est donc requis. Pour lancer l'application de gestion des interventions, une identification de l'utilisateur avec mot de passe est n�cessaire.
De la m�me fa�on, permet d'avoir acc�s � des donn�es qui pourraient �tre confidentielles, comme la position strat�gique de sites. Alors, il est essentiel de prot�ger l'acc�s � ces informations.
	

Comp�tences
-----------

L'application du sous-syst�me de Logistique sera d�velopp�e sous forme de services web. Il faut disposer d'un serveur d'application sur lequel seront stock�s le service web.
Le sous-syst�me n�cessite un acc�s aux bases de donn�es. La base de donn�e est sur le serveur de bases de donn�es.	
		

Configuration cible
====================

Logiciels
---------
Le sous-syst�me gestion de Logistique sera sous forme d'une application web. Elle sera accessible � distance, les applications web seront d�velopp�s en J2EE (Java Entreprise Edition).


Stabilit� de la configuration
------------------------------
Les applications web seront accessibles via navigateur web. 
Aucune application ne sera � installer sur les postes distants.
