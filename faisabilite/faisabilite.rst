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

Solution 2 : Solution tout intégrée à base de chip Atmel
========================================================

Atmel est une entreprise américaine, basée en Californie, qui conçoit et
fabrique des semi-conducteurs depuis 1984.

Cette entreprise des solutions pour plusieurs corps de métier (Domotique,
applications industrielles, solutions d'éclairage automatisée, solutions pour
capteurs, etc.).

Elle propose, tout comme Ember, un ensemble de solutions intégrées, ou à intégrer,
afin d'avoir une plus grande flexibilité, les composants étant standards. La
plupart des solutions proposent des fonctionnalités de communication sans-fil
(ZigBee) et des convertisseurs, afin de brancher des capteurs. Un mode de veille
profonde est supporté, afin de baisser la consommation jusqu'à 250 nA
(le minimum de composants sont alimentés, et un timer tourne pour savoir quand
repasser dans autre mode). Cela permet une durée de vie extrêmement longue.

L'environnement de développement se base sur Eclipse, et est donc portable sur
Windows, Linux et MacOS, tout en assurant une bonne intégration avec les
solutions matérielles.

Comme pour la solution Ember, il est possible d'acheter, pour environ $400, un
kit comprenant 5 ATmega1281V (microcontrôleurs) et 5 AT86RF230 (transmetteurs
sans fils), ainsi que les logiciels pour mettre en œuvre une solution de
démonstration de type réseau maillé.


Solution 3 : Solution tout intégrée module XBee-Pro Digimesh
============================================================

Digi International est une société américaine fondée en 1985 et basée dans le Minnesota.
Elle développe des solutions permettant la mise en réseau d'équipements divers en utilisant
les réseaux cellulaires ainsi que présentant une compatibilité ZigBee et Wifi.

Digi présente ses équipements comme étudiés pour être utilisés en environnement
dangereux, tels que les usines chimiques ou les entrepots de matières inflammables.

Digi propose un kit de développement pour 270 dollars et des modules XBee pour 20
dollars pièce.

Le module XBee 900 n'est pas autonome, il nécessite d'être connecté à un ordinateur.
Le nombre de capteurs possible n'est donc pas limité par cette technologie.




=============================               ==========================      =============================                =====================================================================
Caractéristiques                            Ember EM250                     Atmel ATmega128RFA1                          XBee-Pro Digimesh
=============================               ==========================      =============================                =====================================================================
Température de fonctionnement                -40°C - 85°C                   Non spécifié                                 -40°C - 85°C

Portée                                      100m                            100m                                         140m sans antenne, augmentable à 3km ou 10km selon l'antenne utilisée

Consommation
    - Voltage                               2.1V - 3.6V                     1.8V - 3.6V                                  3.0V - 3.6V
    - Émission/Réception                    40mA                            16.6mA - 18.6mA                              210mA / 80mA
    - Veille                                1µA                             250nA                                        48µA

CPU                                         
   - Type                                   ARM Cortex-M3 16bits            AVR 8Bits                                    non spécifié
   - Vitesse d'horloge                      24Mhz                           35Mhz

Quantité RAM                                12KB                            16KB                                         non spécifié

Quantité mémoire persistante                128 ou 192KB de flash           128KB Flash, 4KB EEPROM                      non spécifié

Débit                                       250kbps                         250kbps                                      156kbps

Nombre de CAN                               Jusqu'à 17                      38 I/O programmable                          indépendant

Sensibilité à l'humidité                    MSL3                            Non spécifié                                 non spécifié

Développement                               IDE spécifique                  GNU Toolchain (libre) + Plugin Eclipse       IDE spécifique, basé sur windows

Type de réseau                              ZigBee - Maillé                 ZigBee Maillé                                ZigBee maillé - wifi - réseaux cellulaires

Dimensions                                  7mm x 7mm                       Non spécifié                                 2.4cm x 3.3cm

Autre hardware                              Coprocesseur de chiffrage       Coprocesseur de chiffrage

Lien vers la doc                            http://bit.ly/iaLOmN            http://bit.ly/8E6dYt                         http://ftp1.digi.com

=============================               ==========================      =============================                =====================================================================

Solution 4 : Intégration manuelle de composants
===============================================

En dehors des solutions toute intégrées, il est envisageable d'intégrer des
composants de différents constructeurs, par exemple, un microcontrôleur, un
périphérique réseau, des capteurs, un système temps réel, pour former une
solution calquée sur les besoins.

Systèmes d'exploitation
-----------------------

=====================       =========================   =======================   =======================   ======================= 
Caractéristique             TinyOS                      L4 Fiasco                 Contiki                   VxWorks
=====================       =========================   =======================   =======================   ======================= 
Matériel                                                                                                    
    - Architecture          ATMega8, AVRMote, Mica,     x86 (32 et 65bits)        Atmel AVR, TI MSP430,     Tous µc et CPU modernes
                            Mica2, Micadot, Mica128,    ARM (v4 - v7)             Nintendo Gameboy et NES   
                            Micaz, MSP430, Rene2,       nVidia Tegra2             x86, Apple II             
                            Telos, Telos2, PC           PowerPC                                             
    - Réseau                TI CC1000 et CC2420,        Varié, possibilité de     Varié, possibilité de     Grand nombre de chip
                            Infineon TDA5250,           coder des pilotes.        coder des pilotes.        
                            Atmel RF212 et RF230,                                                           
                            Semtech XE1205                                                                  
                                                                                                            
Usage                       Réseau de capteurs          Variés                    Variés, dont réseaux      Variés
                                                                                  de capteurs.              
                                                                                                            
Licence                     New BSD                     GPL ou commerciale         BSD                      Commerciale
                                                                                                            
Langage                                                                                                     
    - Système               NesC                        C++ / x86 ASM             C                         C
    - Applications          NesC                        C, C++                    C                         Ada, C, C++, Java
                                                                                                            
Modèle                      Évènementiel                Micro-noyau               Évènementiel              Monolithique
                                                                                                            
Ordonnancement              Non-préemptif                                         Préemptif                 Préemptif
                                                                                                            
Consommation                Très faible                 Variable                  Très faible               Variable
                                                                                                            
Temps réel                  Non                         Oui                       Oui                       Oui
                                                                                                            
=====================       =========================   =======================   =======================   =======================

