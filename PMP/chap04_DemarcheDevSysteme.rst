Démarche de développement
-------------------------

Cycle de vie
============

Ce projet sera développé en plusieurs lots et plusieurs phases.


Découpage du projet
===================

Ce qui suit est une série de listes hierarchisées décrivant le projet selon
plusieurs points de vue.

Approche organisationnelle/fonctionnelle :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

  * Électronique/Système embarqué

    * Étude des capteurs

    * Étude de l'architecture du système embarqué (analyse des solutions
      retenues pendant l'étude préalable)

    * Étude du protocole et du type de communication entre le capteur et le
      système

    * Réalisation de tests de performance, autonomie, résistance

    * Étude des limites techniques de la solution

  * Logiciel

    * Micro-logiciel embarqué

    * Logiciel du système *maître* sur site

    * Progiciel *mainframe* du site central

    * Logiciels d'exploitation utilisateurs

      * Interfaces pour appareils mobiles et terminaux légers (techniciens
        intervenant sur site)

        * Interfaces Homme-Machine

        * Logique métier

      * Logiciels de traitement des données collectées (Aide à la décision,
        statistiques)

        * Interfaces Homme-Machine

        * Implémentation de la logique métier

  * Télécom et réseau

    * Étude de la fiabilité des échanges entre le capteur et le système

    * Étude critique des outils de communication GPRS (performances, capacités,
      limites)

    * Étude de la sécurisation des transmission des données sur le(s) réseaux

    * Étude des infrastructures de télécommunication mises en place en Europe
      et utilisable pour déployer les systèmes.

  * Sciences de l'information

    * Collecte des besoins des clients, analyse de l'existant, analyse des
      fonctions supports

    * Gestion des données, stockage

      * Analyse des solutions existantes

      * Mise à l'échelle (capacité à traiter un grand volume d'informations)

    * Aide à la décision


      * Étude d'algorithmes et euristiques

      * Mise à l'échelle

    * Statistiques

      * Étude des indicateurs courants

      * Élaboration de métriques

      * Mise à l'échelle

    * Monitoring

      * Analyse des outils de fouille de données

      * Classification des données

      * Mise à l'échelle

Approche produit :

  * Système Embarqué de mesure

    * Prise de mesure

    * Normalisation de la mesure

    * Évaluation du niveau d'autonomie

    * Journalisation des anomalies

    * Communication avec le maître du site

      * Transmission de la mesure normalisée

      * Transmission des journaux d'anomalies

      * Transmission du niveau d'autonomie

  * Maître du site (Logiciel)

    * Identification et authentification des systèmes de mesure

    * Collecte des données des systèmes de mesure

    * Tri et compression des données

    * Encryptage et sécurisation des données

    * Communication des données au site central

    * Réception des paramètres de configuration depuis le site central

    * Configuration du système (paramètres de sécurité, adresses de confiance,
      certificats)

    * Configuration des systèmes de mesure (fréquences, etc)

  * Gestion des données centralisées

    * Collection des données

      * Réception

      * Stockage

    * Traitement et calcul

      * Traitements planifiés

      * Traitements sur demande

    * Analyse des données traitées

    * Contrôles de validité

    * Mise à jour des plannings d'intervention

    * Envoi de notifications au personnel

  * Logiciels utilisateurs (basés sur des briques d'un progiciel/framework
    commun)

    * Brique : Identification et authentification des utilisateurs

    * Logiciels pour terminaux mobiles

      * Consultation de planning d'intervention

      * Consultation de la feuille de route

      * Consultation de l'état des infrastructures

      * Consultation de l'annuaire de contacts partagé

      * Édition d'un relevé manuel de données

      * Édition d'une demande d'intervention (remontée manuelle d'une anomalie)

    * Logiciels de supervisation

      * Surveillance du site central

      * Surveillance des sites distants

      * Configuration du site central

      * Configuration des sites distants

      * Analyse des plannings d'intervention

      * Monitoring des serveurs

      * Gestion des permissions

      * Gestion des certificats de sécurité

      * Déploiement de mises à jour

    * Logiciels de monitoring

      * Réception des statistiques 

      * Présentation en tableaux de données

      * Présentation en schémas

      * Éditions de synthèses

      * Requêtes utilisateurs

        * Fouille des données

        * Aide à la décision

Planning prévisionnel
=====================

TODO ?
