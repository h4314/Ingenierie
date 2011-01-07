=====================
Étude de faisabilité
=====================

Solution 1 : Solution tout intégré à base de chip Ember
=======================================================

Ember est une societé américaine crée en 2001, qui s'est spécialisé dans la
production et la commercialisation de solutions ZigBee. Membre de la Zigbee
Alliance, ses solutions sont reconnues pour leur efficacité et leur
interopérabilité.

Elle propose en ensemble de solutions intégrée à base de microcontrôleurs ARM,
comportant des mémoires flash et RAM, pouvant fonctionner sur secteur ou
batteries, avec une grande durée de vie. Le système est conçu pour être intégré
avec des périphérique externe, et propose par la même un grand nombre de
convertisseurs analogique-numériques, permettant de brancher une grande variété
de capteurs (Nom commercial EM250).

Les produits Ember sont conçus pour fonctionner dans des environnements variés.
Il est aussi possible de n'utiliser que le coprocesseur réseau Ember, et de le
coupler avec un processeur d'un autre fabricant, afin de bénéficier de plus de
flexibilité quant au choix des composants (Nom commercial EM260). 

Les solutions Ember sont capables de fonctionner en réseau de type maillé, et
proposent une porté en extérieur d'environ 100m. La consommation est très basse
(40mA en émission/réception, pour 1 à 1.5µA en mode veille), ce qui assure un
fonctionnement sur batterie de longue durée.

Ember a conçu un environnement de développement intégré, adapté à ses produits
(aussi bien ceux de type System on Chip tout intégré que les solutions plus
modulaires), qui sont conçus pour le développement et le débogage
d'applications réseau maillée, et propose donc des outils spécifiquement
adaptés.

Il est possible d'acquérir des kits de tests, peu onéreux, qui sont
spécifiquement conçus pour que des ingénieurs testent des solutions dans leur
environnement spécifique, pour s'assurer de l'adéquation du matériel avec la
résolution de leur problème.

=============================               ==========================      =============================
Caractéristique                             Ember EM250                     Atmel ATmega128RFA1
=============================               ==========================      =============================
Température de fonctionnement                -40° - 85°                     Non spécifié

Porté                                       100m                            100m

Consommation
    - Voltage                               2.1V - 3.6V                     1.8V - 3.6V
    - Émission/Réception                    40mA                            16.6mA - 18.6mA
    - Veille                                1µA                             250nA

CPU                                         
   - Type                                   ARM Cortex-M3 16bits            AVR 8Bits
   - Vitesse d'horloge                      24Mhz                           35Mhz

Quantité RAM                                12KB                            16KB                

Quantité mémoire persistante                128 ou 192KB de flash           128KB Flash, 4KB EEPROM

Débit                                       250kbps                         250kbps

Nombre de CAN                               Jusqu'à 17                      38 I/O programmable 

Sensibilité à l'humidité                    MSL3                            Non spécifié

Développement                               IDE spécifique                  GNU Toolchain (libre) + Plugin Eclipse

Type de réseau                              ZigBee - Maillé                 ZigBee Maillé

Dimensions                                  7mm x 7mm                       Non spécifié

Autre hardware                              Coprocesseur de chiffrage       Coprocesseur de chiffrage

Lien vers la doc                            http://bit.ly/iaLOmN            http://bit.ly/8E6dYt

=============================               ==========================      =============================

TODO : Faire un benchmark des systèmes : L4, Contiki, TinyOS (très spécialisé).
