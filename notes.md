# Notes sur la validatoin croisée

## Nico

### Trois principaux types

#### Test set

C'est celui qu'on connait le plus :

- séparation du train set en *train* et *validation*

On entraîne un modèle sur le set de *train* et lui applique le set de *validation*.
On estime ensuite la performance du modèle.

##### Avantages

La methode la plus simple.
Permet le plus facilement de sélectionner un modèle

##### Inconvenients

Perte de données pour l'entraînement du modèle.
Si le *dataset* est petit peut causer une **variance** élevée.

#### leave-one-out

On défini un échantillon.
Tout le reste du set sert de train et on évalue sur l'échantillon.
On regarde ensuite la moyenne des performances du modèle sur chaque échantillon.

**cas particulier du *K-fold***

##### Avantages

Pas de perte de données

##### Inconvenients

Très lent, donc peu utilisé

#### K-fold

On divise ne échantillons de part égales et on observe les réultat de test après le passage de chaque échantillon au modèle.

##### Avantages

Le meilleur des deux mondes. Equilibre entre les deux autres méthodes.

- très bon en regression

##### Inconvenients

Ne convient pas aux *datasets* avec des répartitions de classes déséquilibrées.

#### Shuffle-split

- alternative à *K-Fold* avec un train/val split aléatoire un certain nombre de fois.

#### Stratified K-Folds

- On sépare par classes et on peut ensuite réaliser des entraînements dont on sait que la répartition des classes est respectée.

#### Group K-Fold

Dans le cas où une variable dépendante serait liée à une classe particulière.
Ex : Une famille de diabétiques => un individus a plus de chance d'être diabétique.
