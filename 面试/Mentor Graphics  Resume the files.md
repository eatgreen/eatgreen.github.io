# Introduction:
Réduire le temps de mise sur le marché, **time to market**
nombre de transistors

puce SoC microprocesseur, traitement analogique et numérique du signal, circuit d'interface, système d'exploitation, composant de radiofréquence.

Conçu, vérifiés et validés de manière sure.

AMS/RF

# 1. simulation des circuits: environnement d'utilisation et principales caractéristiques
## 1.1 simulation dans le flot de conception des circuits:
AMS/RF est de pouvoir simuler tout le circuit dans un premier temps avec des blocs définis à un haut niveau d'abstraction.
## 1.2 simulation dans le flot de vérification des circuits
60,70% du cycle de production d'une puce. La simulation HDL, langages. HVL(hardware vérification langages)
## 1.3 caractéristiques requises pour le simulateur
* vitesse
* capacité
* précision
* convergence(robustesse)
* analyses
* support des langages HDL utilisés pour la conception
* support des langages HVL utilisés pour la conception
* facilité d'utilisation

## 1.4. segmentation du marché
* simulation de circuits intégrés de type SPICE
* simulation de type SPICE-rapide
* simulation RF
* simulation mixte=1+2+3+simulation numérique

### 1.4.1 simulation de circuits intégrés de type SPICE
#### 1.4.1.1 Différents produits disponibles
#### 1.4.1.2 condition d'utilisation
#### 1.4.1.3 logiciels en amélioration constante
* parallélisation du code
* utilisation crossante des statistiques
* Les langages comportementaux
* prise en compte des imperfections

### 1.4.2 simulation de circuits de type FastSPICE
#### 1.4.2.1 Différents produits disponibles
utilises pour valider, juste avant de fabriquer, des conceptions complètes au niveau transistor.
#### 1.4.2.2 condition d'utilisation
#### 1.4.2.3 logiciels en amélioration constante
* optimisation des algorithmes
* parallélisation du code
* prise en compte des imperfections
* nouveaux besoin

### 1.4.3 simulation de circuits,  de type RF
domaine fréquentiel
### 1.4.4 simulation de circuits de type mixte
#### 1.4.4.3 logiciels en amélioration constante
* extension des méthodologies utilisées en numérique
* extension de l'utilisation dans les phases amont
* extension de l'utilisation vers les phases aval
 
#### 1.4.4.4 Besoins en ordinateurs et systèmes d'exploitation
une unité de calcul en virgule flottante performante,
une très haute fréquence d'horloge
une mémoire cache importante
un accès disque rapide

### 1.4.5 simulation de carte et autre modules

# 2. Simulation analogique
## 2.1 principes généraux, terminologie
Le concepteur pourra, après avoir vérifié par simulation que le fonctionnement correspond à ses calcul, utiliser à nouveau le simulateur pour optimiser **le gain, la linéarité ou la puissance** en fonction des spécifications.

les algorithmes et méthodes numériques: 

* traditionnelles: SPICE
* non traditionnelles: SPICE-rapides

### 2.1.1 modes de simulation
Pour des composants numériques, une présentation fonctionnelle et un mode de simulation dirigée par événements (contre espaces temps)

### 2.1.2 domaines d'analyses
un système d'équations algébrodifférentielles :
\\[F(x,t,dx/dt)=0;\\]

#### Approches analyse
Alors l'analyse antomatique de circuit consiste à déterminer la solition de l'équation pour les différent domaines de simulation:

* Domaines continu: on ne considère pas $\frac{dx}{dt}$, on va avoir un système algébriques non linéaire.
* Domaines fréquentiel: l'analyse en petite signaux permet de déterminer la réponse du circuit en régime permanent sinusoïdal. Les composant nonlinear sont remplacés par des modèles équivalents résultant d'une linéarisation autour d'un point de fonctionnement. $\frac{dx}{dt}$ remplacé par le vecteur $j\omega x$.
* Domaines temporel: déterminer la réponse transitoire d'un circuit sur un intervalles de temps. Un algorithm d'intégration est employé pour transformer le systeme d'équations différentielles en un systeme algébrique non linéaire équivilent. 

#### Méthodes numérique
- la formulation des équations de circuit à partir du fichier de description
- la résolution du système linéaire d'équations algébriques
- la résolution du système non linéaire d'équation algébrique
- l'intégration numérique

#### Critères d'évaluation
- la robustesse
- l'efficacité
- la précision 
- la rapidité 

### 2.1.3 Définitions et domaines de validité
**Kirchhoff**


## 2.2 algorithmes de base de la simulation analogique
### 2.2.1 formulation des équations du circuit
- Les lois de Kirchhoff.
- Les équation constitutives des éléments.

#### 2.2.1.1 principales des méthodes de formulation des équations du circuit
Le terme de branche, emprunté à la théorie des graphes

* chaque relation de branche doit être satisfaite à chaque instant
**B(x,t,dx/dt)=0;**
si un circuit contient b branches, B est un système de b équations.
* les lois topologiques de Kirchhoff doivent être satisfaite à chaque instant
**Tx=0;**

#### 2.2.1.2 Relations de branche, équations constitutives des branches
* la courant: 电流
* la tension: 电压
* la résister idéal: 电阻
* branche définie en courant
* branche capacitive: 电容
* branche définie en tension
* branche inductive:

#### 2.2.1.3 lois topologiques de Kirchhoff
* LKT: la somme algébrique des différences de potentiel le long d'une boucle du réseau est nulle, à chaque instant
* LKC: la somme algébrique des courants traversant  chaque noeud du réseau est nulle, à chaque instant

#### 2.2.1.4 approche nodale modifiée (ANM)
LKC nous donne **Yv=J** avec

