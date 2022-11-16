# Questions !

> De quel concept **Christohper Strachey** est-il à l'origine ?
>
> - L'ordre supérieur

> En Haskell, quelle est la valeur de `ssq 1` pour `ssq` définie comme suit :
>
> `ssq :: Int -> Int`
>
> `ssq n = n * ssq (n - 1`
>
> `ssq 1 = 1`
>
> - Stack Overflow

> En Haskell, que représente l'expression `(x:xs)`:
>
> - La liste ayant pour premier élément `x`, et pour reste la liste `xs`.

> EN Haskell, que représente l'expression `bar :: Float -> Float`
>
> - La fonction d'un flottant vers un flottant

> En Lisp, que donne l'évaluation de l'expression `e1 e2 e3` :
>
> - L'appel de la fonction nommée `e1` sur les valeurs des variables `e2` `e 3`.

> Parmis les intérêts de la pureté :
>
> - Il n'y a jamais de problème de concurrence d'accès aux données.

> En Haskell, que représente `[t]` :
>
> - C'est une liste d'éléments de type `t` pour tout `t`.

> Dans un langage fonctionnel pur : 
>
> - Il n'y a que des constantes.

> Que signifie l'expression `Lisp-2` : 
>
> - Qu'il existe des espaces de noms **distincts** pour les **variables** et les **fonctions**.

> Dans une approche fonctionnelle, on a tendance à exprimer : 
>
> - Le haut niveau d'abstraction en **premier**.

> En `Lisp`, les valeurs **booléennes** sont représentées par : 
>
> - `nil` ou la liste vide, et tout sauf `nil`.

> Que fait la fonction suivante en `haskell` :
>
> ```haskell
> f :: a -> Bool
> f x = (:type x) == List
> ```
>
> - Une erreur de syntaxe. `:type x` est incorrect.

> En `Haskell`, que représente l'expression `foo :: Float` : 
>
> - Une constante nommée `foo` et contenant un flottant.

> Que vaut l'expression `(foo foo)` en `Lisp` :
>
> - L'appel à la fonction `foo` avec la variable `foo` comme argument.

> Que fait la fonction complément en `Lisp` :
>
> - Elle prend une fonction booléenne et renvoie une fonction produisant le résultat inverse.

> Le mapping **généralisé**, dans un langage fonctionnel, c'est :
>
> - Un mapping **combinant** plusieurs listes entre elles.

> Qu'appelle-t-on "**Lambda expression**" en `Lisp` : 
>
> - L'expression d'une fonction **anonyme**.

> En `Lisp`, que vaut l'expression suivante :
>
> ```lisp
> ((lambda (x) (lambda (n) (+ n x))) 5)
> ```
>
> - La fonction `+5`

> Que fait la fonction suivante en `Haskell` : 
>
> ```haskell
> f n = \ x -> x + n
> ```
>
> - *Elle prend un nombre n et renvoie une fonction qui ajoute n à son argument* ?

> En `Haskell`, que représente l'expression `n -> 2 * n` :
>
> - La fonction double.

> En langage C, les blocs (entre accolades) sont des formes embryonnaires de :
>
> - Fonctions ou procédures anonymes.

> Que signifie l'expression suivante en `Haskell` : `a . b` :
>
> - La composition des fonctions `a` et `b`.

> En `Haskell`, que vaut l'expresson :
>
> ```haskell
> [ n == 3 | <- [ 2 , 3 , 4 ]]
> ```
>
> - `[ False, True, False ]`

> Qu'appelle-t-on **réduction** dans un langage fonctionnel :
>
> - La combinaison de tous les éléments d'une liste 2 à 2, par une fonction.

> Qu'appelle-t-on "coupure d'opérateur" en `Haskell` :
>
> - L'application partielle d'un opérateur à un seul argument.

> La définition de fonction `Haskell` suivante est-elle correcte :
>
> ```haskell
> backwards :: [a] -> [a]
> backwards = reverse
> ```
>
> - Oui, car `reverse` et `backwards` ont le même prototype.

> Qu'appelle-t-on "Application partielle" en `Haskell` :
>
> - Le passage à une fonction de moins d'arguments que sa définition ne l'indique.

