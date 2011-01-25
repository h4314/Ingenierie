###################
Dossier d'interface
###################

Découpage du projet
###################

Le schéma suivant permet d'identifier clairement les différentes parties du
projet, qui seront découpés en sous-projet.

.. image:: architecture.png
  :width: 100%

Le projet est effectivement découpé en trois sous-parties principales, le site
de contrôle, la communication longue distance, et les sites distants.

Description des blocs
#####################

Site de contrôle
================

Ce bloc peut être découpé découpé en plusieurs sous blocs, donc voici un rapide
descriptif :

Monitoring
  Suivi en temps réel de l'activité des stations.

Commande des sites distants
  Changer des paramètres, mettre à jour les logiciels.

Planification de la maintenance sur site
  Permet de planifier les modalité des maintenances sur site, comme leur
  fréquence, ou encore demander une maintenance exceptionnel sur une site, par
  exemple en cas d'urgence.

Aide à la décision
  Permet d'aider l'employé du site distant dans le tâches courantes, en
  utilisant le *knowledge management* pour faire face à des situations
  classiques, mais demandant une réponse humaine.

Suivi en temps réel des opérations de maintenance
  Suivi géotemporel des opérations de maintenance, permettant d'assister un
  technicien sur site lors d'une intervention, par le biais de matériel
  spécifique dont il est équipé.

Communication longue distance
=============================

Envoi de donnée d'un site distant vers le site central
  Communication unidirectionnelle entre un site distant, et un site central,
  dans le but d'envoyer des valeurs de mesure.

Envoi de commande du site central vers le site distant
  Envoie d'une commande de changement de paramètre du site central vers le site
  distant.

Mise un jour du logiciel d'un site distant
  Envoie d'un nouveau logiciel depuis le site central vers le site distant
  (mise à jour *over the air*).



Site distant
============

Ce bloc peut de la même manière être découpé en plusieurs blocs fonctionnels :

Acquisition de données brutes
  Obtentions de données de capteurs, sans se soucier de leur format.

Communication interne
  Communication entre les noeuds ZigBee (routage, etc.).

Traitement des données au niveau noeud
  Traitement des données au niveau de chaque capteurs (par exemple moyennage).

Traitement des données au niveau site
  Traitement des données par le noeud *MASTER* de chaque site.


Définition des interfaces
#########################

Les échanges entre les blocs se feront de plusieurs manières.

À l'intérieur des réseaux de capteurs, la communication est faite de manière
transparente par l'intermédiaire du protocole ZigBee. Le protocol est en mode
texte, et peut être spécifique à chaque capteur ou chaque site.

Entre les sites distant et le site central, le format est normalisé, XML
compressé, permettant d'abstraire le fonctionnement du réseau de capteurs, et
donc de se protéger d'un éventuel changement ou évolution.

À l'intérieur du site central, les échanges de données se feront par
l'intermédiaire de requêtes HTTP (les employés utilisant l'application à
travers un navigateur internet). SQL sera utilisé par le logiciel serveur pour
insérer et consulter les données des capteurs dans la base de données.

Pour communiquer entre le serveur et les applications clientes, un technologie
du type AJAX (Asynchronous Javascript And XML) sera utilisé.

Nous utilisons donc un modèle de type 3-tiers, où le bloc « Communication
longue distance », étant le tier du milieu, permet de découpler fortement la
solution. L'utilisation de technologies de type web et moderne assure une
compatibilité avec les technologies et outils existants. L'accent a été mis sur
les protocoles standards, largement suffisant pour notre solutions. Quand aucun
protocole standard n'était disponible, l'approche a été de suivre l'idiome KISS 
(*Keep it simple and straightforward*), par exemple en utilisant des protocoles
texte, extrêmement simple à comprendre, implémenter, et étendre.

API des blocs
#############
