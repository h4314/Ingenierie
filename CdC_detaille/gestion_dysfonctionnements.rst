===============================================================
Suivi temps réel, gestion des alarmes et des dysfonctionnements
===============================================================



Présentation du document
========================

Ce document présente une analyse du module permettant un suivi en temps réel 
des urgences signalées par des alarmes. C'est un cahier des charges faisant office de contrat
quant aux fonctionnalités de ce module.

Présentation du problème
========================
Objectifs, principe du logiciel
-------------------------------

Lorsque le système détecte une fuite ou un autre dysfonctionnement dans une des cuves, il déclenche une alarme au site central, permettant ainsi aux techniciens présents de pouvoir réagir rapidement. 
Le logiciel offre également la possibilité de pallier au mieux à ces dysfonctionnements. En cas de fuite ou de batterie à recharger, il offre une interface utile permettant d'affréter un transport correspondant dans les plus brefs délais.
Ce module est étroitement lié à celui d'aide à la décision puisque que ce sera ce dernier qui saura déterminer certaines pannes ou proposer des solutions, ainsi qu'à celui de logistique car il faut savoir où se trouvent les camions afin de choisir lequel affréter pour réparer une panne.

Formulation des besoins généraux
---------------------------------

- Identifier précisément un dysfonctionnement (numéro de cuve, site, type de panne)

- Déclencher une alarme en cas de détection de dysfonctionnement.

- Faire appel au module d'aide à la décision pour proposer une solution

- Les techniciens doivent avoir la possibilité de prendre une solution différente de celle proposée par le système.

- Consulter le module de logistique pour déterminer quels camions sont les mieux placés pour gérer une panne.

- Proposer une interface permettant d'affréter un transport.

Portée, développement, mise en oeuvre, organisation de la maintenance
---------------------------------------------------------------------
Ce module ne se sert pas directement des données de la base de données centrale, car son but premier est de savoir s'il y a un problème ou non. Cela peut être déterminé par plusieurs facteurs. Le module d'aide à la décision peut déterminer s'il y a une fuite. Ou encore, si une cuve manque plusieurs envois de données, on en déduit qu'il y a dysfonctionnement.
Ce n'est qu'une fois qu'un dysfonctionnement est détecté qu'on peut accéder à la base de données en faisant le moins de requêtes inutiles possible. On saura si le problème peut venir de la communication avec un site distant, du niveau de liquide dans une cuve ou d'une défaillance matérielle sur un site distant.

Limites
-------
Ce module est loin d'être autonome car il peut souvent s'apparenter au module d'aide à la décision. Il présente par conséquent les mêmes limites : quelles que soient les solutions qu'il propose, il y a toujours besoin d'un être humain derrière la machine pour prendre la décision finale.


Exigences fonctionnelles
========================
Fonctions de base, performances et aptitudes
--------------------------------------------

- Quand plusieurs alarmes sont levées et ne peuvent être traitées en même temps, il faut les classer par ordre d'importance. C'est-à-dire en fonction de la gravité de la situation, ou bien de la facilité d'accès de la station concernée.

- Toutes les alarmes et leur résolutions doivent être enregistrées afin de pouvoir retracer le fonctionnement du logiciel en cas d'anomalie.

- Chaque alarme est associée à un élément, que ce soit une cuve pour indiquer un problème de niveau ou un matériel pour indiquer un malfonctionnement.

Contraintes d'utilisation
-------------------------

En cas d'alarme, il faut parfois pouvoir réagir vite. C'est pourquoi, en l'absence d'un cadre, tout technicien présent au site central doit être capable de prendre le logiciel en main le temps de pouvoir prévenir un cadre qualifié.

Flexibilité, variation de coût associé
--------------------------------------

Le logiciel n'a pas réellement besoin de flexibilité car il recherche plutôt une efficacité immédiate. Néanmoins, pour les raisons exposées dans les contraintes d'utilisation, il doit être accessible à tout le monde, y compris des personnes non familières avec la gestion des sites distants. C'est pourquoi on prévoit une interface généraliste servant simplement à guider l'utilisateur dans sa démarche.

Contraintes imposées, faisabilité technologiques et éventuellement moyens
=========================================================================
Sûreté, planning, organisation, communication
----------------------------------------------

Il faut tout d'abord définir de manière exhaustive les différentes pannes possibles et leur priorité afin de savoir lesquelles gérer en premier si elles apparaissent en même temps.
Afin de pouvoir réagir rapidement à chaque alarme, tout le personnel devrait suivre une formation minimale quant aux premières décisions à prendre lors d'une panne.

Complexité
----------

La complexité de cette application repose dans la capacité de réaction du logiciel lorsqu'une alarme est levée.

documentation
-------------

Des logs doivent être gardés afin de pouvoir complètement retracer le fonctionnement du logiciel, les alarmes levées et les solutions adoptées. Ainsi, chaque alarme sera associée à un statut "en cours", "résolu" ou "non résolu".
Les logs sont stockés dans la base de données centrale.

Configuration cible
====================
Matériel et logiciels
----------------------

Il n'est pas besoin de matériel spécial pour ce module. Les alarmes sont levées en fonction des données fournies par les sites distants, des calculs effectués par le module d'aide à la décision, ou des données issues de la base de données centrale.
Cela dit, il doit également être exécutable à partir d'un PDA afin que les décisions puissent être prises de partout.


