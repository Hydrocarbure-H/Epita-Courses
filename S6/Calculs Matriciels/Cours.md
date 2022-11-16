# Calculs matriciels

`Notes de cours par Thomas Peugnet`

# Analyse Numérique

> - $A$ est **symétrique** si et seulement si $A^T=A$
> - $A$ est **hermitienne** si et seulement si $A=A^*$
> - $A$ est **orthogonale** si et seulement si $AA^T=I$
> - $A$ est **unitaire** si et seulement si $AA^X=A^XA=I$
> - $A$ est **symétrique** si et seulement si $AA^*=A^*A$

> Le spectre d'une matrice de $A$ est l'ensemble des valeurs propres de la matrice, racine du polynôme caractéristique.

**Notation : **

- $Sp(A)$

**Remarque : **

- $tr(A) = tr(P^{-1}TP)=tr(T)$

## Rayon spectral

> - $\phi(A) = \max\{|\lambda| \lambda \in Sp(A)\}$, avec $Sp(A)$ le spectre de la matrice $A$.

## Théorème

> - Soit $A \in M_N(K)$, il existe $\cup$ unitaire tel que $\cup^{-1}A\cup$ soit **triangulaire**.
> - Soit $A \in M_N(K)$, $A$ normale ==> $\exist \cup$ unitaire tel que $\cup^{-1}A\cup$ soit **diagonale**.
> - Soit $A \in S_n(K), \exist O \in O_n(K)$ tel que $O^{-1}AO$ soit **diagonale**. Avec $O$ -> Orthogonale.
> - Soit $A \in M_N(\R)$, $\exist O_1, O_2 \in O_n(\R)$ tel que $O_2^TAO_1 = diag(\lambda)$.

## Propriété

> Soit $A \in M_N(\C)$ :
>
> - $A^*=A$
> - $A$ définie **positive**
>
> **=>** $\exist \cup \in M_n(\C)$ tel que $A = \cup^* \cup$

**Décomposition de Cholesky** : 

> - $\forall X$, $^tXAX > 0$
> - $\forall X$, $^tXAX = 0$ => $X=0$

**Norme matricielle** définie sur $M_n(K) = ||.||$

> - $||A|| \geq 0$
> - $||A|| = 0$ => $A=0$
> - $||A+B|| \leq ||A|| + ||B||$
> - $AB|| \leq ||A||.||B||$

**Norme subordonnée** :

> $||A|| = \sup\frac{AX}{X}$ avec $X \in (K^n)^X$