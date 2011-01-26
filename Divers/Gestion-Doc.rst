==================================
Gestion de documentation du projet
==================================

.. contents:: Sommaire
.. sectnum::

Introduction
############
	
Contexte et problématique
-------------------------

Il existe aujourd'hui de nombreux sites isolés et/ou difficiles d'accès qui nécessitent une surveillance et parfois des actions à distance. On s'intéresse particulèrement aux stations réservoirs utilisées pour stocker des substances (eau, déchets, etc.). La surveillance ou maintenance défectueuse de ces stations peut entrainer des risques de désastres écologiques et environnementaux.

Actuellement, tous les contrôles et actions sont réalisés par un opérateur qui doit se déplacer sur le site. Il n'y a donc que très peu de réactivité et une grande inefficacité du traitement des problèmes survenus.

Le COPEVUE souhaite étudier un système de surveillance à distance des sites isolés. Le système devra être évolutif, autonome et fiable.

L'hexanôme se charge de répondre à l'appel d'offre du COPEVUE, en réalisant l'étude désignée par le nom "Système de surveillance à distance de sites isolés". Cette étude est composée de 3 parties:

	1. Etude de faisabilité du point de vue technologique
	2. Cahier des Charges (Spécifications Techniques des Besoins)
	3. Proposition de conception (générique) du futur système

Objet
-----
La documentation d'un projet est essentielle. C'est le support pour la communication et le dialogue entre la maîtrise d'oeuvre (MoE) et la maîtrise d'ouvrage (MoA).
La documentation permet également la pérennité des informations au sein du projet, tout au long de son cycle de vie.

Objectifs:
----------
Les objectifs de ce dossier de gestion de la documentation sont de plusieurs ordres:

* Rappel des règles générales concernant la documentation: les acteurs du projet et leurs responsabilités vis-à-vis des documents, les cycles de vie d'un document, l'organisation et la structure de la documentation etc.

* Rappel des règles de la production des documents

* Présente les principaux documents qui devront être produits lors du projet, et propose des plans types pour ceux-ci.

* Indique la procédure à suivre pour mettre à jour le glossaire du projet qui sera commun à l'ensemble de l'équipe

Vocabulaire, abréviations
#########################

Terminologie
------------
Les termes sont classés par ordre alphabétique. Certaines de ces défintions sont extraites des documents de référence de l'AFNOR:

Assurance de la qualité:
	Ensemble des activités préétablies et systématiques mises en oeuvre dans le cadre du système qualité, et démontrées en tant que de besoin, pour donner la confiance appropriée en ce qu'une entité satisfera aux exigences pour la qualité.

Cahier des charges:
	Document fourni par le client au fournisseur, décrivant le plus explicitement possible le contenu de la prestation attentue et des éventuelles contraintes concernant les conditions techniques de production, d'exploitation et de qualité.

Client:
	Acteur qui demande la fourniture d'un bien ou d'un service.

Equipe:
	On appelle *Equipe* l'hexanôme H4314, la maîtris d'oeuvre (MoE) dans le cadre de l'appel d'offre "Système de surveillance à distance de sites isolés".

Livrable:
	Tout composant matérialisant le résultat de la prestation de la réalisation, c'est à dire toute production émise par le titulaire au cours du projet: document, courrier, module de code logiciel, dossiers de tests, application intégrée...

Modification:
	Terme générique qui recouvre à la fois les modifications de type "évolution" et de type "maintenance".

Procédure
	Manière spécifiée d'accomplir une activité

Projet:
	Ensemble d'activités qui sont prises en charge, dans un délai donné et dans les limites de ressources imparties, par des personnes qui y sont affectées dans le but d'attendre des objectifs définis.
	Dans notre cas, le *Projet* est l'étude "Système de surveillance à distance de sites isolées" réalisée par l'hexanôme H4314 pour l'entreprise COPEVUE.

Qualité:
	Aptitude d'un produit ou d'un service à satisfaire les besoins d'un utilisateur.

Abréviations
------------
CdP
	Chef de Projet

EP
	Etude Préalable

GEI
	Gestion d'Etude Informatique

H4314
	Hexanôme H4314

