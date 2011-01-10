Synth�se s�ance 7/01 
====================

Objectifs du document 
---------------------

Etude (draft) de faisabilit� des moyens de communication longue distance entre les sites distants et le site central.

Fait
----

 * recherche sur les moyens de communication courte distance (r�seaux de capteur type Zigbee) => redondance avec les recherches de Paul et Pierrick
 * recherche sur les moyens de communication longue distance
   * GPS
   * Courant porteur libre
   * r�seau GSM/GPRS/UMTS
 * avantages/inconv�nients
   * disponibilit�
   * fiabilit�
   * couts
   * adaptation � nos besoins

Reste � faire 
-------------

 * finir la r�daction 
 * comparatifs des solutions en termes de :
  * couts
  * utilisation (d�pend de la zone g�ographique)
  * difficult� d'impl�mentation (technique ou politique)
 * quel syst�me embarqu� sera charg� de g�rer la communication au site distant ?
  * un modem + puce GPRS ?
  * voir avec Paul et Pierrick

Modifications (08/01) 
---------------------

 * suite des recherches
 * d�coupage avec un plan
 * r�daction
 * *reste a faire : finir le d�tail des solutions + le bilan*



Communication longue distance
=============================

Probl�matique
-------------

Cette �tude a pour objectifs d'effectuer un �tat de l'art en termes de communication longue distance. En l'occurence, ici, il s'agit de trouver des solutions potentielles permettant de r�pondre � la question suivante : *comment s'effectuera la communication entre les sites distants et le site central de monitoring ?*

Pour r�pondre � cette question, il convient dans un premier temps de rappeller les contraintes inh�rentes :
 * le site central pourra �tre d�ploy� (voir migr� � tout moment) partout en Europe, et a forciori n'importe o� dans le monde.
 * les sites distants sont situ�s n'importe o� en Europe, y compris les endroits les plus recul�s et les moins bien desservis, que ce soit en terme de d'�nergie, de t�l�communications ou d'infrastructures routi�res.
 * la communication devra �tre fiable
   * les informations ne doivent pas �tre perdues
   * certaines stations critiques doivent inclure des capacit� de reprise ou de capacit� de redondance pour garder une disponibilit� maximale
 * la communication doit �tre la moins co�teuse possible
 * le mat�riel devra supporter des conditions climatiques extremes

Dans un deuxi�me temps, les crit�res de selection d'une solution se porteront �galement sur la teneur des communications : *quelles donn�es seront amen�es � circuler dans un sens, comme dans l'autre ?*

Du site central vers les sites distants :
 * mises � jour des logiciels (fr�quence : maximum toutes les semaines, mais certainement beaucoup plus espac�)

