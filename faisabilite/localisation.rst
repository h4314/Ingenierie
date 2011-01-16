Analyse de faisabilité du système de localisation géographique
==============================================================

Localisation des stations distantes
------------------------------------

Etant donné que les stations distantes ne sont pas destinées à être déplacées, ou alors que de manière très ponctuelle, il ne sera pas nécessaire de mettre en place un système de localisation par statellite (type GPS).
L'idée est d'enregistrer la position de chaque station/cuve existante ou bien effectuer un unique relevé pour celles qui seront mises en place.

Localisation de la flotte des véhicules de ravitaillement
-------------------------------------------------------

Les véhicules, étant mobiles, pourraient être équipés de balise de suivi GPS. Celles-ci utilisent le réseau satellitaire pour déduire la position en temps réel des véhicules. La communication des coordonnées pourra être ensuite effectuée par le réseau GSM/GPRS, ce qui serait moins coûteux que de le faire transiter par un réseau satellitaire.

Gestion des dispositifs géolocalisés depuis le site central
-----------------------------------------------------------

Côté site central la position des dispositifs pourraient être présentées et traitées de différentes manières.
Cette infrastructure nécessite (en exemples seront données des solutions reposant sur des données libres, des protocoles standards et des technologies open source, donc potentiellement gratuites à l'acquisition et totalement intéropérable avec d'autres systèmes) :
 * Une base de données spatiale. Exemple : PostgreSQL/PostGIS
 * Des données géographiques à l'échelle européenne. Exemple : données libres d'Open Street Map
 * Un serveur cartographique. Exemple : GeoServer ou MapServer
 * Des librairies de présentation et d'utilisation des services géographiques. Exemple : GeoTools (clients lourds), OpenLayers (clients légers)
