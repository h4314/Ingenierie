Synth�se s�ance 7/01 
====================

Objectifs du document 
---------------------

�tude (draft) de faisabilit� des moyens de communication longue distance entre les sites distants et le site central.

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

Cette �tude a pour objectifs d'effectuer un �tat de l'art en termes de communication longue distance. En l'occurrence, ici, il s'agit de trouver des solutions potentielles permettant de r�pondre � la question suivante : *comment s'effectuera la communication entre les sites distants et le site central de monitoring ?*

Pour r�pondre � cette question, il convient dans un premier temps de rappeler les contraintes inh�rentes :
 * le site central pourra �tre d�ploy� (voir migr� � tout moment) partout en Europe, et a fortiori n'importe o� dans le monde.
 * les sites distants sont situ�s n'importe o� en Europe, y compris les endroits les plus recul�s et les moins bien desservis, que ce soit en terme de d'�nergie, de t�l�communications ou d'infrastructures routi�res.
 * la communication devra �tre fiable
   * les informations ne doivent pas �tre perdues
   * certaines stations critiques doivent inclure des capacit� de reprise ou de capacit� de redondance pour garder une disponibilit� maximale
 * la communication doit �tre la moins co�teuse possible

Dans un deuxi�me temps, les crit�res de s�lection d'une solution se porteront �galement sur la teneur des communications : *quelles donn�es seront amen�es � circuler dans un sens, comme dans l'autre ?*

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
 * par le r�seau GPRS, autrement dit par internet
 * par le r�seau GPS, autrement dit par satellite
 * par courant porteur libre, autrement dit par les lignes �lectriques

D�tails des solutions
---------------------

Utilisation du r�seau GPRS
~~~~~~~~~~~~~~~~~~~~~~~~~~

Cette solution n�cessite l'utilisation du r�seau des t�l�communications. Il a l'avantage d'une part de pouvoir rester connect� et d'autre part d'utiliser en plus des canaux de type voix, une passerelle vers le r�seau internet.
La facturation ne se fait non pas � la dur�e mais au d�bit.

Les pr�requis sont :
 * �tre � port�e d'une antenne de t�l�communication (*recherche le nom exact*)
 * n�cessite un abonnement aupr�s d'un FAI, donc un abonnement par site distant ?

La couverture du r�seau GPRS (et donc GSM) sur le territoire europ�en est quasi totale. Il faudra s'assurer pr�alablement de choisir l'op�rateur mobile offrant la meilleure couverture, ce qui sera donc variable suivant les pays. Dans la m�me id�e il faudra veiller � traiter avec un op�rateur pr�sent dans la majorit� des pays europ�ens afin de n�gocier des prix int�ressants avec un support de qualit�.

Un exemple de couverture, en Norv�ge (op�rateur : Telenor), qui comprend un certains nombres de sites isol�s, notamment dans le nord :
.. image:: images/telenor.png

Concernant son impl�mentation, il n�cessite la mise en place d'un modem compatible GSM/GPRS. Deux solutions se d�tachent :
 * l'achat de composants et leur adaptation avec le syst�me embarqu� du site distant 
 * l'achat d'une solution compl�te

Exemple de solution compl�te (constructeur : erco&gener)

=============================               ==========================      =============================
Caract�ristique                             GenLoc 53e AOB                        
=============================               ==========================      =============================

GSM/GPRS			            oui			            

GPS                                         oui

Temp�rature de fonctionnement               -20� +60�                       

Consommation
    - Voltage                               3.8V - 20V                     
    - �mission/R�ception                    < 200mA (avec GPs)                            
    - Veille                                10�A                             

Bus CAN                                     en option

Lien vers la doc                            http://bit.ly/ejBbMS            

=============================               ==========================      =============================


=> les prix (max 300�) : http://www.kamosis.com/store/index-n-Modems_GSM_GPRS_EDGE_3G-cp-555.html


Sources :
 * couverture GSM : http://www.mobileworldlive.com/maps/
 * comparatifs modems chez ercogener : http://www.ercogener.com/comparatif-modem-gsm-gprs-gps.html


Utilisation du r�seau GPS
~~~~~~~~~~~~~~~~~~~~~~~~~

Les pr�requis sont :
 * �tre dans un milieu d�gag�
 * abonnement sp�cial ?

4 Mbits/s - 10 Mbits/s

source : 
 * solution internet par satellite en france : http://www.internet-par-satellite.com/asp-boutique/boutique/default.asp?centre=ABONNEMENTS.htm
 * satellite iridum : http://www.iridium.com/solutions/monitoring.aspx?applicationID=9
 * internet par satellite en europe : http://www.sat2way.fr/fr/defaut/index

Utilisation du courant porteur libre
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Les pr�requis sont :
 * �tre reli� aux lignes �lectriques
 *

=> probl�me politique ? (r�seau domestique ok mais r�seaux nationaux pas encore pr�ts ?)


Comparaison et bilan
--------------------

Le courant porteur libre, bien que prometteur, pour des raisons principalement politiques ne peut pas �tre envisag�s � une �chelle europ�enne.

Reste la solution GPRS et GPS, la derni�re �tant la plus couteuse mais ne pouvant pas �tre �cart�e car elle se r�v�le n�cessaire dans certains endroits extremement isol�s non couverts par le r�seau GSM/GPRS.

On pourrait imagnier � ce moment l� pr�voir une solution par d�faut GSM/GPRS et mettre en place, au cas par cas, des sites distants capable de communiquer via satellites.





