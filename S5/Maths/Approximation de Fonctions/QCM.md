# QCM

> Soient $E$ un espace vectoriel sur $\R$ et $N$ une norme sur $E$.
>
> La distance $d$ induite par $N$ sur $E$ est donnée par la relation :
>
> - $D(x,y) = N(x - y)$

> Soit $y=(-4,-7, 4)$, que vaut $||y||_1$ :
>
> - 15

> Soit $y=(-4,-7, 4)$, que vaut $||y||_2$ :
>
> - 9

> Soit $y=(-4,-7, 4)$, que vaut $||y||_\infty$ :
>
> - 7

> Soient $a$ et $b$ deux réels et $f:[a,b]$⟶$\R$ une fonction continue sur $[a,b]$. Quelles affirmations parmi les suivantes sont vraies ?
>
> - $f$ est bornée sur $[a,b]$.
> - $f$ admet un maximum sur $[a,b]$.
>
> *Attention, Dérivable => Continue => Définie*. Inverse **faux**.

> Pour quelle(s) distance(s) sur $\R^2$ la boule de rayon $1$ centrée en $(0,0)$ associée est-elle le carré de sommets $(0,1),(1,0),(0,−1),(−1,0)(0,1),(1,0),(0,−1),(−1,0)$ ?
>
> - La distance de Manhattan

> Pour quelle(s) distance(s) sur $\R^2$ la boule de rayon $1$ centrée en $(0,0)$ associée est-elle le disque de centre $(0,0)$ et de rayon 1.
>
> - La distance Euclidienne

> Quelle est la limite de la suite de fonctions ($f_n$) avec $n \in N^*$, définie par
>
> $\forall x \in \R, f_n(x) = \frac{x^2 + n^2}{1+n}\times e^{x/n}$ :
>
> - On retrouve du $\frac{n^2}{n^2}$, donc vers la fonction constante égale  à $1$ sur $\R$.

> On suppose qu'une suite $f_n$ de fonctions de classe $C^1$ sur un segment $[a,b]$ converge uniformément vers une fonction $f$ sur cet intervalle. Alors :
>
> - $f$ est continue (car dérivable une fois)
> - $\int_a^bf_n (t)dt$ –> $\int_a^bf (t)dt$

> On cherche à définir la distance entre deux sommets d'un graphe valué comme le poids minimal pour un chemin reliant ces deux sommets. 
>
> - **Symétrie** –> Le graphe est non orienté
> - La distance est bien définie pour tout couple de sommets –> Le graphe est connexe
> - Inégalité **triangulaire** –> On choisit le poids minimal
> - **Séparation** –> Les valuations sont strictement positives.
> - La distance est à valeurs positives –> Les valuations sont strictement positives

> Ces fonctions sont des distances sur $E$ :
>
> - $(x,y)$ –> $0$ si $x=y$, $2$ si $x \neq y$ avec $E = [0,1]$
> - $(x,y)$ –> $|x-y|$ avec $E=\R$

> On muni ce graphe valué de la distance usuelle définie par le poids minimal pour un chemin entre deux sommets. Quels points dans la boule fermée de centre $a$ et de rayon $6$ ?
>
> - Compter tous les points à une distance de 6, mais aussi prendre le centre $a$ dont la distance $d(a,a) = 0$.

> On dit que deux normes $N_1$ et $N_2$ sur un espace vectoriel $E$ sont équivalents si :
>
> - Il existe deux réels $(k_1,k_2) \in (\R^*_+)^2$ tels que : $k_1N_1(x) \leq N_2(x)\leq k_2N_2(x)$.

> Donner un vecteur $u$ de $\R^2$ pour lequel $||u||_1 = ||u||_2 = ||u||_\infty = 1$ :
>
> - $(x,y) : (0,1) \space ou \space (1,0)$

> Quelles valeurs optimales peut-on trouver pour $\alpha$ et $\beta$ dans l'encadrement $\forall x \in \R^n, \alpha ||x||_1 \leq ||x||_infty \leq \beta ||x||_1$ :
>
> - $\alpha = \frac{1}{n}$, $\beta = 1$

> Soit une suite de vecteurs de $\R^n$ et $l \in \R^n$. On suppose que $||x_k - l||_\infty$ -> 0, alors $||x_k - l||_1$ –> 0 :
>
> - **Vrai**

> Une fonction sur un intervalle $[a,b]$ avec $a < b$. On suppose que $||f_n||_1$ –> 0, alors $||f_n||_\infty$ –> 0 :
>
> - **Faux**

> Pour une suite de fonction, l'assertion $||f_n||_\infty$ –> 0 => $||f_n||_1$ –> 0 :
>
> - Est vraie en particulier si on considère des fonctions **continues** définies sur un **segment**, mais **pas uniquement.**

