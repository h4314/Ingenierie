Spécifications fonctionnelles
=============================

Systeme embarque
----------------

Le système embarqué proposé doit être utilisable en environnement dangereux, comme à proximité de 
produits chimiques, d'endroits à risques d'incendies ou difficilement atteignables par l'homme.
Il doit être facilement reliable à différents capteurs. Actuellement, un seul capteur par cuve est
nécessaire afin de mesurer le niveau de liquide, cependant il est raisonnable de penser qu'on 
pourrait ajouter d'autres mesures, telles que la température ou la toxicité. On estime donc 
qu'il faut prévoir au moins cinq capteurs possibles par cuve.
Toutes les cuves d'un site se trouvent dans un diamètre d'une centaine de mètres. Les dispositifs
doivent donc pouvoir communiquer entre eux à cette distance.
Pour des raisons évidentes, le système doit disposer d'une grande autonomie afin de ne pas 
obliger des opérations de maintenance sur site en cas de panne. De même, les maintenances
et les mises à jour doivent pouvoir être effectuées à distance.


- Performances du système embarqué :

 - possibilité de brancher au moins 5 capteurs par dispositif
 - portée efficace d'environ 100m
 - autonomie minimale d'un an
 
 
Communication
-------------

La communication doit être gérée par un réseau offrant une bonne couverture sur l'ensemble de l'europe.
La communication doit être fiable, c'est-à-dire sans pertes et au fonctionnement constant garanti.

- Performances  du système de communication :

 - le site central pourra être déployé (voir migré à tout moment) partout en Europe, et a fortiori n'importe où dans le monde.
 
  - les sites distants sont situés n'importe où en Europe, y compris les endroits les plus reculés et les moins bien desservis, que ce soit en terme de d'énergie, de télécommunications ou d'infrastructures routières.
  - la communication devra être fiable
    
	- les informations ne doivent pas être perdues
    
	- certaines stations critiques doivent inclure des capacité de reprise ou de capacité de redondance pour garder une disponibilité maximale
  
  - la communication doit être la moins coûteuse possible en énergie
  
  

Capteurs
--------

Les capteurs doivent être capable de mesurer grossièrement le niveau d'un liquide.


Interface
---------

Afin d'administrer à distance les différents sites, les utilisateurs doivent avoir une interface portable.
L'utilisation de cette interface doit être simple et générique, facilitant l'accès aux informations 
sur tous les sites, ainsi que sur les éléments mobiles tels que les véhicules envoyés pour la maintenance.


Localisation
------------

Il est nécessaire de pouvoir localiser sur une carte les emplacemments précis des cuves. Cependant,
comme leurs coordonnées sont fixes, aucun système n'est primordial dans un premier temps. De plus, les 
camions transportant du matériel d'un site à un autre sont censés être équipés de gps. C'est pourquoi
nous ne nous focaliserons pas sur ce point.


Production d'énergie
--------------------

Le système de gestion du contenu d'un réservoir a besoin d'énergie pour alimenter les capteurs, le système embarqué et les équipements de communication. Le système doit pouvoir fonctionner en autonome et de façon écologique au niveau d'énergie.

Estimation des besoins d'énergie pour une station
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Dans une station, nous avons deux principaux consommateurs d'énergie: le chipset du système embarqué et le modem GSM/GPRS. 
Pour le chipset, nous nous basons sur un produit qui a une très bonne autonomie. La puissance à l'état repos est inférieur à 1 mWatt, qui est négligeable. Quand il est en émission ou en réception, la puissance ne dépasse pas 0,1 Watt. 
En ce qui concerne le modem, la puissance au repos est de l'ordre de 0,1 Watt et celle en émission/réception est au maximum 3 Watt.
En conséquence, une alimentation de 12V et 5 Watt est suffisante pour notre système. Si on estime que les équipements échangent des données avec le serveur toutes les minutes pendant 1 seconde, il faut 0.2 Amp*h d'électricité par jour ou 6 Amp*h par mois sous un voltage de 12 V. 
