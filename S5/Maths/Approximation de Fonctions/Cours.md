# Approximation de fonctions

`Notes de cours par Thomas Peugnet`.

# Introduction

Une suite $U_n$ converge vers $l$ si $\forall \epsilon > 0, \exists N \in \N, n >= N \rightarrow |U_n - l| < \epsilon$

-   $|U_n - l| < \epsilon$ => $U_n$ est à **au plus** $\epsilon$ de $f$.
-   $\forall \epsilon > 0, \exists N \in \N, n >= N$  => $f_n$ est à **distance** au plus $\epsilon$ de $f$.



## Question : Comment parler de distance entre deux éléments de $E$ ?



## Définitions

### Distance

-   *Une distance est une fonction sur $E \times E$ à valeurs positives.*

-   *La distance entre un élément de $E$ et lui-même est nulle.*
-   *Étant donnés 2 éléments $x, y$ de E et un élément intermédiaire $z$, la somme des distances entre $x$ et $z$ puis $z$ et $y$ ne peut être plus petite que celle entre $x$ et $y$.*

>   Une **distance** sur un ensemble de $E$ est une application $d : E\times E \rightarrow \R_+$ qui satisfait :
>
>   -   Séparation : $\forall x,y \in E, d(x,y) = 0 \Leftrightarrow x = y$
>   -   Symétrie : $\forall x,y \in E, d(x,y) = d(y,x)$
>   -   Inégalité $\Delta$ : $\forall x,y,z \in E, d(x,y) \leq d(x,z) + d(z,y)$

### Normes

>   On dit qu’une application $N:E \rightarrow \R_+$ est **une norme** sur $E$ si elle vérifie :
>
>   -   Définition : $\forall x \in E$, $N(x) = 0 \Leftrightarrow x = 0$
>   -   Homogénéité : $\forall x \in E, \forall \lambda \in K$, $N(\lambda x) = |\lambda|N(x)$
>   -   Inégalité $\Delta$ : $\forall (x,y) \in E²$, $N(x+y) \leq N(x) + N(y)$



**Une norme $N$ sur $E$ induit une distance $d_N$ sur $E$ par la relation :**
$$
\forall(x,y) \in E², d_N(x,y) = N(x-y)
$$
$d_N$ correspond à la distance, et $N(x-y)$ est la norme de la différence entre $x$ et $y$.

On peut donc dire que la norme d’un vecteur correspond à sa distance de $0_E$ :
$$
N(x) = d_N(x,0_E)
$$

>   On appelle boule ouverte centrée en $a$ de rayon $r$ par rapport à la distance $d$ l’ensemble : 
>   $$
>   B_d(a,r) = {x\in E|d(a,x)<r}
>   $$

### Exemple

![graph-1](/home/thomas/Cours/Actuels/Maths/Approximation de Fonctions/graph-1.png)

On peut remarquer l’inégalité :

-   $||x-y||_{\infty} \leq ||x-y||_2 \leq ||x-y||_1$
-   Et :
    -   $||x||_\infty \leq ||x||_2 \leq ||x||_1 \leq n||x||_\infty$

-   Enfin :
    -   $p < q \Rightarrow ||x||_p \geq ||x||_q$

### Normes équivalentes

On dit que deux normaes $N$ et $N’$ sur $E$ sont équivalentes si et seulement s’il existe deux réels strictement positifs $k_1$ et $k_2$ tels que :
$$
\forall x \in E, k_1 N(x) \leq Nx)\leq k_2 N(x)
$$
Avec $k_1$ et $k_2$ ne dépendant pas de $x$.

**Théorème de l’équivalence des normes en dimensions finie :**

-   Si $E$ est une espace vectoriel de dimension finie, alors toutes les normes sur $E$ sont équivalentes.



### Exemple

![graph_2](/home/thomas/Cours/Actuels/Maths/Approximation de Fonctions/graph_2.png)



### Normes usuelles

>   Soit $I$ un segment de $\R$ non réduit à un seul point. On se place sur l’ensemble $C$ ($C^0(I,\R)$) des fonctions continues sur $I$ à valeur dans $\R$.
>
>
>   Soit $p \in [1, +\infty[$. On appelle **nombre $p$** sur $C$ la norme notée $|| . ||_p$ définie pour tout $f \in C$ par :
>   $$
>   ||f||_p = (\int_I |f(t)|^p dt)^{1/p}
>   $$
>   Pour $p = + \infty$, on pose :
>   $$
>   ||f||_\infty = \sup|f(x)|
>   $$
>   On note $d_p$ la distance induite par $||.||_p$.



# Convergence et séries de Fonctions

`Notes de cours provenant de la fiche S4 de Mr. Cambon`.

## Suites de fonctions

### Convergence simple

>   $f_n(x)$ –> $f(x)$ quand $n$ –> $+ \infty$.

### Convergence uniforme

>   $f_n(x)$ converge uniformément sur $I$ vers $f(x)$ si :
>
>   -   $ \sup |f_n (x) - f(x)|$ –> $0$ quand $n$ –> $+ \infty$.

*Par ailleurs, la convergence uniforme implique forcément la convergence simple.*

*La limite de l’intégrale est égal à l’intégrale de la limite.* 

>   $\lim \int_a^b f_n(x)dx =\int_a^b  \lim f_n(x)dx =  \int_a^b f_n(x)dx$

## Séries de fonctions

### Convergence simple

>   $\Sigma f_k(x)$ converge simplement sur $I$ si :
>
>   -   $\Sigma f_k (x)$ converge

### Convergence uniforme

>   $\Sigma f_k(x)$ converge uniformément sur $I$ si :
>
>   -   $\sup |R_n(x)|$ existe, et tend vers $0$ quand $n$ –> $+ \infty$.
>       -   Avec $R_n(x)= \Sigma_{k=n+1}^{+\infty} f_k (x)$.

### Convergence normale

>   $\Sigma f_k(x)$ converge normalement sur $I$ si :
>
>   -   $\sup |f_n(x)|$ existe
>   -   $\Sigma \sup |f_n(x)$ converge

*Par ailleurs, la convergence normale implique nécessairement la convergence uniforme, qui elle-même implique forcément la convergence simple.*

*De plus, l’intégrale de la somme est égal à la somme de l’intégrale*.

## Séries alternées

>   Soit $U_n$ une suite positive et décroissante, alors :
>
>   -   $|\Sigma_{n_0}^n(-1)^nU_n|\leq U_{n_0}$ 

## Convergence dominée

>   Si $f = o (g)$, c’est-à-dire $\lim \frac{f(x)}{g(x)} = 0$, alors si $\int g$ converge, $\int f$ converge également.

## Équivalence

>   Si $f$~$ o (g)$, c’est-à-dire $\lim \frac{f(x)}{g(x)} = 1$, alors si $\int g$ et $\int f$ sont de même nature.

## Convergence absolue

>   $\int f(t)$ converge **absolument** si $\int |f(t)|$ converge.

*De plus, la convergence absolue implique la convergence.*

## Intégrale de Riemann

>   -   $\int_a^{+ \infty} \frac{1}{t^\alpha}dt $ converge si $\alpha > 1$.
>
>   -   $\int_0^a \frac{1}{t^\alpha}dt $ converge si $\alpha < 1$.
>
>   Avec $a>0$.
