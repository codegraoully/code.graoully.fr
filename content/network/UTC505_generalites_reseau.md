
## Modele OSI

|OSI|TCP/IP|
|---|---|
|Application|Processus utilisateur|
|Presentation|Processus utilisateur|
|Session|Processus utilisateur|
|Transport|TCP / UDP|
|Réseau|IP|
|Liaison|LLC: Logical Link Control MAC: Medium Access Control PSS: Physical Signaling Sublaye|
|Physique||

### La couche Physique

Un signal est transporté par une onde porteuse variant en: s(t) = A sin(wt+o) et en utilisant différente type de modulation;
* w pulsation = 2𝛑f
* fréquence (f) - nombre de période T en 1 seconde, T correspondant au temps qu'il faut pour que le signal  soit entièrement répété;
* en phase (o phi) - décalage du début de la sinusoïde;
* amplitude (A) - hauteur de la sinusoïde;

#### Codage du signal

* Bande de base:  2v-5v -> 1 et 0v -> 0
* NRZ non retour à zéro : +5v -> 1 et -5v -> 0
* Code Manchester: variation de transition entre +Xv -> 0 et - Xv -> 1
* Code Manchester différentiel: variation de transition dans le temps élémentaire sans différence entre +Xv et -Xv: milieu de temps -> 1 début de temps -> 0
* Code de Miller: sans transition de signal -> 0 et une transition en milieu de temps élémentaire représente un 1

#### Définitions

* Bande passante: intervalle de fréquences à l'intérieur duquel les signaux seront transmis.
* Valance : un codage associe une valeur physique à une valeur logique, +5v -> 1.
* Moment élémentaire: durée d'emission du signal physique pour re reconnu par le récepteur.
* vitesse de modulation: nombres de valeurs physique émise en une seconde - rapidité de modulation - exprimé en bauds: Rm = 1 / Tm.
* Débit binaire: vitesse de transmission, nombres de valeurs logique émise en une seconde en bit/seconde: D = (Rm/k)log2(V); avec k nb de valeurs physique pour coder une information et V la valance.

#### Déformation

* Affaiblissement;
* Distorsions;
* Bruits;