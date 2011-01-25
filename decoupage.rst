=========================
Découpage en sous-projets
=========================


Macro découpage
###############

- Site central
	- infrastructure matérielle 
	- développement logiciel
- Site distant
	- infrastructure matérielle
	- développement logiciel 
- Communication entre le site central et les sites distants
	- infrastructure matérielle
	- développement logiciel 
- Accompagnement de projet


Découpage détaillé
###################

=> document transverse qui présente comment un sous sytème doit être pensé 

Site central 
============

- Harmonisation des couches de données, applicatives, et de présentation pour l'ensemble des modules
=> document de référence pour harmoniser les IHM entre les différents modules => PAQP idem BDD + Applicatif

Modules :
- Monitoring
- Commandement des sites distants
- Gestion des données
- Logistique
- Aide à la décision
- Suivi temps réel des opérations de maintenance


TODO: a virer :
- aide à la décision, statistiques => dysfonctionnements, problèmes de dimensionnement, comparaison d'efficacité entre cuve/site distant, nb pannes => maintenance préventif => Yi Quan
- logistique, planification des convois => quels prestataires, quels trajets (site distant, cuve) - gestion des prestataires  => Arturo
- mise à jour, paramétrage => frequence de deep sleep, synchronisation, nb mesures, etc.
- monitoring temps réel, alarmes (dysfonctionnements critiques) - procédure => gestion des exceptions => Pierrick
- suivi temps réel des opérationnels (employés + camions) 
- client web (IHM) => peu de travail pour passer sur smartphone
	- administratif (gestion)
	- opérationnel (technique)
- tracabilite, donnees, volume, securite, BDD ?


(serveur web/applicatif, serveur base de données, postes de travail, etc.)


Site distant
============

Infrastructure matérielle :
- Installation des capteurs
- Installation des noeud esclave
- Installation des noeuds maître

Développement logiciel :
- Acquisition et traitement des données bruts sur noeud esclave
- Communication intra-site
- Traitement des données collectées sur noeud maître 
- Portage des couches de présentation des modules du site central sur appareils mobiles (PDA, smartphones)

Communication entre le site central et les sites distants
==========================================================

- définition du protocole de communication
- interface côté site central
- interface côté sites distants

Accompagnement de projet
========================

- Mise en place
- Aide dans la démarche de Copevue
- Projet pilote
- Formation




