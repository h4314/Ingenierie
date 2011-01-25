###################
Dossier d'interface
###################

.. contents:: Sommaire
    :depth: 3
.. sectnum::

.. page::

Découpage du projet
###################

Le schéma suivant permet d'identifier clairement les différentes parties du
projet, qui seront découpés en sous-projet.

.. image:: architecture.png
  :width: 100%

Le projet est effectivement découpé en trois sous-parties principales, le site
de contrôle, la communication longue distance, et les sites distants.

Ces parties seront elles-mêmes découpées en sous parties, et des interfaces
(au sens d'API, Application Programming Interface) seront spécifiée, afin de
fixer les interfaces entre les modules, et permettre ainsi de faire du
développement en parallèle. Les lecteurs qui ont des connaissances en
programmations trouverons peut être plus facile de lire directement la dernière
section, celle-ci étant plus formelle que les précédentes.

.. page::

Description des blocs
#####################

Site de contrôle
================

Ce bloc peut être découpé découpé en plusieurs sous blocs, donc voici un rapide
descriptif :

Monitoring
  Suivi en temps réel de l'activité des stations. Aucun mécanisme d'alerte n'est
  mis en place, celui-ci correspondant à un calcul fait par le site de contrôle
  lui-même.

Commande des sites distants
  Changer des paramètres, mettre à jour les logiciels.

Planification de la maintenance sur site
  Permet de planifier les modalité des maintenances sur site, comme leur
  fréquence, ou encore demander une maintenance exceptionnel sur une site, par
  exemple en cas d'urgence.

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


.. page::

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


.. page::

API des blocs
#############

Les API présentées ci-dessous correspondent à celles qui seront disponibles à un
développeur pour implémenter le système. Il est fait grand usage d'appels
asynchrone demandant des fonctions de *callback*, l'utilisateur devant fournir
ses propres fonctions qui traiteront les arguments proposés.
Les fonctions sont, par défaut, asynchrone, et les fonction synchrone,
nécessitant la prise en compte du programmeur au niveau multi-tâche seront
clairement indiquée dans leur descriptions.

Conventions
===========

La syntaxe de ces API ne correspond pas à un langage en particulier, et s'inspire de
beaucoup de langage de programmation. Les paramètre seront entre parenthèses,
séparés par une virgule.

Le type de retour est spécifié, comme en C ou en Java, avant le nom de la
fonction.

Types utilisés
==============
``callID``
  Entier utilisé pour identifier un appel asynchrone au
  sein du système. Deux appels ne pourront pas avoir la même valeur de ``callID``
  dans des temps raisonnablement long, correspondant à la valeur maximum de ce
  type numérique (ex: 65536 pour un entier 16 bits), l'identifiant étant
  incrémenté à chaque appel'.

``NodeID``
  Identifiant unique donné à un capteur. Il peut aussi s'agir du noeud *MASTER*.

``SiteID``
  Identifiant unique donné à un site contenant des cuves. Un couple 
  (``NodeID``, ``SiteID``) permet d'identifier de manière unique un
  noeud (capteur ou noeud *MASTER*) du système).

``SensorInfo``
  Structure de donnée contenant toutes les informations d'un capteur :
  coordonnées GPS, format de données, fréquence d'actualisation, etc.

``void``
  En référence à de nombreux langages de programmation, la présence de ce
  mot-clé signifie que la fonction ne retourne pas de valeur. Ça n'est pas à
  proprement parler un type.

Fonction commune aux différents blocs
=====================================

``void ack(callID, returnCode)``
  Fonction qui est appelé après une requête, en utilisant l'API.
  ``callID`` est l'entier qui est retourné à chaque appel, pour la traçabilité
  au sein du système. ``returnCode`` correspond à éventuel code d'erreur, qu'il
  s'agira de mettre en regard avec le ``callID`` pour obtenir le type d'erreur.

Site central
============

Ces fonctions ne sont pas des primitives réseau, mais appellent en fait la
couche centrale (communication longue distance), pour communiquer avec les
sites. Il est donc fait une abstraction total du réseau.

Monitoring
----------

Le monitoring est fait en *push*, il n'y a donc pas de fonction de type
``getValue(NodeID)``, bloquante tant que le capteur n'a pas de donnée à
proposer. Cela permet de s'affranchir du besoin de lancer beaucoup de processus
ou de *threads* pour *monitorer* beaucoup de capteurs.

