======================================================
Bonne Pratique: Rédaction d'un Cahier des Charges (CdC)
======================================================

*Contexte d'application de ce document*: rédaction d'un CdC pour un/ou des sous-ensembles logiciels.

*Objectif du document*: synthétiser les bonnes pratiques à appliquer lors de la rédaction d'un CdC.

Définition générale d'un CdC
	Le Cdc pose un problème et appelle à une proposition de solution.
	Le cahier des charges est un document qui est l'expression des besoins néccessaires, essentiels, fonctionnels et techniques de la solution souhaitée.
	Ce document doit décrire de manière simple et claire les besoins auxquels MoE doit répondre. Il doit être suffisamment précis pour assurer la satisfaction des besoins.
	Le CdC est un outil de dialogue entre la MoE et la MoA qui permet d'affiner la correspondance entre l'offre et la demande.
	Un Cdc n'est pas forcément statique. Son contenu peut-être modifié au cours du projet. Cependant, l'idéal est que la première version de ce document soit la plus proche possible de la version finale, et qu'il soit modifié le moins souvent possible.


Définition Cdc pour un produit logiciel:
	Le CdC doit répondre à la question "Que doit faire le logiciel?".

Remarque: Pour réaliser le CdC d'un sous-ensemble logiciel, il est important de connaître le système dans sa globalité pour savoir et comprendre dans quel contexte le logiciel va s'inscrire. Il est important d'être cohérent avec les autres sous systèmes du projet, et pour cela il faudra être particulèrement attentif aux interactions et aux échanges impliqués.

* Objectifs du CdC:

Le Cdc doit traiter les points suivants:

- poser le problème à résoudre
- définir les objectifs et les besoins à satisfaire
- définir les exigences fonctionnelles
- identifier les contraintes imposées
- définir la configuration cible
- proposer un guide de réponse au problème posé

Plan type pour un  CdC
----------------------
*Remarque: ce qui suit est une suggestion. Il ne s'agit pas d'un plan à appliquer automatiquement. Certaines modifications et ajustements peuvent être adoptés en fonction du contexte du projet concerné*.

réf: (Rappeler la référence de l'appel d'offre concernée)

#. Introduction
	#. Présentation du projet
	#. Présentation du document
	#. Terminologie et abréviations
		(lister les termes utilisés dans ce document qui nécessitent d'être explicités)
#. Présentation du problème
	#. Objectifs, principe du logiciel
	#. Formulation des besoins (généraux)
	#. Portée, développement, mise en oeuvre, organisation de la maintenance
	#. Limites
#. Exigences fonctionnelles
	#. Fonctions de base, performances et aptitudes
	#. Contraintes d'utilisation
	#. Critères d'appréciation de la réalisation effective de la fonction
	#. Flexibilité, variation de coût associé
#. Contraintes imposées et faisabilité technologique
	#. Sûreté, planning, organisation, communications
	#. Complexité
	#. Compétences, moyens et règles
	#. Normes de documentation
#. Configuration cible
	#. Matériel et logiciel
	#. Stabilité de la configuration
	#. Interfaces (description des API, si nécessaire)
#. Guide de réponse au cahier des charges
	#. Grille d'évaluation (poser la question de l'apport de chaque fonction)
#. Annexes (*liste non exhaustive, et à titre d'exemple*)
	#. Observations de l'existant
	#. Propositions d'orientation
	#. Image(s) d'écran(s) principaux du logiciel
	#. Résultat de l'analyse de la valeur
	#. Descriptions des API avec le reste du système
	#. Choix d'une solution et justifications
	#. Appréciation de la solution retenue
	#. Rapport d'analyse du besoin

Ressources utiles pour la rédaction du CdC
------------------------------------------
- Critères d'appréciation de la réalisation effective de la fonction: approche "Analyse de la valeur" dans chapitre II du cours 4IF (QL).
- Grille d'évaluation: "Processus d'acquisition: cas de la sous-traitance" dans chapitre VIII du cours 3IF (GL).


Règles sur la forme pour un CdC
-------------------------------

- On utilisera de préférence un langage impersonnel: le "dispositif", le "système" ou "l'application".
- Le temps verbal "idéal": le futur. Cela permet de décrire une exigence à venir pour le futur système non encore réalisé. Cela permet de bien décrire le contrat à remplir pour la future implémentation.
- Emploi du conditionnel possible en plus du futur (ex: devra/devrait, pourra/pourrait), c'est même recommandé: cela permet d'introduire des différences entre ce à quoi on s'oblige et ce qu'on envisage souhaitable/possible.