> En `Lisp`, quelle est la valeur de l'expression suivante : 
>
> ```lisp
> (flet ((foo (x) (* 2 x))) (foo "bar"))
> ```
>
> - Aucune valeur, mais une erreur de **type**.
>   - `2x` sur une chaine de caractères

> Que vaut l'évaluation de l'expression suivante en `Lisp`: 
>
> ```lisp
> (let ((a 2)
>    (b (+ a 1)))
>   (- a 1))
> ```
>
> - `Unbound variable : a`

> En `Lisp`, quelle est la différence entre (`list a b)` et `'(a b)` : 
>
> - Dans le premier cas, `a` et `b` sont évalués.

> Quelle est la valeur de l'expression : 
>
> ```lisp
> (car (list 1 (error "Barf!")))
> ```
>
> - `Simple-error: Barf!`

> Qu'appelle-t-on "opérateur spécial" en `Lisp` :
>
> - Une fonction n'obéissant pas aux règles de l'évaluation stricte.
>   - Exemple : `', if, etc.`

> En `Haskell`, quelle est la valeur de l'expression `head [1, error "Barf! "]` :
>
> - C'est **1**.
>   - Ce n'est pas une évaluation **stricte**, mais à la **demande**.

> Qu'appelle-t-on "**Modèle de substitution**" :
>
> - *Le principe de **remplacement** de paramètres formels …?*

> Quelle fonctionnalité n'est pas **idiomatiquement** **non**-**stricte** :
>
> - Les branchements conditionnels.

> Qu'est-ce que le **Scopping** **lexical** :
>
> - Rechercher les valeurs des variables libres dans l'environnement de l'expression concernée.

> En `Lisp`, que vaut l'expression `(quote ABC)` :
>
> - Le symbole `ABC`.

> En `Lisp`, quelle est la différence entre `let` et `let*` :
>
> - `let*` permet les références croisées entre les variables.

> Qu'est-ce que le **scoping dynamique :**
>
> - Rechercher les valeurs des variables libres dans l'environnement d'appel de l'expression…

> Dans la fonction 
>
> ```lisp
> (defun sq (x) (* x x))
> ```
>
> La variable `x` est :
>
> - liée

> Comment appelle-t-on ce type de forme :
>
> ```lisp
> (let ((x 1)) (lambda () (incf x)))
> ```
>
> - Une fermeture lexicale

> En `Haskell`, il est possible d'utiliser la notation préfixe pour les opérateurs infixes, tels `+`. L'expression `a + b` s'écrit :
>
> - `(+) a b`

> En `Haskell`, il existe un **séparateur** **implicite** qui remplace **l'offside** **rule**, lors du parsing. Ce séparateur est :
>
> - `;`

> En `Haskell`, que signifie `[a] -> Int` :
>
> - Une fonction d'une liste de n'importe quel type `a`vers un entier.

> En ` Haskell`, que vaut l'expression `double 3 + 4.0` pour `double` définie comme suit :
>
> ```haskell
> double :: Int -> Int
> double x = 2 * x
> ```
>
> - **10.0**

> On parle de typage **fort** quand :
>
> - Aucune erreur de type ne passe sans être vue.

> Un **évaluateur paresseux** permet d'exprimer plus de choses :
>
> - Par exemple : Des structures de données **infinies**

> Les **fonctions pures** n'existent pas. Les **langages purs**, eux, oui.

> Qu'appelle-t-on "**tree-accumulation**" :
>
> - L'évaluation récursive de gauche à droite de toutes les expressions d'une expression fonctionnelle.

> Qu'est-ce qu'une variable déclarée **spéciale** en `Lisp` :
>
> - C'est une variable **libre** scopée **dynamiquement**.

> En ` Haskell`, que vaut l'expression `let x = 5 in foo 1` sachant que l'on a les définitions suivantes au préalable :
>
> ```haskell
> a :: Int
> a = 10
> foo :: Int -> Int
> foo x = a - x
> ```
>
> - C'est **9**.

> En `Haskell`, quel est le résultat de `foo = 2 * foo` :
>
> - L'expression elle-même.