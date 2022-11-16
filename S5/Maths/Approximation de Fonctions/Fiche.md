# Fiche APXF

`Notes de cours par Thomas Peugnet`.

# Symétrie :

> Concerne les graphes non-orientés.

# Séparation : 

> Concerne les graphes qui ne possèdent pas de cycle.

## Distance définie pour tout couple : 

> Concerne les graphes connexes.

# Inégalité triangulaire :

> $d(x,y) \leq d(x,z) + d(z,y)$

# Distance $E \times E$ –> $\R$ :

> **Séparation :** $d(x,y)=0$ –> $x = y$
>
> **Symétrie :** $d(x,y) = d(y,x)$
>
> **Inégalité triangulaire** : Voir ci-dessus.

# Boule :

> Quels sont les points qui sont à une distance $\leq$ rayon ?
>
> - Compter tous les points, sans oublier le point du centre.

# Distance euclidienne :

> $\sqrt{(x_2-x_1)^2+(y_2 - y_1)^2}$
>
> - Appliquer avec le nombre de composantes.

# Distance de Manhattan :

> $d(A,B)=|x_B - x_A| + |y_B - y_A|$
>
> - Appliquer avec le nombre de composantes.

# Relation Norme & Distance :

> $d(x,y)=N(x-y)$
>
> - Norme : Distance de $0_E$ –> Point
> - Distance : Point –> Point

# Distance  :

> - Distance infinie : $\max(|d(x,x')|, |d(y,y')|)$
>
> - $|x|_1 = |a| + |b| + |c|$
> - $|x|_2=\sqrt{a^2 + b^2 + c^2}$

# Normes équivalentes :

> $\exists a,b \forall x \in E : aN(x) \leq N'(x) \leq bN(x)$

# Égalité de distances :

> $|x|_\infty \leq |x|_1$
>
> - **égaux si les coefficients sont nuls**
> - Sinon : $|x|_1 \leq n|x|_\infty$

# $||f||_\infty$ :

> On calcule le tableau de variations. On trouve pour quel $x_{max}$ on trouve le maximum de $f$. Enfin, on calcule $f(x_{max})$.