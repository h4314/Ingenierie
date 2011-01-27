===================
Dossier de synthèse
===================

.. contents:: Sommaire 
.. sectnum::

Ce document présente de manière synthétique la solution retenue pour répondre à l'appel d'offre de la COPEVUE.

Introduction
**************************************************

Ce document présente de manière synthétique la solution retenue pour répondre à l'appel d'offre de la COPEVUE: "Système de monitoring à distance de sites isolés".

Dans ce document seront présentés les différents aspects du futur système ainsi que les fonctionnalités qui lui seront associées.

Terminologies et Abréviations
****************************************** 
**TODO**
lister et définir les différents termes.

Cadre de l'étude et objectifs
*******************************************

Le COPEVUE (Comité Pour la Protection de l'EnVironnement de l'Union Européenne) souhaite étudier un système de monitoring à distance de sites isolés. L'objectif est d'étudier et de concevoir un système complet, autonome et générique de mesure et de monitoring ainsi que le pilotage, la configuration et la maintenance à distance de ces stations. Le résultat doit constituer une solution évolutive, autonome, fiable et déployable à l'échelle européenne.
Ce système se veut être un parfait palliatif aux dysfonctionnements actuels en apportant une réponse aux problématiques détaillées ci-dessous.

De nombreuses régions d'Europe sont faiblement desservies pour des raisons :

* démographiques, le faible peuplement de ces zones fait que les infrastructures de transport sont peu développées ;
* géographiques, certaines de ces zones sont difficilement accessibles par la difficulté et le coût d'installation d'infrastructures.

La problématique réside ici en la capacité d'autonomie des stations isolées (en
énergie, déchets, présence humaine, etc.).  Ces stations doivent être
régulièrement surveillées pour veiller à un fonctionnement optimale tout en
évitant les risques environnementaux.  Ces visites permettent de s'assurer que
les stations sont bien ravitaillées, nettoyées, vidées et fonctionnelles.

A l'échelle européenne il n'existe aucun organisme centralisé et
donc aucun système de gestion chargé de la surveillance de sites distants
isolés.  Notre solution vise donc à informatiser ce système d'information que ce
soit au niveau des sites distants ou par la mise en place d'un site central de
monitoring.  Il s'agit avant tout d'un projet technique mais qui pose de solides
fondations quant à la mise en place d'un organisme visant à fédérer l'ensemble
des acteurs européens.

Pour cet appel d'offre, seront
visées uniquement les stations réservoirs utilisées pour stocker des liquides
(eau, carburant et autres substances) ou bien des déchets.

Rappel synthétique des dysfonctionnement
*********************************************

La décentralisation de la surveillance des sites isolés est source de
nombreux dysfonctionnements qui peuvent être déclinés en deux grandes catégories : 
- un gaspillage financier (argent provenant pour la majorité des cas des
contribuables) 
- un risque environnemental important, non contrôlé.

Plusieurs facteurs sont sources de gaspillage financier :

