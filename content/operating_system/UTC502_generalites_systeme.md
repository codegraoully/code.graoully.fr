---
title: "Système"
date: 2019-12-01T09:00:00+00:00
draft: false
images:
tags:
  - OS
  - Système
  - Linux
  - GNU/Linux
---

## Définition
* gère ressources matérielles avec les pilotes de périphérique;
* Gestion du système de fichiers;
* Interface entre les applications et le materiel;
* Gestion des processus:
 - Shell (Text User Interface) -> fils -> "ls -l"

## Modes

1. Utilisateur: quelques commandes seulement
2. Noyau: toutes les commandes sont exécutables par l'OS

## Shéma

1. Application
2. système d'exploitation
3. Pilotes de périphérique
4. Materiel


## Pyramides des mémoires

1. Registre
2. Cache
3. RAM
4. EPROM BIOS
5. HDD
6. Bandes magnétiques

## Bases

* Pipeline / registre
* A chaque changement d'application l'état du registre est sauvegarder
* le registre Process State Word contient cette information ainsi que le mode d'éxécution de l'OS
* SPOOL: Simultaneous peripheral operation OnLine: file d'attente des périphérique


## Utilisateurs

* accès au systèmes selon des droit
* super utilisateur pour des droits spéciaux
* UID
* GID 

## Fichiers

* descripteur de fichier: entier permettant de manipuler / opérer dur un fichier
* Fichiers spéciaux : périphérique comme un fichierQ
 * mode bloc : disque
 * mode caractere: imprimante / modem : flux de caractere
 * dans /dev/

## Appel système

* lecture écriture sur fichier
* ajout / suppression de fichier

## Processus

* C'est une instance d'un programme;
* l'OS alloue de la ressource virtuelle: du CPU et de la mémoire virtuelle pour être indépendant du materiel;
* Concept permettant le pseudo paralellisme: P1 -> P2 -> P3 -> P1
* Herite de l'UID;
* Les processus enfants communiquent via une table: c'est la communication interprocessus;
* peuvent partagé leur mémoire virtuelle;

### Thread

* Les threads sont des processus léger, des flux d'application;
* Font partis d'un processus;
* Partage les ressources du processus;


### informations d'un processus

* mémoire virtuelle
* contexte d'execution (addresse de la prochaine instruction etc...)
* état: idle, execution, bloqué 
* liste de ressources (fichiers, périphériques...)
* utilisateur (droits)

### mémoire virtuelle

|Mémoire virtuelle||
|---|---|
|Code||
|Variables||
|Pile - Stack|stock les paramètres d'entré d'une fonction|
||résultat|
||adresse de retour de la fonction précédente|
||variables locales|
|Tas - Heap|allocation dynamique de mémoire|
|||
|||


 * permet d'allouer plus de mémoire que la mémoire physique
 * adressage virtuel
 * implémentation: pagination:unité de taille fixe

 |page virtuelle|cadre mémoire physique|droit d'accès|
 |---|---|---|
 |||



### Système de fichiers

#### Materiel

Un disque se décompose comme suit:

1. des plateaux
2. Les cylindres -> ensembles des pistes / secteurs sur l'ensemble des plateaux ( verticale )
3. Les pistes -> cercle concentrique sur un plateau
4. Les secteurs -> sécteurs angulaires


Pour un disque dur:
1. secteur de boot
2. table des partitions
3. partitions

Sur une partition:

1. meta données:
 * table des inodes
 * liste des blocks disponibles
2. données:
* divisé en bloc de 512 octets généralement

un inode contient:

* taille du fichier
* permissions
* date de modif et accès
* pointeurs des contenus du fichier
* PAS le nom du fichier

Un répertoire est un fichier particulier

* Son inode reserve les inodes des fichiers
