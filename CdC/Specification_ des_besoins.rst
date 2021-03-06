Sp�cifications fonctionnelles
=============================

Systeme embarque
----------------

Le syst�me embarqu� propos� doit �tre utilisable en environnement dangereux, comme � proximit� de 
produits chimiques, d'endroits � risques d'incendies ou difficilement atteignables par l'homme.
Il doit �tre facilement reliable � diff�rents capteurs. Actuellement, un seul capteur par cuve est
n�cessaire afin de mesurer le niveau de liquide, cependant il est raisonnable de penser qu'on 
pourrait ajouter d'autres mesures, telles que la temp�rature ou la toxicit�. On estime donc 
qu'il faut pr�voir au moins cinq capteurs possibles par cuve.
Toutes les cuves d'un site se trouvent dans un diam�tre d'une centaine de m�tres. Les dispositifs
doivent donc pouvoir communiquer entre eux � cette distance.
Pour des raisons �videntes, le syst�me doit disposer d'une grande autonomie afin de ne pas 
obliger des op�rations de maintenance sur site en cas de panne. De m�me, les maintenances
et les mises � jour doivent pouvoir �tre effectu�es � distance.


- Performances du syst�me embarqu� :

 - possibilit� de brancher au moins 5 capteurs par dispositif
 - port�e efficace d'environ 100m
 - autonomie minimale d'un an
 
 
Communication
-------------

La communication doit �tre g�r�e par un r�seau offrant une bonne couverture sur l'ensemble de l'europe.
La communication doit �tre fiable, c'est-�-dire sans pertes et au fonctionnement constant garanti.

- Performances  du syst�me de communication :

 - le site central pourra �tre d�ploy� (voir migr� � tout moment) partout en Europe, et a fortiori n'importe o� dans le monde.
 
  - les sites distants sont situ�s n'importe o� en Europe, y compris les endroits les plus recul�s et les moins bien desservis, que ce soit en terme de d'�nergie, de t�l�communications ou d'infrastructures routi�res.
  - la communication devra �tre fiable
    
	- les informations ne doivent pas �tre perdues
    
	- certaines stations critiques doivent inclure des capacit� de reprise ou de capacit� de redondance pour garder une disponibilit� maximale
  
  - la communication doit �tre la moins co�teuse possible en �nergie
  
  

Capteurs
--------

Les capteurs doivent �tre capable de mesurer grossi�rement le niveau d'un liquide.




Interface
---------

Afin d'administrer � distance les diff�rents sites, les utilisateurs doivent avoir une interface portable.
L'utilisation de cette interface doit �tre simple et g�n�rique, facilitant l'acc�s aux informations 
sur tous les sites, ainsi que sur les �l�ments mobiles tels que les v�hicules envoy�s pour la maintenance.


Localisation
------------

Il est n�cessaire de pouvoir localiser sur une carte les emplacemments pr�cis des cuves. Cependant,
comme leurs coordonn�es sont fixes, aucun syst�me n'est primordial dans un premier temps. De plus, les 
camions transportant du mat�riel d'un site � un autre sont cens�s �tre �quip�s de gps. C'est pourquoi
nous ne nous focaliserons pas sur ce point.


Production d'�nergie
--------------------

Le syst�me de gestion du contenu d'un r�servoir a besoin d'�nergie pour alimenter les capteurs, le syst�me embarqu� et les �quipements de communication. Le syst�me doit pouvoir fonctionner en autonome et de fa�on �cologique au niveau d'�nergie.

Estimation des besoins d'�nergie pour une station
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Dans une station, nous avons deux principaux consommateurs d'�nergie: le chipset du syst�me embarqu� et le modem GSM/GPRS. 
Pour le chipset, nous nous basons sur un produit qui a une tr�s bonne autonomie. La puissance � l'�tat repos est inf�rieur � 1 mWatt, qui est n�gligeable. Quand il est en �mission ou en r�ception, la puissance ne d�passe pas 0,1 Watt. 
En ce qui concerne le modem, la puissance au repos est de l'ordre de 0,1 Watt et celle en �mission/r�ception est au maximum 3 Watt.
En cons�quence, une alimentation de 12V et 5 Watt est suffisante pour notre syst�me. Si on estime que les �quipements �changent des donn�es avec le serveur toutes les minutes pendant 1 seconde, il faut 0.2 Amp*h d'�lectricit� par jour ou 6 Amp*h par mois sous un voltage de 12 V. 
