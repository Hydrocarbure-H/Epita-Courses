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