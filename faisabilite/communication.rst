Synthèse séance 7/01 
====================

Objectifs du document 
---------------------

Étude (draft) de faisabilité des moyens de communication longue distance entre les sites distants et le site central.

Fait
----

 * recherche sur les moyens de communication courte distance (réseaux de capteur type Zigbee) => redondance avec les recherches de Paul et Pierrick
 * recherche sur les moyens de communication longue distance
   * GPS
   * Courant porteur libre
   * réseau GSM/GPRS/UMTS
 * avantages/inconvénients
   * disponibilité
   * fiabilité
   * couts
   * adaptation à nos besoins

Reste à faire 
-------------

 * finir la rédaction 
 * comparatifs des solutions en termes de :
  * couts
  * utilisation (dépend de la zone géographique)
  * difficulté d'implémentation (technique ou politique)
 * quel système embarqué sera chargé de gérer la communication au site distant ?
  * un modem + puce GPRS ?
  * voir avec Paul et Pierrick

Modifications (08/01) 
---------------------

 * suite des recherches
 * découpage avec un plan
 * rédaction
 * *reste a faire : finir le détail des solutions + le bilan*



Communication longue distance
=============================

Problématique
-------------

Cette étude a pour objectifs d'effectuer un état de l'art en termes de communication longue distance. En l'occurrence, ici, il s'agit de trouver des solutions potentielles permettant de répondre à la question suivante : *comment s'effectuera la communication entre les sites distants et le site central de monitoring ?*

Pour répondre à cette question, il convient dans un premier temps de rappeler les contraintes inhérentes :
 * le site central pourra être déployé (voir migré à tout moment) partout en Europe, et a fortiori n'importe où dans le monde.
 * les sites distants sont situés n'importe où en Europe, y compris les endroits les plus reculés et les moins bien desservis, que ce soit en terme de d'énergie, de télécommunications ou d'infrastructures routières.
 * la communication devra être fiable
   * les informations ne doivent pas être perdues
   * certaines stations critiques doivent inclure des capacité de reprise ou de capacité de redondance pour garder une disponibilité maximale
 * la communication doit être la moins coûteuse possible

Dans un deuxième temps, les critères de sélection d'une solution se porteront également sur la teneur des communications : *quelles données seront amenées à circuler dans un sens, comme dans l'autre ?*

Du site central vers les sites distants :
 * mises à jour des logiciels (fréquence : maximum toutes les semaines, mais certainement beaucoup plus espacé)

Des sites distants vers le site central :
 * les informations provenant des capteurs (fréquence : de l'ordre de la minute)

Enfin, la taille du réseau est à prendre en compte, nous partirons d'une base de simulation 10 fois plus importante que l'existant scandinave, soit :
 * 100 sites distants * 10 = 1000 sites distants
 * 1000 sites distants * 10 cuves = 10000 cuves

Solutions possibles
-------------------

A l'heure actuelle trois méthodes de communication longue distante peuvent être envisagées pour ce système :
 * par le réseau GPRS, autrement dit par internet
 * par le réseau GPS, autrement dit par satellite
 * par courant porteur libre, autrement dit par les lignes électriques

Détails des solutions
---------------------

Utilisation du réseau GPRS
~~~~~~~~~~~~~~~~~~~~~~~~~~

Cette solution nécessite l'utilisation du réseau des télécommunications. Il a l'avantage d'une part de pouvoir rester connecté et d'autre part d'utiliser en plus des canaux de type voix, une passerelle vers le réseau internet.
La facturation ne se fait non pas à la durée mais au débit.

Les prérequis sont :
 * être à portée d'une antenne de télécommunication (*recherche le nom exact*)
 * nécessite un abonnement auprès d'un FAI, donc un abonnement par site distant ?

La couverture du réseau GPRS (et donc GSM) sur le territoire européen est quasi totale. Il faudra s'assurer préalablement de choisir l'opérateur mobile offrant la meilleure couverture, ce qui sera donc variable suivant les pays. Dans la même idée il faudra veiller à traiter avec un opérateur présent dans la majorité des pays européens afin de négocier des prix intéressants avec un support de qualité.

Un exemple de couverture, en Norvège (opérateur : Telenor), qui comprend un certains nombres de sites isolés, notamment dans le nord :
.. image:: images/telenor.png

Concernant son implémentation, il nécessite la mise en place d'un modem compatible GSM/GPRS. Deux solutions se détachent :
 * l'achat de composants et leur adaptation avec le système embarqué du site distant 
 * l'achat d'une solution complète

Exemple de solution complète (constructeur : erco&gener)

=============================               ==========================      =============================
Caractéristique                             GenLoc 53e AOB                        
=============================               ==========================      =============================

GSM/GPRS			            oui			            

GPS                                         oui

Température de fonctionnement               -20° +60°                       

Consommation
    - Voltage                               3.8V - 20V                     
    - Émission/Réception                    < 200mA (avec GPs)                            
    - Veille                                10µA                             

Bus CAN                                     en option

Lien vers la doc                            http://bit.ly/ejBbMS            

=============================               ==========================      =============================


=> les prix (max 300¤) : http://www.kamosis.com/store/index-n-Modems_GSM_GPRS_EDGE_3G-cp-555.html


Sources :
 * couverture GSM : http://www.mobileworldlive.com/maps/
 * comparatifs modems chez ercogener : http://www.ercogener.com/comparatif-modem-gsm-gprs-gps.html


Utilisation du réseau GPS
~~~~~~~~~~~~~~~~~~~~~~~~~

Les prérequis sont :
 * être dans un milieu dégagé
 * abonnement spécial ?

4 Mbits/s - 10 Mbits/s

source : 
 * solution internet par satellite en france : http://www.internet-par-satellite.com/asp-boutique/boutique/default.asp?centre=ABONNEMENTS.htm
 * satellite iridum : http://www.iridium.com/solutions/monitoring.aspx?applicationID=9
 * internet par satellite en europe : http://www.sat2way.fr/fr/defaut/index

Utilisation du courant porteur libre
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Les prérequis sont :
 * être relié aux lignes électriques
 *

=> problème politique ? (réseau domestique ok mais réseaux nationaux pas encore prêts ?)


Comparaison et bilan
--------------------

Le courant porteur libre, bien que prometteur, pour des raisons principalement politiques ne peut pas être envisagés à une échelle européenne.

Reste la solution GPRS et GPS, la dernière étant la plus couteuse mais ne pouvant pas être écartée car elle se révèle nécessaire dans certains endroits extremement isolés non couverts par le réseau GSM/GPRS.

On pourrait imagnier à ce moment là prévoir une solution par défaut GSM/GPRS et mettre en place, au cas par cas, des sites distants capable de communiquer via satellites.






