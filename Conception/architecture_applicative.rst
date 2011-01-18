Architecture applicative
========================
Site central
-------------
L'architecture applicative sur le site central se décompose en trois couches: base de données, noyau applicatif et un client web.
Base de données
~~~~~~~~~~~~~~~
Le système central dispose d'une base de données qui s'occupe de la centralisation et du contrôle des données.
La solution que nous avons choisi est le PostgreSQL. C'est un système de base de données libre qui est largement reconnu pour son comportement stable et aussi pour ses possibilités de programmation étendues, directement dans le moteur de la base de données, via PL/pgSQL. Nous utilisons également le plugin PostGIS pour activer la manipulation d'informations de géométrie (points, lignes, polygones). Ce fonctionnement très particulier peut faciliter largement la gestion des données géographiques(ex. la localisation des stations et des cuves).
Dans cette base de données, plusieurs types de données seront sauvegardés. Il y a d'abords des données propres du système telles que les informations des stations, leurs configurations. Ensuite, on a des valeurs de mesure pour chaque station et chaque capteur plus précisément. Enfin, pour la raison de traçabilité, les traces applicatifs du serveur et de tous les systèmes embarques sont enregistrés.

Noyau applicatif
~~~~~~~~~~~~~~~~~
Le noyau applicatif constitue le moteur du système informatique.
Nous développons des applications en Java pour le traitement des données. Elles communiquent entre la base de données et l'interface utilisateur.
Dans un sens, les applications reçoivent les données émites par des stations. Elles font des analyses sur ces données. Ensuite elles les stockent dans la base de données et elles les fournissent à l'interface pour afficher aux utilisateurs.
Dans un autre, les applications reçoit des commandes des utilisateurs. Elles vérifient la cohérence de ces commandes avant de les envoyer à la station destinataire.

Planification, gestion alarme
Client web
~~~~~~~~~~~
Les utilisateurs abordent le système par la couche clients.
Nous obtenons la technologie web pour réaliser l'interface client. HTML5 (HyperText Markup Language 5) est la dernière révision du principal langage du web. C'est un futur standard incontournable du web qui est déjà odopté par des acteurs majeurs. Elle permet de concevoir une interface conviviale pour utilisateur sur un pc ainsi que sur un mobile. Accès au hardware.
Grâce à ce client web, utilisateur peut accéder aux données brutes des stations, visualiser des indicateurs ou des graphes calculés et générés par le noyau applicatif, configurer le système ou envoyer une commande manuel à une station. Le client web possède une procédure d'authentification permettant de contrôler des accès aux données et le droit aux différentes fonctionnalités.


Sites distants
---------------
Un OS léger tourne sur chacun des système embarqué. Cette OS offre la possibilité d'effectuer des traitements mineurs ainsi que l'émission et la réception des données.