- Y la matrice $n\timesn$ des admittances nodales,
- v le vecteur $n\times1$ des potentiel inconnus,
- J le vecteur $n\times1$ des sources de courant d'entree.

### 2.2.2 résolution  du  système linéaire d'équations
*Ax=b; méthodes directe et méthodes itératives.

#### 2.2.2.1 LU décomposition
#### 2.2.2.2 techniques appliquées aux matrices creuses
Il faut cependat que l'ordre dans lequel les variables sont éliminées soit choisi pour toujouts maintenit l'aspect clairsemé de la matrice.

Stratégy de reclassment. 

### 2.2.3 résolution du  système non linéaire
#### 2.2.3.1 Méthode de Newton-Raphson
\\[f(x,\frac{dx}{dt},t)=0; x(0)=x_0
\\]

- discrétiser les dérivées afin de transfomer en un systeme d'équation non linéaires, algébriques de la forme
**G(x)=0;**
- une méthodes itérative afin de résoudre le système
- échec de l'algorithme de non-convergence: divergence, oscillation, dépassement de capacité numérique, vitesse de convergence extrêmement faible

#### 2.2.3.2 convergence de l'algorithme de Newton
* la topologie du circuit
* les modèles
* le paramétrage du simulateur

### 2.2.4 intégration numérique
pour déterminer la réponse transitoire d'un circuit sur un intervalle de temps spécifiée.

## 2.3 Différentes analyses

- la détermination du point de fonctionement en continu
- l'analyse tempotelle 
- l'analyse fréquentielle en petite signaux

Une analyse temporelle non linéaire est faire d'une succession d'appels à la routine de détermination d'un point de fonctionnement en continu.

L'analyse fréquentielle en petits signaux déterminera ce point de fonctionnement avant d'effectuer le calcul point par point. 

La détermination du point de fonctionnment en continu est une boucle d'itérations de Newton.

### 2.3.1 calcul du point de fonctionnement en continu
SPICE
### 2.3.2 Analyse en continu

### 2.3.3 Analyse en régime transitoire
avec condition initiales, computer la réponse temporelle du circuit sur un intervalle de temps.

### 2.3.4 Analyse en régime fréquentiel petits signaux

# 3. simulation des circuit en radiofréquence
Ces circuit servent principalement dans le système de communication sans-fils.
## 3.1 Analyse dy régime établi. Equilibrage harmonique
considèrant le circuit est stimulé par des signaux périodiques ou quasi pérodique. 
n'import quel signal peut etre repreesenté mathématiquement sous forme d'une série de Fourier.
de la même façon un signal quasi périodique s'écrira sous la forme d'une série de Fourier à deux dimension.

Le calcul du régime établi d'un circuit revient à calculer les coefficient de la série de Fourier des tension de chaque noeud de ce circuit.

Pour réduire la taille du système à résoudre, les séries de Fourier sont bien évidemment tronquées.

Les lois de Kirchhoff en courant sur chaque noeud:
$f(v(t))=i(v(t))+\frac{dq(v(t))}{dt}+u(t)=0$
## 3.2 Analyse linéaires autour du régime établi

## 3.3 Approche mixte temps-fréquence pour l'analyse de sigmaux modules (analyse d'enveloppe)
Les signaux RF réels peuvent etre décrits comme de signaux modulés.

Un signal modulé peut etre représenté mathématiquement sous la form d'une serie de Fourier a corfficients variables dans le temps.


# 4. simulation des circuit numérique
## 4.1 modélisation des circuits logiques
### 4.1.1 niveau d'abstraction des modèles
* la simulation niveau interrupteur
* la simulation niveau porte logique
* la simulation niveau fonctionnel
* la simulation niveau registre de transfert

### 4.1.2 Représentation des signaux

### 4.1.3. Représentation des porte logiques
la temporisation modéliser le temps de propagation des portes
l'opération de determination de la valeur de sortie

#### 4.1.3.1 temps de propagation
#### 4.1.3.2 détermination de la valeur de sortie
#### 4.1.3.3 modèle de la porte logique

## 4.2 algorithme de simulation des circuits logiques
déclenchée par l'apparition d'un événement
un événement dans une simulation logique est un changement à un noeud

* extraire de la queue d'événement tous les événements dont l'instant d'occurrence est t.
mettre à jour les noeuds attachés aux entrées qui ont changé
* calculer les nouvelles valeurs des sorties selon les nouvelles valeur des entrées
* créer un événement, pour chaque noeud connecté à une sortie ayant été affectée à l'étape précédente. L'insérer dans la queue au temps $t+\delta t$, $\delta t$ étant le temps de propagation

# 5 simulation des circuits et systèmes en mode mixte
* combiner différents algorithmes en une structure unifiée et de l'appliquer à l'ensemble du circuits décrit avec des niveau d'abstraction différents

* l'approche augmentée
* l'approche couplée
* l'approche intégrée

## 5.1 interfaçage entre le numérique et l'analogique: les convertisseurs
A2D, D2A

## 5.2 problèmes de synchronisation

## 5.3 algorithme de simulation en mode mixte


# 6. conclusion
La validation devient de plus en plus critique. et les outil plus en plus diversifiés (des vérificateurs de règles, de la preuve formelle, des langages d'assertion, des méthodes de réutilisation)

La coeur de cette validation reste la simulation.

L'innovation viendra de l'introduction de nouveaux algorithme, de l'utilisation de nouvelle architectures d'ordinateurs et même de remise en cause de l'architecture du logiciel.

Défis:

* la simulation au niveau transistor de fonctions complètes.
* la variation des élément géométrique sur une puce


Résumé: les défis sont permanents et ce marché de la simulation, stimulé par les évolutions technologiques du milieu du circuit intégré, va encore connaitre des évolution très importantes.