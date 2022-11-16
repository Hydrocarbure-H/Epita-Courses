# Probabilités et statistiques

## Activité 3 - Analyse des données botaniques

Par Dorian TURGOT et Thomas PEUGNET.

### Questions

> - **Si on considère toutes les données, les quatre variables continues sont-elles corrélées ?**

> - **Qu'en est-il si on isole les observations concernant une seule espèce ?**

> - **Est-ce que la loi des quatre variables continues dépend de l'espèce ? Pour chaque variable continue 𝑋X et chaque espèce, comparer E(𝑋)E(X) et E(𝑋|espèce)E(X|espèce).**

### 1. Les variables sont-elles corrélées ?

La corrélation de ces deux variables a été faite à l'aide de la méthode `Pearson`.

![image-20220528155451930](/Users/thomas/Library/Application Support/typora-user-images/image-20220528155451930.png)

En gris : Corrélation des variables de l'espèce.

**Cercle de corrélation :**

![image-20220528160002786](/Users/thomas/Library/Application Support/typora-user-images/image-20220528160002786.png)

Variables présentes (peu lisibles), de haut en bas : `Sepal.Width`, `Sepal.Length`, `Petal.Width`, `Petal.Length`

Nous pouvons remarquer que la variable Sepal.Width est indépendante, contrairement aux trois autres qui semblent fortement corrélées.

### 2. Isolation des observations

D'après les précédents schémas, nous pouvons observer que :

- **Versicolor **: Il n'existe aucune relation.
- **Virginica** : Il existe une relation entre les variables  `Petal.Length` et `Sepal.Length`.
- **Setosa** : Il existe une relation entre les variables `Sepal.Length` et `Sepal.Width`, ainsi que `Petal.Length` et `Petal.Width`.

### 3. La loi des 4 variables dépend-elle de l'espèce ?

Nous n'avons pas réussi à répondre à cette question pour des raisons techniques. Néanmoins, nous avons une supposition sur le démarrage de la marche à suivre pour l'appliquer. Selon nous, il faudrait commencer par vérifier qu'il existe une relation entre la taille et une espèce donnée. La méthode du KhiCarré semblerait pertinente, mais nous n'avons pas réussi à la mettre en place. 

- En supposant que cette relation existe, il faudrait prouver prouver que la variable ne suit pas une loi quelconque pour prouver que l'espèce est indépendante.

- En supposant que cette relation n'existe pas, nous ne savons pas quelles démarches il faudrait entreprendre.