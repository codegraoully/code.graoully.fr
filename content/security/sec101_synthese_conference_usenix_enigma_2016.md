---
title: "Sec101_synthese_conference_usenix_enigma_2016"
date: 2020-10-28T11:28:44+01:00
draft: false
tags:
 - sécurité
 - conférence
 - cyber
---

## Organisation d’une attaque

On dénombre six phases lors d’une attaque.

### Reconnaissance

* Par source ouverte ;
* Par ingénierie sociale ;
* En attente d’une opportunité, d’une erreur de stratégie de la défense.

### Attaque initiale

* Exploiter une faille technique : CVE, zero-day, Injection SQL ;
* Exploiter une faille humaine : Phishing, usurpation d’identité par téléphone par exemple, website infecté, clef USB infecté…

### Persistance de l’attaque

Pouvoir accéder au réseau après l’intrusion, quand l’attaquant le souhaite ou selon son besoin.

### Installation d’outils

Installation de portes dérobées ou d’un troyen par exemple.

### Translater l’attaque sur le réseau

Se déplacer sur le réseau c’est déplacé l’attaque sur celui-ci, contaminé d’autres machines, pour masquer le maillon faible, pour masquer le point d’entré sur le réseau. Cela permet de rester discret et en cas de découverte de garder un accès.

### Collecter, s ‘exfiltrer et exploiter les résultats

Une attaque discrète est une attaque réussie, dans le cas d’extraction, soit de vol de données par exemple, permettant d’exploiter le résultat sans lever le doute de la cible.

## Différente type d’attaques et de menaces

Il faut prendre en compte différents menaces et types d’attaques :

* Gouvernementales : vol de données, ou encore intrusion persistante sur des systèmes expert (centrales nucléaires iraniennes)
* Cyber délinquance : attaques plutôt axées sur la destruction ou le chiffrement de donnée contre rançon.

## Les solutions

1. Connaitre son réseau en profondeur pour mieux le protéger ;
2. Réduire la surface d’attaque en limitant les logiciels installés ;
3. Connaitre et approuver les logiciels que l’on installe ;
4. Effectuer des tests d’intrusions ;
5. Corriger TOUTES les failles découvertes, sans sous-estimer celles qui ne semblent pas importantes ;
6. Choisir les équipements de confiance : téléphone mobiles, tablette, équipement d’infrastructure ;
7. Employer les bonnes pratiques de sécurité :
    1. Double facteur d’authentification ;
    2. Établir une politique de sécurité ;
    3. Limiter les droits des utilisateurs à leurs stricts nécessaires ;
    4. Segmenter le réseau ;
    5. Utilisation de liste autorisé / interdite (whiteliste / blackliste) ;
    6. Journaliser, monitorer puis consulter les journaux ;
8. Utilisation de systèmes de réputation de services / logiciels ;
9. Plan de sauvegarde des données en cas de tentative de destruction ;

Ces solutions sont applicables en fonctions de ce que l’on veut protéger et contre qui on veut le faire. En effet il y a peu de chance de constater une attaque persistante chez un particulier qui n’est pas dans une entreprise cible / importante / gouvernementale par exemple.
