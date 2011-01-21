Architecture applicative
========================

Site central
-------------
L'architecture applicative sur le site central se décompose en trois couches: base de données, noyau applicatif et client web.

Base de données
~~~~~~~~~~~~~~~
Le système central dispose d'une base de données qui s'occupe de la centralisation et du contrôle des données.
La solution que nous avons choisi est le PostgreSQL. C'est un système de base de données libre qui est largement reconnu pour son comportement stable et aussi pour ses possibilités de programmation étendues, directement dans le moteur de la base de données, via PL/pgSQL. Nous utilisons également le plugin PostGIS pour activer la manipulation d'informations de géométrie (points, lignes, polygones). Ce fonctionnement très particulier peut faciliter largement la gestion des données géographiques(ex. la localisation des stations et suivi des camions en temps réel). 
Les interactions avec la couche base de données se font par l'intermédiaire de commandes PL/PGSQL standardisées. Ces commandes permettent à la fois de consulter les données enregistrées, d'en enregistrer de nouvelles ou de modifier celles existantes.
Dans cette base de données, plusieurs types de données seront sauvegardés. Il y a d'abords des données propres du système telles que les informations des stations, leurs configurations. Ensuite, on a des valeurs de mesure pour chaque station et chaque capteur plus précisément. Enfin, pour la raison de traçabilité, les traces applicatifs du serveur et de tous les systèmes embarqués sont enregistrés. Ces informations pourront être utilisées en cas de problème ou d'analyse de l'activité.

Noyau applicatif
~~~~~~~~~~~~~~~~~
Le noyau applicatif constitue le moteur du système informatique.
Nous allons développer des applications en Java pour traiter des données, configurer le système, gérer la planification et des alarmes. 
 - Traitement des données
   L'application reçoit des données émites par des stations. Elles les persiste dans la base de données. Elle font également des analyses sur ces données et les fournissent à l'interface pour présenter aux utilisateurs.	
 - Configuration du système
   L'application permet aux utilisateurs à paramétrer ou commander le système.  Elles vérifient la cohérence des commandes et des paramétrage avant de les envoyer à la station destinataire. Elle se charge aussi de la mise à jour des système embarqués.
 - Planification
   L'applicaion est capable de surveiller le niveau des réservoirs grâce aux données envoyés par des captuers et suivre en temps réel des camions équipés de GPS. Cela permet de planifier les trajets des camions.
 - Gestion des alarmes
   L'application reçoit des alarmes qui signalent un niveau faible de batterie ou d'autre dysfonctionnements de systèmes embarqués. Elle est capable de réagir de façon automatique pour résoudre certains problèmes ou avertir l'utilisateur.

Client web
~~~~~~~~~~~
Les utilisateurs abordent le système par la couche clients.
Nous obtenons la technologie web pour réaliser l'interface client. Cela garanti un accès au système aussi large que possible. Les utilisateurs pourront donc accéder au système par un navigateur web standard. HTML5 (HyperText Markup Language 5) est la dernière révision du principal langage du web. C'est un futur standard incontournable du web qui est déjà odopté par des acteurs majeurs. Elle permet de concevoir une interface conviviale pour utilisateur sur un pc ainsi que sur un mobile. Le stockage des données en mode déconnecté et l'API de géolocalisation de HTML5 est surtout très pratique pour le client mobile/PDA.
Grâce à ce client web, utilisateur peut accéder aux brutes des stations, visualiser des indicateurs ou des graphes calculés et générés par le noyau applicatif, configurer le système ou envoyer une commande manuel à une station. Le client web possède une procédure d'authentification permettant de contrôler des accès aux données et le droit aux différentes fonctionnalités.


Sites distants
---------------
Un OS très léger tourne sur chacun des système embarqué. Cette OS offre la possibilité d'effectuer des traitements mineurs ainsi que l'émission et la réception des données. Dans chacune des stations, on distingue un système maître et des systèmes esclaves.

Système esclave
~~~~~~~~~~~~~~~
Le système esclave se réveille à un intervalle de temps régulier qui est paramétrable. Il effectue un nombre de mesures qui est également paramétrable en tenant compte de type de capteur, niveau de batterie du système etc. Les valeurs de capteurs seront transmises au système embarqué de manière brute. Le système embarqué calcul la moyenne des valeurs mesurées et l'envoie au sysème voisin en format uniformalisé en rajoutant l'identifiant de cuve, unité de valeur etc... Au cas où un dysfonctionnement est détecté, une alarme sera généré et envoyé.
Quand le système esclave reçoit un message, s'il s'agit du message d'un système voisin destiné au système maître, il le transmet au système suivant. Si le message lui est destiné contenant des données de configuration, le système doit se reconfigurer.

Système maître
~~~~~~~~~~~~~~~
Le système maître possède le même fonctionnement que le système esclave au niveau de récolte de données. En plus, il reçoit les données de systèmes esclaves qui se trouvent dans la même station. Il est chargé d'envoyer ces données par le réseau GSM en protocol Http au serveur central.
Le système maître reçoit également des messages de configuration ou des commandes d'utilisateur. Il les redistribue aux systèmes esclaves.

Synchronisation
~~~~~~~~~~~~~~~
Dans une station, tous les systèmes embarqués seront synchronisés. Il est possible de paramétrer de sorte qu'ils se réveillent en même temps régulièrement pour effectuer la mesure, le traitement, l'emission et la réception de données. Cette synchronisation permet aux systèmes de se mettre en veille profonde (Fermeture des recepteur et émetteur) durant le reste du temps afin de réduire la consommation d'énergie.