PAQP
	Plan d'Assurance Qualité Projet

PAQL
	Plan d'Assurance Qualité Logicielle

PMP
	Plan de Management de Projet

P1
	Plateforme **GitHub** d'hébergement du projet

P2
	Plateforme **Redmine** de gestion de projet

RQ
	Responsable Qualité

Plateforme et outils utilisés pour le projet:
#############################################
- Plateforme (P1) **Git** d'hébergement de projet: 

::

  git@github.com:h4314/Ingenierie.git

- Plateforme (P2) de gestion de projet **Redmine**: 

::

  http://bde.insa-lyon.fr:3000/projects/ingenierie

(P1) contiendra tous les documents de travail relatifs au projet (drafts, livrables finaux, documents ressources etc.)

(P2) est un outil de gestion de projet, qui permettra de:
- gérer les tâches pour les membres du projet
- suivre l'avancement du projet
- communiquer et d'échanger entre les membres du projet grâce à l'outil *Wiki*.

Tous les documents devront être rédigés dans des fichiers textes encodés en UTF-8 et en utilisant la syntaxe **reStructuredText**. (http://docutils.sourceforge.net/docs/user/rst/quickref.html)

Il est vivement encouragé aux différents acteurs d'utiliser des schémas dans leurs documents: l'utilisation des logiciels d'édition de schémas est libre, à condition que les sources des schémas soient présents dans la plateforme (P1).

Règles Générales
################

Les acteurs et leurs responsabilités
------------------------------------

Responsable Qualité
	Il supervise la gestion de la documentation et s'assure du respect des règles générales énoncées dans ce document.

Rédacteur
	Il est chargé de rédiger un document, ou une partie d'un document, conformément aux règles générales énoncées dans ce document. Si besoin, il définit les nouveaux termes dans le glossaire.
	Si besoin, il peut être chargé de modifier son travail suite à une vérification/validation.

Responsable de la vérification:
	Il relit attentivement le document rédigé, peut l'enrichir (correction, ajout, modification mineure) et apporter des commentaires au rédacteur.

Responsable de la validation:
	Il evalue la cohérence et la pertinence du contenu d'un document, et le valide.

Procédure en cas de non application des règles générales
--------------------------------------------------------
En cas de non application d'un document des règles énoncées dans ce document, deux cas de figure se présentent:

* Soit l'auteur de la non-application a une raison jugée valable par le CdP, alors une dérogation est accordée;

* Soit l'auteur de la non-application ne possède aucune raison que le CDP ne juge valable, alors le document concerné devra être modifié pour rentrer en conformité avec les règles.

Gestion des drafts
------------------
Les *drafts* seront placés sous le gestionnaire de version décentralisé
**Git** (P1). Le dépôt sera placé sur le site Github, et tous les membres de
l'équipe pourront effectuer des modifications (commit et push) et accéder aux
modifications effectuer par les autres personnes de l'équipe (pull).

Un document pourra avoir plusieurs états, en fonction de la tâche qui lui est
associé dans l'outil de gestion de projet **Redmine** (P2):
- *En cours* : Le document est commencé, et est en cours de rédaction.  L'avancement peut être visualisé à l'aide de la barre de progression dans (P2).
- *Besoin de relecture* : Le document est bien avancé, et l'auteur estime que la relecture peut commencer. Il s'agit alors pour le responsable qualité de faire des vérification de forme et de fond. La personne chargé de la relecture peut créer des nouvelles demandes associées à la tâche de rédaction du document si celui-ci contient des irrégularités qui ne peuvent pas être corrigées par le relecteur.
- *Fermé* : Une fois que le document est en version final, il doit être placé sous cette catégorie.

Le versionning ainsi que la sauvegarde des documents est donc assuré par le
gestionnaire de version (P1). Le suivi de la rédaction est assuré par l'outil de
gestion de projet (P2).

Tout commentaire sur un *draft* doit être fait dans l'outil de gestion de
projet (P2), ou sur l'interface de GitHub (P1), s'il s'agit d'un commentaire spécifique
à une portion de document. Sur Redmine, la fonctionnalités *notes* sera
utilisé, sur une tâche, et pour les commentaire globaux à une tâche. Sur
Github, les commentaires sur un commit ou une ligne, et uniquement cette
fonctionnalité doivent être utilisés, pour ne pas dupliquer les informations
sur les différents outils.

Les *drafts* sont placés dans le dossier /Documents.

Gestion des livrables
-----------------------
Les livrables seront générés à partir des *drafts*, et auront le même contenu,
mais un fond différent, indiquant précisément l'état du document. La mise en
page sera alors soignée.
Cette opération sera réalisée à l'aide de l'outil **rst2pdf**.

La création d'un livrable à partir d'un *draft* devra faire l'objet d'une
sous-tâche dans l'outil de gestion de projet, afin d'avoir un suivi précis du
temps passé sur cette étapes, et de pouvoir annoncer à l'équipe qu'il est temps
de relire le document avant le dépôt.

Les livrables sont placés dans le dossier /Documents/Livrables.

Structuration des documents
-----------------------------
Les documents auront une page de titre, indiquant clairement le type du
document, l'équipe, et le projet associé à ce document.

La seconde page consistera en un sommaire, qui permettra de mettre en évidence
la structure utilisé dans le document.

Les document disposeront d'un *header* et d'un *footer*, permettant de repérer le nom du document, le nom de l'équipe qui l'a rédigé, et le projet auquel se
document se rapporte. Il s'agit en quelque sorte de dupliquer les informations
de la page de garde de manière discrète, afin de replacer le document dans son
contexte à tout moment au cours de la lecture.

Les documents auront une forme unifiée, permettant d'augmenter la cohérence, et
de ne pas perdre le lecteur.

Sauvegardes et versionning
--------------------------
Les sauvegardes et versionning de tous les documents, fichiers et produits réalisés dans le cadre de ce projet sont gérées automatiquement par (P1) et (P2) grâce aux configurations initiales de ces plateformes.

Gestion des modifications
#########################

Il peut arriver de déceler, tard dans le projet, la nécessité de modifier une
partie du projet, ceci impactant plusieurs endroits du projet.

Un modification peut être une **non-conformité** (c'est à dire que la réponse de la
MOE s'écarte du cahier des charges, il s'agit donc en quelque sorte
d'une erreur), et une **demande d'évolution**, souvent demandé par la MOA
(il s'agit alors d'un souhait de la MOA qui n'avait pas été exprimé lors de la
rédaction du cahier des charges, mais qui doit être étudié par la MOE).

Il est donc nécessaire de formaliser la réponse à un problème de ce type, en
indiquant une procédure pour :

Dans le cadre de la découverte d'une non-conformité:
----------------------------------------------------
#. Informer la MOA, si le changement est important.
#. Placer une demande, du type *anomalie*, dans le logiciel de gestion de projet (P2), dans la catégorie adéquate.
#. Effectuer la modification dans le document racine, c'est à dire le document où se trouve la principale modification à faire.
#. Propager cette modification dans les différents documents impactés. On veillera à utiliser au mieux les capacités d'inclusions de documents du logiciel utilisé, afin de ne garder qu'en un seul endroit l'information : une information à plusieurs endroit doit être modifiée plusieurs fois en cas de réponse à une non conformité.
#. Informer les différents acteurs concernés du changement, afin qu'il puissent adapter leur travail futur, en prenant en compte cette évolution. Les autres acteurs, non directement informés, pourront se tenir au courant de la situation en consultant l'outil de gestion de projet (P2).

Dans le cadre d'une demande d'évolution émanant de la MOA
---------------------------------------------------------
#. Discuter de l'acceptation de la demande d'évolution. Les critères pouvant être pris en compte sont (liste non exhaustive) : la taille des modifications à apporter, la complexité des modifications à apporter, le nombre de demande d'évolution déjà acceptées durant le projet, la disponibilité de la MOE, la criticité de la demande d'évolution.
#. Si la demande est accepté, procéder comme pour une non-conformité.
#. Si la demande est refusée, en informer la MOA, en expliquant les raison, de manière clair. Il peut être possible de négocier, mais cela sort du cadre de la procédure à suivre lors d'une demande d'évolution.


Gestion de la qualité globale d'un document
###########################################

Lorsqu'un document a le statut *Besoin de relecture* sur l'outil de gestion de
projet, le responsable qualité devra commencer à effectuer une relecture, qui
devra être faite en considérant plusieurs aspects :

Fond
----
- Si possible, le responsable qualité devra mettre en regard différents document, et tenter de déceler d'éventuelles incohérences. En fonction de la taille d'une éventuelle erreur, il pourra décider de faire une demande d'anomalie, qu'il pourra s'assigner, ou assigner à une autre personne de l'équipe (se référer à la section *Gestion des modification*). 
- La cohérence au sein d'un même document doit être vérifiée. Cela passe notamment par :

    - La vérification sémantique des phrases (Exemple : une négation qui n'a pas lieu d'être, et qui induit une confusion pour le lecteur).
    - La vérification de la non contradiction au sein d'un même document (Exemple : le rédacteur a changé d'opinion sur un point précis du projet entre le début et la fin du document)

Forme
-----
- Grammaire : les fautes de grammaires en tout genre doivent être évitées.
- Typographie : la typographie devra respecter les standards français, afin de produire des document agréables et facile à lire, sans détourner le lecteur du contenu.


Vérification/Validation
-----------------------
La vérification d'un document, ou d'une sous-partie d'un document se fait obligatoirement par une autre personne que celle qui l'a rédigé.
La vérification fait l'objet d'une tâche dans la plateforme P2.

La validation d'un document est faite par le CdP et le RQ:
	- le CdP valide le document au niveau du fond
	- le RQ valide le document au niveau de la forme. 

Gestion des répertoires
-----------------------
L'organisation des répertoires pour les documents dans la plateforme P1 (Github) est la suivante:

:/Documents: contient tous les documents produits par l'équipe de projet
:/Documents/Livrables: contient tous les livrables produits par l'équipe de projet
:/Documents/Schemas: contient tous les schémas et leurs fichiers sources
:/Ressources: contient tous les documents qui ont été fournis à l'équipe de projet (Cahier des charges, documentation, cours etc.)
:/Divers: contient les fichiers et documents qui sont en dehors du système de gestion de documentation du projet. Chaque personne du projet peut y avoir un répertoire personnel où il peut stocker des fichiers relatifs à son travail.
	

Gestion du glossaire
--------------------
Tout au long du projet, un certain nombre de notions vont apparaître et il est important que l'ensemble de l'équipe soit en accord sur la signification de chacun de ces termes. 
C'est pourquoi, dès le début du projet, un glossaire commun est initialisé et sera utilisé par l'ensemble de l'équipe projet.
Ce glossaire contiendra toutes les notions rencontrées ainsi que leur définition. La procédure suivante décrit les modalités pour insérer un nouveau terme dans le glossaire.

Le glossaire se trouve dans */Documents/Glossaire.rst*

#. Insertion d'un nouveau terme dans le glossaire: Si le terme que l'on veut définir est nouveau, on crée une nouvelle entrée dans le fichier glossaire, en respectant l'ordre alphabétique et la syntaxe du fichier existant.
#. Insertion d'un terme déjà existant dans le glossaire: Deux cas de figure se présentent:

    - soit la personne est d'accord avec la définition existante
    - soit la personne est en désaccord avec la définition existante. Dans ce cas une tâche devra être crée dans Redmine (P2) pour résoudre ce problème.

Gestion de la documentation papier
##################################
Dans le cadre de sa politique éco-responsable, l'équipe H4314 s'engage à limiter au maximum l'utilisation du papier et des impressions.

Tous les documents relatifs au projet seront numériques.

Seuls les livrables finaux pourront être imprimés.

Quelques régles de bonnes pratiques:
####################################

#. Un schéma vaut mieux qu'un long discours
#. Règle des 5 lignes: être capable d'exprimer une idée à une autre personne en 5 lignes

La bonne application des paragraphes précédents nécessite donc une maitrise
parfaite des outils, relativement sophistiqués, par l'équipe de projet. Une
formation leur a été donnée en début de projet, et des référents technique ont
été nommés :

- Git et GitHub : Paul ADENOT et Martin RICHARD.
- Redmine : Paul ADENOT et Etienne GUÉRIN.