``callID newSensor(SiteID, SensorInfo)``
  Fonction de callback appelée quand un nouveau capteur s'enregistre auprès du
  site central. Cette fonction permet à un nouveau site de s'enregistrer dans le
  système. Il pourra être prévu un procédé cryptographique pour authentifier les
  site. Lorsque cette fonction est appelée, il devient possible de *monitorer*
  le capteur.

``callID addWatch(SiteID, NodeID)``
  Fonction qui permet de demander au système de nous communiquer toute nouvelle
  donnée qui est émise par le capteur ``NodeID`` du site ``SiteID``. Dès lors,
  dès que ce capteur aura des données à envoyer, la fonction ``dataAvailable``
  sera appelée.

``callID removeWatch(SiteID, NodeID)``
  Fonction qui permet de retirer le capteur de la liste de capteur dont les
  données sont surveillées.

``callID dataAvailable(SiteID, NodeID, Data)``
  Fonction de callback appelée quand un capteur a des données disponibles.
  L'identifiant du site est dipsonible dans le champ ``SiteID``.
  L'identifiant du capteur est disponible dans le champ ``NodeID``, et les
  données sont disponibles dans le champ ``Data``.

``callID eventOccured(SiteID, NodeID, event)``
  Fonction de callback appelée quand un capteur veut envoyer un évènement qui
  ne correspond pas à des données, tel une défaillance matérielle, un signal de
  batterie faible, etc. ``event`` contient alors un horodatage, et les informations
  relatif à cet évènement.

  

Commande des sites distants
---------------------------

``callID setValue(SiteID, NodeID, key, value)``
  Permet de fixer une valeur, pour le noeud ``NodeID`` du site ``SiteID``,
  pour un certain paramètre, de nom ``key``. La valeur sera fixée à ``value``.
  Si le noeud n'est pas disponible, car endormi, la valeur sera mis en cache par
  le noeud *MASTER*, et elle lui sera communiqué lors de son réveil.

``callID getValue(SiteID, NodeID, key, value)``
  La valeur de l'attribut de nom ``key`` du noeud ``NodeID`` du site ``SiteID``
  est placé dans l'attribut ``value``.


Planification de la maintenance sur site
----------------------------------------

Les opérations de cette partie sont de très haut-niveau, et ne concernent pas
l'ajout dans un logiciel de planning, qui devra être faite de manière interne au
logiciel.

``callID newMaintenanceOperation(SiteID, NodeID, type, priority, operationID)``
  Ajoute un besoin de maintenance dans le système, permet de communiquer avec
  d'autres système, par exemple de planning, lorsqu'une opération de maintenance
  doit être effectuée sur le système. Le ``type`` correspond à un type d'opération
  de maintenance, l'attribut ``priority`` permet de fixer la priorité pour
  l'opération de maintenance, permettant de faire passer des opérations avant
  d'autres. 

``callID removeMaintenanceOperation(callID)``
  Enlève la demande d'intervention du système, par exemple si elle avait été
  ajouté par erreur.
  Permet de planifier les modalité des maintenances sur site, comme leur
  fréquence, ou encore demander une maintenance exceptionnel sur une site, par
  exemple en cas d'urgence.

Suivi en temps réel des opérations de maintenance
-------------------------------------------------

De la même manière, cette partie ne permet d'obtenir que des informations brutes
concernant une opération de maintenance, c'est à dire consulter une sorte de
fichier de journalisation associé à la tâche de maintenance.

``callID getMaintenanceOperationStatus(callID, status)``
  ``status`` est une structure de donnée qui contient des enregistrement de mise
  à jour d'une tâche de maintenance. Chaque enregistrement peut contenir (non exhaustif) :
  
  - Un horodatage (fuseau horaire GMT, quelque soit l'emplacement du site sur lequel est fait la maintenance).
  - Des coordonnées GPS
  - Un statut pour la tâche (terminée, en cours, en approche du site, etc.).
  - Un commentaire textuel.

  Ces données sont fournies par l'appareillage du technicien envoyé sur site (de
  type *smartphone*).

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

Réception de données depuis le site distant
  Cette fonctionnalité permet de recevoir des données depuis le site distant
  vers le site central.

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


