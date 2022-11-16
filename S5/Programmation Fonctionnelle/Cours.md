# Programmation fonctionnelle

`Notes de cours par Thomas Peugnet`.

Langage de programmation basé sur un système formel de calcul. (**Top Down**)

# Introduction

## Règles

-   Variable : `x`

-   Abstraction : ($\lambda x.M$)
-   Application : $(MN)$

## Opérateurs

-   $\alpha$-conversion : ($\lambda x .M[x])$ -> $(\lambda y . M[y])$

-   $\beta$-conversion : (($\lambda x .M)[E])$ -> $(Mx := E)$

## `Lisp`

>   Créé par **John McCarty** en 1960, c’est le premier langage fonctionnel qui a été créé, et le deuxième langage de plus haut niveau.
>
>   Paradigme : manière de s’exprimer dans un langage.
>
>   Multi-paradigme : permet de supporter plusieurs langages.

## Autres langages

>   -   IPL
>   -   APL
>   -   ML, OCaml

# Paradigme de programmation

## Rappels sur la notion de paradigme

>   -   Affecte l’expressivité d’un langage
>   -   Affecte la manière de penser dans un langage
>   -   Porosité

## Paradigme fonctionnel

>   -   Expression (vs. Instruction)
>   -   Évaluation (vs. Exécution)

```lisp
(defun ssq (n)
    (if (= n 1)
        1
        (+ (* n n) (ssq(1- n))))
```

`Absolument infâmes à écrire ces parenthèses`.

```lisp
(defun hypo (a b)
    (sqrt(+ (* a a) (* b b))))
```

```haskell
hypo :: Float -> Float -> Float
hypo a b = sqrt(a*a + b*b)
```

Équivalent en `C`:

```c
float hypo (float a, float b)
{
    return sqrt(a * a + b * b);
}
```

# Caractéristiques de l’Approche de l’ordre supérieur (Important)

## Définition

*Approche classique* :

```lisp
(defun backwards (lst) (reverse lst))
```

*Ordre supérieur :*

```lisp
;; Function to function
(setf (symbol-function 'backwards) #'reverse)

;; Variable to function
(setq function2 function 1)

;; Function to variable
(setq function2 #'function1)

;; Variable to function
(setf (symbol-function) 'function1 function2)
```

## Variables locales

Nul besoin de définir les variables locales.

```lisp
(defun f(x)
    (let ((a (* x x))
          (b (+ (* x x)))
    (+ (/ a b) (/ b a))))
```

Il n’y a pas de références mutuelles dans `let`. Il faut alors utiliser `let*`.

## Principe d’Évaluation

>   *Quand calculer la valeur d’une expression ?*

-   Au préalable (`Lisp`, évaluations strictes).
-   À la demande (`Haskell`, évaluations paresseuses).

### Exemple

```lisp
(defun intlist (s)
    (cons s (intlist (1+ a))))
```

```haskell
intlist :: Int -> [ Int ]
intlist s = s : intlist (s + 1)
```

### Intérêt

>   Il y a plus d’expressivité, de clarté, de concision, etc.

### Contrainte

>   Fonctionnel pur uniquement.

## Programmation fonctionnelle pure

### Fonction

-   **Impératif** : (procédure) ensemble de calculs à effets de bords avec éventuellement retour d’une valeur.
-   **Fonctionnel pur** : calcul d’une valeur de sortie (retour) en fonction de valeurs d’entrée (arguments). 

### Variable

-   **Impératif** : Stockage d’informations qui varie au cours du temps (mutation).
-   **Fonctionnel** **pur** : Valeur inconnue.

```lisp
(defun foo 10)
(netq foo 10)
(netq bar (sqrt (- (* 3 (+ 6 7)))))
(netq boo bar)
(defun baz (a b)
    (sqrt (- (* 3 ( + a 7)) b)))
```

*On parle d’abstraction fonctionnelle, car on utilise une fonction pour affecter une valeur.*

### Vocabulaire

-   **Nommage** (fonctionnel pur) : *Donner un nom à une valeur.* 
    -   Une valeur peut donc avoir différents noms.

-   **Affectation** (fonctionnel impur) : *Donner une valeur à un nom.* 
    -   Un nom peut donc avoir différentes valeurs.

# `Lisp-2`

## Chaque symbole possède **deux** valeurs

>   -   Une valeur quelconque.
>   -   Une valeur fonctionnelle.
>   -   Ces valeurs coexistent.

## Accès

>   -   `foobar` => *valeur*
>
>   -   #`foobar` => *fonction*

## Développement interactif

### Boucle “`read-eval-print`”

-   **Read** : saisir une expression
-   **Eval** : évaluer une expression
-   **Print** : présenter le résultat sous forme affichable

### Remarques

-   **Haskell** : $REPL$ limité (expressions vs. déclarations)
-   **Lisp** : interprétation / byte-[$JIT$] compilation au choix.

# Typage et vérification

