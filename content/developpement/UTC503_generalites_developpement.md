---
title: "Paradigme de programmation"
date: 2019-11-01T09:00:00+00:00
draft: false
images:
tags:
  - dev
  - paradigme
  - programmation
  - developpement
---

- [Paradigme (modèle) de programmation](#paradigme-mod%c3%a8le-de-programmation)
  - [La programmation impérative](#la-programmation-imp%c3%a9rative)
      - [la séquence d'instructions](#la-s%c3%a9quence-dinstructions)
      - [L'assignation ou affectation](#lassignation-ou-affectation)
      - [L'instruction conditionnelle](#linstruction-conditionnelle)
      - [La boucle](#la-boucle)
      - [Les branchements](#les-branchements)
  - [Programmation orientée objet](#programmation-orient%c3%a9e-objet)
      - [Encapsulation](#encapsulation)
      - [Héritage (généralisation)](#h%c3%a9ritage-g%c3%a9n%c3%a9ralisation)
      - [Polymorphisme, redéfinition, Upcasting et surcharge](#polymorphisme-red%c3%a9finition-upcasting-et-surcharge)
      - [Classe abstraite](#classe-abstraite)
      - [Les génériques](#les-g%c3%a9n%c3%a9riques)
      - [Patron de conception «design pattern»](#patron-de-conception-%c2%abdesign-pattern%c2%bb)
  - [Programmation déclarative](#programmation-d%c3%a9clarative)
  - [Programmation descriptive](#programmation-descriptive)
  - [Programmation fonctionnelle](#programmation-fonctionnelle)
      - [Fonction pure](#fonction-pure)
      - [Transparence référentielle](#transparence-r%c3%a9f%c3%a9rentielle)
      - [Immutabilité](#immutabilit%c3%a9)
      - [Assignation de fonction en TypeScript](#assignation-de-fonction-en-typescript)
        - [Fonction Lambda](#fonction-lambda)
      - [Fonction d’ordre supérieur](#fonction-dordre-sup%c3%a9rieur)
      - [La «closure» ou fermeture](#la-%c2%abclosure%c2%bb-ou-fermeture)
      - [La curryfication](#la-curryfication)
      - [L’application partielle](#lapplication-partielle)
      - [La récursion](#la-r%c3%a9cursion)
      - [Recherche et transformation de listes](#recherche-et-transformation-de-listes)
  - [Programmation logique](#programmation-logique)
      - [Programmer en Prolog, c’est :](#programmer-en-prolog-cest)
      - [Applications:](#applications)
      - [Faits](#faits)
      - [Règles :](#r%c3%a8gles)
      - [Faits : 1ère base de connaissance](#faits--1%c3%a8re-base-de-connaissance)
      - [Interrogations](#interrogations)
      - [Des règles](#des-r%c3%a8gles)
      - [Termes](#termes)

Un langage est une notation conventionnelle destinée à formuler des algorithmes: Il s'agit d'un vocabulaire et de règles de grammaire.
Le paradigme est une représentation du monde par le biais d'un modèle cohérent. Il permet de répondre à des problèmes types.

Le code est transformé pour être:

* Interprétation / Interpréteur;
* Compilation / Compilateur;
* Bytecode.

## La programmation impérative

* Décrit les opérations en séquence d’instructions pour modifier l’état du programme;
* Introduit les concepts de procédures, structures de contrôle, et structures de données;
* Certainement le paradigme le plus ancien et le plus répandu dans les langages;
* Exemples de langages : Basic, Cobol, C, Javascript, Pascal, Perl, PHP, Python

#### la séquence d'instructions

La machine va exécuter les instructions les unes après les autres dans l’ordre de lecture.
Une instruction par ligne et/ou séparés par un ’;’.

#### L'assignation ou affectation

Une assignation : `identifiant <- expression` : Stocke dans la zone mémoire «pointée» par "identifiant" le résultat de l’exécution ou l'évaluation de "expression".

#### L'instruction conditionnelle

* Si condition est vraie alors exécute {instructions} : "condition" est une expression booléenne : vraie ou fausse, 0 ou 1.
* Si condition est vraie alors exécute {instructions A} sinon exécute {instructions B}.

#### La boucle

Répète N fois {instructions}.
La «boucle for» permet d’exécuter un nombre prédéfini d’itérations exécutant les instructions.
Elle se définit par quatre blocs : initialisation, condition de sortie de boucle, code évolution boucle, instructions à exécuter à chaque boucle.
```C
for (int compteur = 0; compteur < maximum; compteur = compteur + 1){
faitUnTruc();
}
```

#### Les branchements

Permettent à la séquence d’instructions d’être déroutée vers un autre endroit du programme de deux manières:

* goto
* appel de fonctions

---

## Programmation orientée objet

* Consiste à définir et assembler des briques logicielles appelées objets communiquant entre eux par messages (appel de méthode) pour consulter et modifier leur état;
* Paradigme le plus utilisé aujourd’hui;
* Design patterns: des solutions applicatives répondant à des problèmes connus;
* Exemples de langages : C++, C#, Java, PHP, Python, Smalltalk, TypeScript;
* Né dans les années 60-70 avec les langages Simula67, Smalltalk puis C++, Objective-C ensuite avec Java, PHP, Python, JavaScript, TypeScript;
* Un objet est une entité, du monde physique par exemple : personne, service qui a une structure interne et un comportement, il interagit avec les autres objets par des messages.
* La POO c’est : Modéliser ces objets et Définir ces propriétés (ou attributs), ses relations avec les autres objets composition, héritage, délégation, etc...) et définir son interface, i.e. l’ensemble des messages qu’on pourra lui appliquer.
La modélisation pourra se faire via UML par exemple.
* Définir les «types»de ces objets Ces types sont appelées «classes»;
* Une classe définit des attributs: données de la structure interne de l’objet, son état; ses méthodes : une méthode étant une fonction définissant le comportement à la réception d’un message;
* La classe peut être vue comme le moule permettant la création d’un objet ou plusieurs: les instances ayant les mêmes attributs, mais potentiellement pas le même état, i.e. pas les mêmes valeurs d’attributs.

#### Encapsulation

Un objet s’appuie sur le principe d’encapsulation : regrouper des données et les fonctions qui les manipulent; il doit être considéré comme une «boîte noire» dont l’état interne doit rester intègre, cohérent pour maintenir cette intégrité, l’objet ne doit être manipulé par les autres objets qu’au travers de son «interface», i.e. ses méthodes publiques.
Pour garantir l’intégrité, on peut «masquer» certains attributs et méthodes en modifiant leur niveau d’accessibilité : «private» ou «public» par défaut.
Méthodes spéciales:

* le *constructeur* : est appelé automatiquement lors de la création de l’objet pour initialiser ses attributs;
* le *destructeur* / Finaliseur qui est appelé à la fin de vie de l’objet pour libérer des ressources détenues par l’objet;
* les *Accesseurs*:
* *Getters* : permet de lire un attribut (virtuel ou pas) privé de l’objet;
* *Setters* : permet de modifier un attribut privé de l’objet selon des contraintes d’intégrité;

#### Héritage (généralisation)

Wikipedia: spécialisation qui permet d'hériter dans la déclaration d’une nouvelle classe (appelée classe dérivée, classe fille, classe enfant ou sous -classe) des caractéristiques (propriétés et méthodes) de la déclaration d'une autre classe (appelée classe de base, classe mère, classe parent ou super -classe)
En déclarant une nouvelle classe B par héritage de la classe A, ajoutant de nouveaux membres, on peut alors dire que:

* A est une généralisation de B et B est une spécialisation de A;
* A est une super - classe de B et B est une sous - classe de A;
* A est la classe mère de B et B est une classe fille de A.

Lorsqu'une classe fille hérite d'une classe mère, elle peut alors utiliser les caractéristiques de la classe mère. Pour invoquer une définition de la classe mère, utilisation de mot clé super.

#### Polymorphisme, redéfinition, Upcasting et surcharge

* Consiste à *redéfinir* une méthode pour affiner son comportement.
* L’*upcasting*, c’est voir un objet selon l’interface de la classe mère, mais en appelant les méthodes redéfinies: c'est faire passer une classe fille pour sa classe mère.
* *ad hoc* ou *surcharge*: écrire plusieurs méthodes de même nom renvoyant le même type de résultat, mais avec des arguments différents dans le cas de la conversion d'argument ou de gestion de valeur par défaut par exemple.

#### Classe abstraite

Écrire un code «par défaut» dans une méthode, c’est prendre le risque qu’elle ne soit pas redéfinie par la classe fille et donc d’avoir une valeur erronée.

* Ne peut pas être instanciée.
* Forcer les classe filles à implémenter / redéfinir une méthode.

#### Les génériques

`function defautSiNul <T> (x: T, defaut: T): T`

La fonction defautSiNul va fonctionner avec un type paramétré qu’on appellera T, dont on ne sait rien à la définition de la fonction. Ce type inconnu T sera celui des paramètres x et defaut ainsi que celui de retour. T sera défini, deviné, «inféré», pour chaque appel de la fonction grâce au type du 1er argument passé : si x est un number, alors defaut sera aussi un number et la valeur retournée par la fonction sera aussi number.

* Dans une fonction générique, tous les paramètres ne sont pas obligatoirement génériques;
* On aurait pu choisir une autre lettre que T: X, Y, Z, etc...
* Le type paramétré peut être intégré à la déclaration d’un tableau;
* On peut utiliser plusieurs types paramétrés;

`class NomClasse<T>`

* Le type générique paramétré peut être utilisé pour définir le type des :
* attributs;
* paramètres de méthodes;
* résultat de méthodes;
* On peut indiquer de quel classe (abstraite) ou interface hérite T;

`<T extends MaClasse>`

La généricité est une forme de polymorphisme, le polymorphisme de type, dit aussi paramétrage de type : en effet, le type de donnée général (abstrait) apparaît comme un paramètre des algorithmes définis, avec la particularité que ce paramètre-là est un type.
Elle consiste à définir des algorithmes identiques opérant sur des données de types différents.
Un algorithme de tri d’objet est par exemple toujours le même; peu importe le type de données l’algorithme doit uniquement disposer d'un itérateur sur les éléments - générique et/ou d'une fonction de comparaison, générique aussi.
Les algorithmes génériques sont ainsi très présents dans le domaine des collections.

#### Patron de conception «design pattern»

décrit une organisation de classes fréquemment utilisée pour résoudre un problème récurrent. Le patron de conception parle d'instances, de rôles et de collaboration. Voir le livre «Design Patterns» écrit par le Gang of Four (GoF).
Un pattern c'est un nom, une description du problème à résoudre, une description de la solution, une illustration, un exemple.

Orthogonalité du patron:
«Chaque patron doit correspondre à une approche différente, qui ne répète pas les idées ou stratégies présentes dans d'autres patrons»
«Cette qualité permet au concepteur d'analyser un problème et d'en résoudre chaque aspect d'une façon organisée, ainsi que de combiner les patrons pour construire une solution»

Patrons de Conceptions issus du livre «Design Patterns: Elements of Reusable Software» paru en 1994 et co-écrit par le «Gang of Four» (GoF): Erich Gamma, Richard Helm, Ralph Johnson (en) et John Vlissides.
Les patrons du GoF c'est un catalogue de 23 patrons de 3 familles:

* *Créateurs*: comment faire l'instanciation et la configuration des classes et des objets;
* *Structuraux*: comment organiser les classes d'un programme dans une structure plus large (séparant l'interface de l'implémentation);
* *Comportementaux*: ils définissent comment organiser les objets pour que ceux-ci collaborent (distribution des responsabilités) et expliquent le fonctionnement des algorithmes impliqué;
* exemples: Itérateur, Observeur, Factory, Builder, Singleton

```Java
// Factory pattern
public class FabriqueAnimal {

Animal create(String typeAnimal) throws AnimalCreationException {
  if(typeAnimal.equals("chat")) {
    return new Chat();
  }
  else if(typeAnimal.equals("chien")) {
    return new Chien();
  }
  throw new AnimalCreationException("Impossible de créer un " + typeAnimal);
  }
}
```

```java
// Observer pattern
class Signal extends Observable {

  void setData(byte[] lbData){
    setChanged(); // Positionne son indicateur de changement
    notifyObservers(); // (1) notification
  }
}

    Le panneau d'affichage qui implémente l'interface java.util.Observer est créé. Avec une méthode d'initialisation (2), il lui est transmis le signal à observer (2). Lorsque le signal notifie une mise à jour, le panneau est redessiné (3).

class JPanelSignal extends JPanel implements Observer {

  void init(Signal lSigAObserver) {
    lSigAObserver.addObserver(this); // (2) ajout d'observateur
  }

  void update(Observable observable, Object objectConcerne) {
    repaint();  // (3) traitement de l'observation
  }
}
```

```Java
// From wikipedia
// La classe est finale, car un singleton n'est pas censé avoir d'héritier.
 public final class Singleton {

     // L'utilisation du mot clé volatile, en Java version 5 et supérieure,
     // permet d'éviter le cas où "Singleton.instance" est non nul,
     // mais pas encore "réellement" instancié.
     // De Java version 1.2 à 1.4, il est possible d'utiliser la classe ThreadLocal.
     private static volatile Singleton instance = null;
 
     // D'autres attributs, classiques et non "static".
     private String xxx;
     private int zzz;

     /**
      * Constructeur de l'objet.
      */
     private Singleton() {
         // La présence d'un constructeur privé supprime le constructeur public par défaut.
         // De plus, seul le singleton peut s'instancier lui-même.
         super();
     }
     
     /**
      * Méthode permettant de renvoyer une instance de la classe Singleton
      * @return Retourne l'instance du singleton.
      */
     public final static Singleton getInstance() {
         //Le "Double-Checked Singleton"/"Singleton doublement vérifié" permet 
         //d'éviter un appel coûteux à synchronized, 
         //une fois que l'instanciation est faite.
         if (Singleton.instance == null) {
            // Le mot-clé synchronized sur ce bloc empêche toute instanciation
            // multiple même par différents "threads".
            // Il est TRES important.
            synchronized(Singleton.class) {
              if (Singleton.instance == null) {
                Singleton.instance = new Singleton();
              }
            }
         }
         return Singleton.instance;
     }

     // D'autres méthodes classiques et non "static".
     public void faireXxx(...) {
       this.xxx = "bonjour";
     }

     public void faireZzz(...) {
     }
 }
```

---

## Programmation déclarative

* Paradigme de programmation de type déclaratif qui consiste à déclarer les données du problème, puis à demander au programme («moteur») de le résoudre; Années 1930, Alonzo Church travaille sur les concepts de fonction d'application : le Lambda calcul.
* Historique: 1954 Fortran (FORmula TRANslator), 1958 Lisp, 1975 Scheme, 1987 Caml, 1990 Haskell;
* Sous familles très différentes : descriptive, fonctionnelle, logique;
* Le calcul est l’évaluation de fonctions mathématique;
* Une méthode de développement par composition en fonction pure;
* Permet d’éviter les problèmes inhérents à:
* la mutation des données (mutable data);
* Les états partagés (shared state);
* Les effets de bords (side-effects);

---

## Programmation descriptive

* Décrit des mises en forme d’objets graphiques
* C’est le moteur de rendu du navigateur qui va interpréter et afficher le résultat
* Exemples : HTML, xml

---

## Programmation fonctionnelle

* Un programme est une fonction qui considère le calcul du programme en tant qu’évaluation de fonctions au sens mathématique du terme
* Difficile à aborder pour les programmeurs impératifs, car façon de penser très différente
* Adopté par les langages récents (fonction lambda entre autres) et adapté aux problématiques exprimables sous forme de flux asynchrones;
* Exemples de langages : Haskell, Lisp, Rust, Scala, TypeScript

#### Fonction pure

* C’est l’unité de traitement de ce paradigme;
* Il s’agit de fonction pure, i.e. fonction au sens mathématique;
* Ne dépend QUE des arguments;
* Ne dépend PAS d’un état externe;
* N’a donc pas d’effets de bords, dû à un changement d’état;
* Donnera toujours le même résultat pour un paramètre donné;

#### Transparence référentielle

* renvoie toujours le même résultat pour un ensemble de paramètres d’entrée;
* n’appelle pas d’autres fonctions susceptibles de modifier un état et donc de créer un effet de bord;
* Décomposition d’un problème complexe en parties plus simples, plus facile à comprendre et à tester
* Optimisation de l’exécution grâce à un système de cache de résultat :
* Add(3) : mise en cache de la valeur 4 pour add avec 3 en paramètre
* Add(3) : inutile de faire l’appel : add 3 est en cache, retourne 4 immédiatement
* Parallélisation de l’exécution des fonctions car elle sont indépendantes les unes des autres et d’un contexte;

#### Immutabilité

* Prérequis de la programmation fonctionnelle où les variables ne changent pas après affectation;
* Car la mutation d’un élément peut entraîner des effets de bord;
* Simplifie la gestion d’état de l’application en réduisant le nombre de bugs introduits avec une mutation;

#### Assignation de fonction en TypeScript

Les fonctions sont des objets. Elles peuvent être :
* Affectées à des variables;
* Passées en paramètre à une fonction;
* Retournées par une fonction;

##### Fonction Lambda

* Fonction anonyme;
* Utilisée de manière ponctuelle;
* N’effectuant généralement qu’une seule opération;
* Par exemple: `let my_func = x => x * 2;`

#### Fonction d’ordre supérieur

* Soit elle prend une ou plusieurs fonctions en paramètres;
* Soit elle renvoie une fonction;
* Générer des fonctions pures, avec un seul argument:
* Principe de «curryfication»;
* Permettra la composition de fonctions;
* Meilleure expressivité du code :
* met l’accent sur la tâche à accomplir : format_dollar;
* plutôt que sur la façon de l’accomplir : format_devise;

#### La «closure» ou fermeture

* Fonction qui utilise des variables définies dans la portée englobante;
* Elle se souvient de l’environnement dans lequel elle a été créée;
* Elle «capture son environnement»;
* Exemple suivant: name et separator sont dits fermés, d’où la closure;

```Typescript
function logger(name) {
    let separator = ": ";
    function log(message){
        console.log(name + separator + message);
    }
    return log
}
let my_logger = logger("Typescript");
my_logger("J’ai capturé name et separator!");

// Or ->

let logger = separator => name => message => console.log(name + separator + message);
let colonLogger = logger(": ");
let my_logger = colonLogger("Typescript");
let mes = my_logger("coucou");
```

#### La curryfication

* Transformation d’une fonction à plusieurs arguments en fonction à un seul argument qui retourne une fonction sur le reste des arguments;
Pour:
* Créer une fonction pure;
* Permettre la réutilisabilité de code pour de nouvelles combinaisons et compositions;
* Grâce à la technique de closure, nous pouvons écrire une forme curryfiée;
* Exemple:

```Typescript
function logger(name, message){
let separator = ": ";
console.log(name + separator + message);
}

// To ->

let logger = separator => name => message => console.log(name + separator + message);

```

#### L’application partielle

* La curryfication permet l’application partielle;
* L’application partielle permet d'avoir une fonction réalisant uniquement le calcul demandé;
* Par exemple: `let colonLogger = logger(": ");`

#### La récursion

* En programmation fonctionnelle, on privéligie la récursion aux instructions de boucle comme for et while;
* Pas d’état (compteur) à maintenir, donc pas d’effets de bords;

```Typescript
let fact = n => {
if(n < 2){
return n;
}
return n * fact (n -1);
}
```

#### Recherche et transformation de listes

* Domaines où les boucles sont habituelles en langage impératif;
* En programmation fonctionnelle, privilégiez:
* filter() pour la recherche: list.filter(fonction_de_filtrage_booleenne) renvoie une liste filtrée;
* map() pour la transformation: liste_de_A.map(fonction_de_transformation_de_A_vers_B) renvoie une liste_de_B;
* reduce() Consiste à prendre un tableau, et à accumuler les éléments de celui-ci à l’aide d’une fonction associative; Le résultat est UNE valeur dont le type dépend de la fonction appliquée et de la valeur d’initialisation; Prend 2 paramètres: La fonction associative - dont les 2 premiers paramètres sont la valeur actuelle de l’accumulateur (vaut la valeur initiale à la 1ère itération) et la valeur du tableau de l’itération courante - qui renvoie la valeur de l’accumulateur de la prochaine itération et une valeur initiale. `let sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0);`

---

## Programmation logique

En Prolog, on énonce :
* Des faits;
* Des règles;
* Des questions;

#### Programmer en Prolog, c’est :
* Mettre à jour la base de connaissance (BC);
* Introduire des nouveaux faits et des nouvelles règles;
* Exécuter un programme Prolog, c’est Charger la BC;
* Poser des questions;

#### Applications:
* Traitement du langage naturel;
* Écriture de grammaire (analyseur syntaxique);
* Calcul formel;
* Système expert;
* Base de données déductive;
* Intelligence artificielle;

#### Faits
* Pour Prolog, des faits = «des données»;
* On veut déclarer que:
* Sébastien est le père de Elena;
* Les objets : Sébastien, Elena;
* Une relation : père;
* fait: pere(sebastien, elena);

#### Règles :
* Quand on a choisi un sens au fait, on s’y tient;
* L’ordre d’écriture des arguments est arbitraire mais il est choisi une fois pour toutes par le programmeur;
* Convention :verbe(sujet, complément);

#### Faits : 1ère base de connaissance
* Tous les faits définissant un même prédicat sont regroupés en séquence dans l’ordre énoncé par l’utilisateur.
* Ils forment un paquet de faits;
* L’intérêt est calcul;

#### Interrogations
* Prolog connaît maintenant notre BC familiale : on peut l’interroger;
* Questions avec inconnues : «De qui Robert est le père ?»;
* Conjonction de questions (de buts) ;
* En Prolog «,» = «et» = conjonction;
* Prolog cherche dans le paquet pere, une solution à pere(Robert, X)
* S’il y a une solution, X est instancié, lié puis Prolog cherche dans le paquet mere une solution à mere(Y, X) avec X lié;
* Non déterminisme :
* Prolog donne toutes les solutions;
* Explosion combinatoire éventuelle

#### Des règles
* Par une règle, on exprime qu’un fait peut se déduire / dépend d’autres faits;
* Conclusion de la règle <= hypothèse de la règle;

#### Termes
* les objets manipulés par Prolog sont appelés des terme;
* Constantes symboliques : apparaissent comme des noms écrits en minuscules;
* Variables : elles sont en majuscules, précisément la 1ère lettre est en majuscule;
* Constantes symboliques : apparaissent comme des noms écrits en minuscules;
* Variables : elles sont en majuscules, précisément la 1ère lettre est en majuscule;