> Déterminer la borne supérieur sur $\R$ de la fonction $\frac{x}{1+4x^2}$ : 
>
> - 0.25
>
> *On étudie les variations et on compare les valeurs aux bornes et les extrema locaux*.

> $||f||_1$ = ? avec $f$ sur $[a,b]$
>
> - Intégrale de $f$ sur $[a,b]$

# Limites de fonction

> La limite de la fonction $f_n (x) = n^2 e^{-nx²}$ est :
>
> - $0$ -> $1$, $x \neq 0$  -> $0$
>
> $e^X$ est celle qui a la plus forte croissance, et elle tend vers 0.

> $(f_n)$ converge uniquement vers $f$ :
>
> - $\sup |f_n(x) - f(x)|$ –> 0
> - $||f_n - f||_\infty$ –> 0

> $\sum n^3x^n$ converge simplement sur :
>
> - $]-1, 1[$

> $\sum n^3x^n$ converge **uniformément** et **normalement** sur :
>
> - $[-\frac{1}{2}, \frac{1}{2}]$

> La série de fonction $\sum f_n$ converge uniformément vers sa limite $S$ si :
>
> - $||S - \sum_{k=0}{n}f_k||_\infty$ –> $0$
> - $||R_n||_\infty$ –> 0

> - $\sum x^n$ sur $]-1, 1[$ converge absolument mais pas uniformément.
>
> - $\sum \frac{(-1)^nx}{n}$ sur $[0,1]$ converge normalement.
> - $\sum \frac{(-1)^nx}{n}$ sur $[0,1]$ converge uniformément mais pas absolument.

# Fourrier

## Complexe

> Soit une fonction $2\pi$ périodique, et **continue par morceaux**. Série de Fourrier associée $S(f(x))$ est donnée par :
>
> - $S(f(x)) = \sum_{k \in \Z}(\frac{1}{2\pi}\times \int_0^{2\pi}f(t)e^{-ikt}dt)e^{ikx}$

> **Les coefficients de Fourrier :**
>
> - $a_n(f) = c_n(f) + c_{-n}(f)$
> - $b_n(f) = i\times (c_n (f) - c_{-n}(f))$
> - $c_n(f)=\frac{1}{2}\times (a_n(f) - i(b_n(f)))$
> - $c_{-n}(f)=\frac{1}{2}\times (a_n(f) + i(b_n(f)))$

> **Parseval**
>
> - $\frac{1}{2\pi}\int_0^{2\pi}|f(t)|^2dt = \sum_{k\in\Z}|c_k(f)|^2$
> - $\forall k \in \Z, \space c_k(f')=ikc_k(f)$

## Réel

> - $S(f(t)) = \frac{a_0}{2} + \sum(a_n(f)\cos(nt) + b_n(f)\sin(nt))$

> Les **coefficients de Fourrier** : 
>
> - $a_n(f) =  \frac{1}{\pi} \int_{2\pi}f(t)\cos(nt)$
> - $b_n(f) =  \frac{1}{\pi} \int_{2\pi}f(t)\sin(nt)$
>
> Si $f$ est paire, $b_n=0$. Si $f$ est impaire, $a_n(f)=0$.

> **Parceval** :
>
> - $\frac{1} {2\pi}\int_{2\pi}(f(t))^2 = \frac{a_0^2(f)}{4}+\frac{1}{2}\sum(a_n^2(f) + b_n^2(f))$

> Soit $f$ une fonction $2\pi$ périodique,n et soit $S(f)$ sa série de Fourrier :
>
> - $S(f)$ n’est pas nécessairement convergente.

# Espaces Vectoriels

> On dit que deux normes $N_1$ et $N_2$ sont équivalentes si :
>
> - Il existe deux réels $(k_1,k_2) \in \R$ tels que $\forall x \in E, \space k_1N_1(x)\leq N_2(x) \leq k_2N_1(x)$

> On dit que $\phi$ est un produit scalaire sur $E$ si :
>
> - $\phi : E \times E$ –> $\R$
> - $\phi$ est bilinéaire
> - $\phi$ est homogène
> - $\phi$ est symétrique
> - $\phi$ est positive
> - $\phi$ est définie

> Dire qu’une forme bilinéaire $\phi$ est positive sur un EV $E$ :
>
> - $\forall x \in E, \space \phi (x,x) \geq 0$

> Soit un espace préhilbertien complexe muni de son produit scalaire $\phi$. La norme $N_\phi$ induite par $\phi$ est donnée par :
>
> - $\forall x \in E, N_\phi(x) = \sqrt{\phi(x,x)}$

> Soit $(E, +, ., \phi)$ un espace préhilbertien, et soit || . || la norme induite par $\phi$. Soit $x$ et $y$ deux vecteurs de $E$, alors :
>
> - Si $x$ et $y$ sont orthogonaux, alors $||x + y||^2 = ||x||^2 + ||y||^2$