* La logistique. Il n'existe pas de planification globale et donc pas d'optimisation dans les livraisons/enlèvements de contenant et systématiquement un camion se retrouve avec un chargement nul sur un des trajets (l'aller ou le retour).
* La surveillance. Celle-ci est effectuée par des opérationnels et est donc fortement coûteuse, en particulier lorsque l'on constate que la majorité des déplacements ne débouche sur aucune opération de maintenance. Il s'agit donc d'une monopolisation des ressources humaines pour une tâche sans réelle valeur ajoutée par rapport à ce qu'elles pourraient apporter.
* Une surveillance non globale. L'éparpillement de la gestion de ces sites empêche de faire des économies d'échelles à de nombreux niveaux que ce soit au niveau de la surveillance ou bien dans la mise en commun des achats de contenant ou de services de transport.

De nombreux points favorisent les risques environnementaux :

* Oublis. Le système reposant uniquement sur des ressources humaines, de nombreux oublis de ravitaillement de cuves ont été constatés. C'est totalement inacceptable pour des cuves stratégiques comme celles dédiées à la lutte contre les incendies.
* Fuites. En plus d'être une perte financière, les fuites, suivant le contenant de la cuve, peuvent s'avérer très dangereuses d'un point de vue écologique. Le problème est que ces fuites sont constatées bien souvent trop tard du fait d'une surveillance manuelle, souvent fortement espacée dans le temps.
D'une manière générale, il manque une traçabilité des opérations effectuées par les divers acteurs et ne permet donc pas un monitoring global.

Description des axes de progrès
***********************************

Deux axes de progrès ont été retenus:

* Gain en termes de coûts directs
   * Centralisation de la surveillance : économies d'échelle.
   * Une meilleure logistique, notamment en termes de transport.
   * Des ressources humaines mieux utilisées. Les opérationnels doivent passer moins de temps à la surveillance (faible valeur ajoutée) pour se concentrer sur leur métier.

* Une qualité de surveillance accrue (des réductions de coûts indirects ou qualitatifs)

   * Un meilleur contrôle des risques environnementaux
   * Un gaspillage des ressources réduit au minimum (énergie, déchets, contenant des cuves)
   * Automatisation de la surveillance, fiabilité augmentée
   * Une meilleure traçabilité des opérations

Descriptions des exigences non fonctionnelles
*************************************************

Les exigences non fonctionnelles que doit respecter et qui seront respectées par le futur système sont les suivantes:

- Intégration de l'existant
- Fiabilité
- Evolutivité et Maintenabilité
- Limitations Technologiques
- Généricité
- Réutilisation
- Ergonomie
- Traçabilité

Description des besoins et des exigences fonctionnelles
*************************************************************

Ci-dessous la liste des besoins et des exigences fonctionnelles qui sont prises en compte:

- Monitoring à distance
  - Monitoring de l'état des cuves
  - Monitoring des anomalies
  - Localisation géographique
- Maintenance à distance
- Maintenance sur site
- Traitements sur site central
  - Aggrégation des données provenant des sites centraux
  - Planification des interventions
  - Suivi en temps réel des interventions
  - Aide à la décision
- Traitements sur station
  - Relevé des capteurs
  - Uniformisation des données
  - Circulation de l'information sur le réseau interne
  - Communication de l'information vers le site central
  - Optimiser la gestion de l'énergie


Présentation de la solution proposée
****************************************

Architecture globale
########################

.. image:: images/architecture.png
   :scale: 50%

**TODO** Descriptions

Architecture matérielle
########################

Site central
==============

Postes de travail
------------------

Il convient de mettre en place un réseau local regroupant ces postes afin d'une part de partager la connexion internet et d'autre part d'utiliser ce réseau à des fins de partage de documents.

Serveurs
---------

Tout d'abord l'hébergement et la maintenance de ces serveurs seront laissés à la charge d'un prestataire externe pour des raisons de coûts, de fiabilité, de sécurité et de haute disponibilité.
Des serveurs privées seront choisis afin de garder un contrôle total du système et de garantir des performances suffisantes dans les traitements. 

Dans un souci d'extensibilité et de mise à l'échelle, l'architecture serveur pourra être découpée en plusieurs serveurs chacun dédié à une fonctionnalité : serveur web, serveur applicatif, serveur hébergeant la base de données, etc. Les performances pourront être améliorées grâce à la technique du load-balancing et donc exploiter la redondance.

En cas de panne, le prestataire devra être en mesure de remettre en marche le système de manière fonctionnelle rapidement et le nombre de pannes doit être limité dans l'année (99,9% de disponibilité préconisée, soit moins de 8,75 heures par an).

Sites distants
===============

Capteurs
---------

Chaque cuve sera équipée d'un ou plusieurs capteurs. Bien que générique, ce système ne considérera pour l'instant que la mise en place de capteur de niveau de liquide.
Le choix est porté vers un capteur peu cher, autonome et interfaçable avec le système embarqué de la cuve :  Capteur OTT RLS (75 dollars pièce).

Système embarqué
------------------

Chaque cuve comprendra un système embarqué. La solution intégrée Ember EM250 a été retenue.

Avantages:

- solution tout intégrée
- faible coût
- répond aux contraintes environnementales.

Communication
-------------

Utilisation du réseau GPRS
~~~~~~~~~~~~~~~~~~~~~~~~~~

Cette solution nécessite l'utilisation du réseau des télécommunications GSM. Le réseau GPRS est en réalité une extension s'appuyant sur le réseau GSM et a l'avantage d'une part de pouvoir rester connecté et d'autre part d'utiliser en plus des canaux de type voix, une passerelle vers le réseau internet. La facturation ne se fait non plus à la durée mais au débit.

Architecture du réseau GSM/GPRS

.. image:: images/reseau_gsm.png
   :scale: 50%

Les pré-requis sont :

* être à portée d'une antenne de télécommunication (BTS)
* nécessite un abonnement auprès d'un FAI/opérateur téléphonique par site distant

La couverture du réseau GPRS (et donc GSM) sur le territoire européen est quasi totale. Il faudra s'assurer préalablement de choisir l'opérateur mobile offrant la meilleure couverture, ce qui sera donc variable suivant les pays. Dans la même idée il faudra veiller à traiter avec un opérateur présent dans la majorité des pays européens afin de négocier des prix intéressants avec un support de qualité.

Un exemple de couverture, en Norvège (opérateur : Telenor), qui comprend un certains nombres de sites isolés, notamment dans le nord :

.. image:: images/telenor.png
   :scale: 50%

Production d'énergie
----------------------

Chaque composant sera hautement indépendant vis à vis de sa consommation électrique. Chaque composant consomme peu, et de plus est capable de rentrer en mode veille extrêmement peu consommateur.
Ils seront alimentés via des piles et pour certaines régions couplés avec un mini panneau solaire pour la recharge (50€ par panneau et 50€ - 200€ par pile).


Architecture applicative
#########################

Site central
=============

L'architecture applicative sur le site central se décompose en trois couches: base de données, noyau applicatif et client web.

Base de données
-----------------

Le système central dispose d'une base de données qui s'occupe de la centralisation et du contrôle des données.
La solution que nous avons choisi est la base de données relationnelle objet PostgreSQL. 

Noyau applicatif
-------------------

Le noyau applicatif constitue le moteur du système informatique.
Seront développées des applications en Java pour traiter des données, configurer le système, gérer la planification et des alarmes. 

Client web
------------

Les utilisateurs abordent le système par un navigateur internet.
L'interface client sera donc réalisé avec des technologies standards du web (HTML5). Cela garanti un accès au système aussi large que possible. Les utilisateurs pourront donc accéder au système par un navigateur web standard. 

Sites distants
===============

Un OS très léger tourne sur chacun des système embarqué. Cette OS offre la possibilité d'effectuer des traitements mineurs ainsi que l'émission et la réception des données. Dans chacune des stations, on distingue un système maître et des systèmes esclaves.

Système esclave
------------------

Le système esclave se réveille à un intervalle de temps régulier qui est paramétrable. Il effectue un nombre de mesures qui est également paramétrable en tenant compte de type de capteur, niveau de batterie du système etc. Les valeurs de capteurs seront transmises au système embarqué de manière brute. Le système embarqué calcul la moyenne des valeurs mesurées et l'envoie au système voisin en format uniformisé en rajoutant l'identifiant de cuve, unité de valeur etc... Au cas où un dysfonctionnement est détecté, une alarme sera générée et envoyée.

Système maître
---------------

Le système maître possède le même fonctionnement que le système esclave au niveau de récolte de données. En plus, il reçoit les données de systèmes esclaves qui se trouvent dans la même station. Il est chargé d'envoyer ces données par le réseau GSM en protocole Http au serveur central.

Synchronisation
----------------

Dans une station, tous les systèmes embarqués seront synchronisés. Il est
possible de paramétrer de sorte qu'ils se réveillent en même temps régulièrement
pour effectuer la mesure, le traitement, l'émission et la réception de données.
Cette synchronisation permet aux systèmes de se mettre en veille profonde
(Fermeture des récepteur et émetteur) durant le reste du temps afin de réduire
la consommation d'énergie.



Coût de la solution
***************************

Etude + Conception + Développement (site central + distants)
1 an: équipe pluridisciplinaire de 10 personnes. 600 à 750 k€

Site distant (matériel)
Capteurs (x10): 75€
Piles (x10): 25 à 190€
Panneaux solaires (x10): 30 à 100€
Modem GSM/GPRS (x1): 100 à 300€
Total (pour un site): 1400 à 4000€

**TODO**: Non complet. (Intégration, Formation, Maintenance, etc.)

Mise en place du système
********************************

Description de la mise en place du système
############################################

**TODO**

Plan de formation
#####################

**TODO**

Retour sur Investissment (ROI)
####################################

**TODO**