## Typage

### Typage statique `Haskell`

>   -   **Typage** des variable / fonctions
>   -   **Vérifications** de type à la compilation
>   -   **Plus contraignant** que le typage dynamique
>
>   Déclaration d’une fonction : `baz :: Float -> Float`
>
>   Déclaration d’une constante : `baz :: Float`
>
>   *Accès dynamique potentiel*.

### Typage dynamique `Lisp`

>   -   **Typage** des valeurs
>   -   **Vérifications** des valeurs à l’exécution
>   -   **Impact** sur les performances et la sûreté
>
>   *Boxing : typage des valeurs.*
>
>   Accès dynamique langagier (fonctionnel)
>
>   ```lisp
>   (type-of this)
>   (typep that `integer)
>   ```

#### Vocabulaire

-   Vérification du type *dynamique* à l’exécution
-   Typage *implicite*

# Booléen

## `Lisp`

### Branchements conditionnels

```lisp
(defun max3 (m n p)
    (if (and (>= m n) (>= m p))
        m
        (if (and (>= n m) (>= n p))
			n
        p)))

(defun month1 (month)
    switch (month)
    case (jan  mar  mai...) 31
    case (fev avr juin...) 30
    [...])
```

`cond` permet de vérifier une assertion : `cond (Traitement conditionnel)`.

# Arithmétique

## Types numériques

> **Transtypage** a la même signification que le **cast**.
>
> -   **Prédicats** : `floatp, integerp, etc`
> -   **Transtypage implicite** : rationnels vers entiers, complexes vers réels
> -   **Transtypage opérationnel** :
>     -   **Automatique** : vers flottants ou complexes
>     -   **Explicite** : `float, coerce`
>
> **Attention : ** `eq` est un **équivalent**. `eq` est différent de `equal`.

# Listes

## Construction

### Forme canonique

>   -   Tête + reste
>   -   Constructions successives au-dessus de la liste vide

### `Haskell`

-   `(:) :: a` -> `[a] -> [a]`

### `Lisp`

-   `cons` (un prédicat `consp`), contient une valeur et un pointeur.
-   Liste vide : `nil` ou `()`.

## Accesseurs

### Canoniques

-   `Lisp` : `car / first, cdr / rest`.
-   `haskell` : `head, tail`.

### Positionnels

-   `Lisp` : `first … tenth`
-   `Haskeel` : `last, :: [a] -> int -> a`

### Structurels

-   `Lisp` : `last, nth, cdr`
-   `Haskell` : `drop`

# Homoiconicité

## Syntaxe

> -   S-Expression : atome ou liste
> -   Atome : littéral ou symbole
> -   Symbole : `foobar`
> -   Liste : `(a “foo” (bar +) 2.5)` etc.
>

*L’ homoiconicité signifie la même représentation.*

# Retours 

##  Fonctionnels

*Quand on a une fonction, on retourne une fonction.*

```lisp
(defun +/- (plusp)
    (if plusp #'+ #'-))
;; (funcall (+/- t) 4 2)
```

## Anonymes

Complément logique : 

```lisp
(defun complement (f)
    (lambda (#'rest args) (not apply g args)))
```

# Évaluation et Scoping

## Évaluation stricte

### Processus 

> 1. Évaluer les sous-expressions de gauche à droite.
>
> 2. Appliquer l'opérateur à ses arguments.

`(* (+ 2 (* 4 6)) (+ x 5 7))` 

### Mémoisation

`(5 + 1)` sginifie `6`. Partout où cette expression sera écrite, le programme conservera en cache cette information, et remplacera tous les `(5 + 1)` par `6`.

## Évaluation paresseuse

L'évaluation **stricte** est plus **efficace**. Il n'y  a pas de redondance de calcul, etc.

L'évaluation **paresseuse** est plus **expressive**. Notamment avec les structures de données **infinies**.

# Scoping

- Contexte

  > - Variable liée (définie dans le bloc local)
  > - Variable libre (non définie localement)

- Scoping

  > - Recherche d'une liaison la plus proche.

## Formes

### Rappels

C'est la recherche de la liaison la plus proche.

### Lexical (statique)

C'est la recherche dans l'environnement de définition

### Dynamique

C'est la recherche dans l'environnement d'appel.

### Remarque

`let` fait deux choses différentes à la fois.

## Notion de fermeture lexicale

### Définition

> C'est la combinaison d'une fonction avec son enviromenement de définition.
>
> *Les valeurs des variables sont libres au moment de la définition.*

### Intérêt

> Elle sous-entend tout le fonctionnement de l'ordre supérieur.

## Scoping Dynamique

### Intérêt

> - Il existe certains paradigmes (Programmation orientée contexte, etc).
>
> - Gestion des exceptions, avec des `handlers`.
> - Il existe des variables globales.

### Inconvénient

> - C'est inadapté à l'ordre supérieur.
> - Source de bugs très difficiles à pister.