Des sites distants vers le site central :
 * les informations provenant des capteurs (fr�quence : de l'ordre de la minute)

Enfin, la taille du r�seau est � prendre en compte, nous partirons d'une base de simulation 10 fois plus importante que l'existant scandinave, soit :
 * 100 sites distants * 10 = 1000 sites distants
 * 1000 sites distants * 10 cuves = 10000 cuves

Solutions possibles
-------------------

A l'heure actuelle trois m�thodes de communication longue distante peuvent �tre envisag�es pour ce syst�me :
 * par le r�seau GPRS (2G+), autrement dit par le r�seau GSM et internet
 * par le r�seau GPS, autrement dit par satellite
 * par courant porteur libre, autrement dit par les lignes �lectriques

D�tails des solutions
---------------------

Utilisation du r�seau GPRS
~~~~~~~~~~~~~~~~~~~~~~~~~~

Cette solution n�cessite l'utilisation du r�seau des t�l�communications GSM. Le r�seau GPRS est en r�alit� une extension s'appuyant sur le r�seau GSM et a l'avantage d'une part de pouvoir rester connect� et d'autre part d'utiliser en plus des canaux de type voix, une passerelle vers le r�seau internet. La facturation ne se fait non plus � la dur�e mais au d�bit.

*Architecture du r�seau GSM/GPRS*
.. image:: images/reseau_gsm.svg

Les pr�requis sont :
 * �tre � port�e d'une antenne de t�l�communication (BTS)
 * n�cessite un abonnement aupr�s d'un FAI/op�rateur t�l�phonique?, donc un abonnement par site distant ? 

La couverture du r�seau GPRS (et donc GSM) sur le territoire europ�en est quasi totale. Il faudra s'assurer pr�alablement de choisir l'op�rateur mobile offrant la meilleure couverture, ce qui sera donc variable suivant les pays. Dans la m�me id�e il faudra veiller � traiter avec un op�rateur pr�sent dans la majorit� des pays europ�ens afin de n�gocier des prix int�ressants avec un support de qualit�.

Un exemple de couverture, en Norv�ge (op�rateur : Telenor), qui comprend un certains nombres de sites isol�s, notamment dans le nord :
.. image:: images/telenor.png

L'utilisation du r�seau UMTS ou 3G (qui utilise une partie du r�seau GSM), bien qu'apportant une capacit� de d�bit bien plus �lev�, est �cart� car son territoire de couverture reste tr�s faible dans les zones recul�es (ce type de r�seau n'utilise pas les antennes BTS du r�seau GSM). Ensuite, pour ce syst�me, le d�bit offert par le r�seau GPRS sera suffisant.

Concernant son impl�mentation, il n�cessite la mise en place d'un modem compatible GSM/GPRS. Deux solutions se d�tachent :
 * l'achat de composants et leur adaptation avec le syst�me embarqu� du site distant 
 * l'achat d'une solution compl�te

De nombreux fabriquants proposent des solutions de modems GSM/GPRS embarqu�s particuli�rement adapat�s aux contraintes. Les prix varient d'une centaine d'euros l'unit� � 400� pour les mod�les hauts de gamme, avec des caract�ristiques techniques qui satisfont les contraintes (donn�es prix sur les mod�les hauts de gammme) :
 * Temp�rature de fonctionnemment : -20�C � +85�C
 * Tol�rance � l'humidit� : 90%
 * Faible taille : 10cm*5cm*10cm
 * Consommation en communication : (< 200mA sous 14 Vdc)
 * Consommation au repos : (< 10mA sous 14 Vdc)


Sources :
 * couverture GSM : http://www.mobileworldlive.com/maps/
 * comparatifs modems chez erco&gener : http://www.ercogener.com/comparatif-modem-gsm-gprs-gps.html
 * prix (erco&gener) : http://www.kamosis.com/store/index-n-Modems_GSM_GPRS_EDGE_3G-cp-555.html
 * wikipedia


Utilisation du r�seau GPS
~~~~~~~~~~~~~~~~~~~~~~~~~

Les stations � distance pourraient communniquer avec la station centrale via satellite. Cette technique n�cessite l'installation d'une antenne emetrice/receptrice satellite et d'un modem d�di�.

Les pr�requis sont :
 * �tre dans un milieu d�gag�
 * souscrire un abonnement � un op�rateur (tarification �tablit suivant le d�bit allou� et le volume de donn�es �chang�)

Avantages :
 * couverture totale
 * d�bit suffisant

Inconv�nients :
 * cout du mat�riel : environ 350�
 * abonnement plus �lev� (de 25� pour 2Go � 100� pour 12Go)

Les latences sont cons�quentes (autour des 650ms contre 40ms pour l'ADSL) mais n�gligeables pour ce syst�me.

Deux flottes de satellites couvrant l'Europe :
 * Astra, op�rateurs : Viv�ole, Nordnet
 * Eutelsat, op�rateurs : Connexion Verte, Sat2way, Num�o

Le mat�riel fournit par ces op�rateurs se r�velerait surement insuffisant par rapport aux contraintes du syst�me et dans un souci d'int�rop�rabilit� avec la solution mis en place du c�t� des sites distants.
Des constructeurs sp�cialis�s dans l'embarqu� proposent des modems r�pondant � ces contraintes, modems similaires � ceux pr�sent�s pour la solution GPRS. Cependant leurs prix varient de 1500� � 3500� l'unit�.

source : 
 * offres chez Sat2way : http://www.sat2way.fr/fr/offre_haut_debit/
 * wikipedia : http://fr.wikipedia.org/wiki/Internet_par_satellite
 * prix des modems GPS : http://www.kamosis.com/store/index-n-Modems_Satellite-cp-558.html

Utilisation du courant porteur libre (CPL)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Cette solution permettrait de faire circuler l'information par les lignes �lectriques.

Les pr�requis sont :
 * �tre reli� aux lignes �lectriques
 * un modem sp�cifique

Inconv�nients :
 * libre d'utilisation chez les particuliers mais fortement r�glement� voir interdit sur le r�seau public dans certains pays europ�en
 * pas de normes d�finitives


Comparaison et bilan
--------------------

Le courant porteur libre, bien que prometteur, pour des raisons principalement politiques ne peut pas �tre envisag�s � une �chelle europ�enne.

Reste la solution GPRS et GPS. La derni�re est la plus couteuse mais ne peut pas �tre �cart�e car elle se r�v�le n�cessaire dans certains endroits extremement isol�s non couverts par le r�seau GSM/GPRS.

On pourrait imagnier � ce moment l� pr�voir une solution par d�faut GSM/GPRS et mettre en place, au cas par cas, des sites distants capable de communiquer via satellite.






