# Mathématiques du signal

# Introduction

## Définitions

Un signal est une observation/mesure d’un phénomène physique ou chimique qui varie dans le temps et ou l’espace, et qui transporte de l’information.

Il existe deux types de signaux :

-   Analogique : varie de maière continue par rapport à ses variables et aux valeurs qu’il peut prendre.
-   Varie de manière discrète par rapport à ses variables, et qux valeurs qu`il peut prendre. Un signal **discret** correspond à tout ce qui est manipulable par un ordinateur.

Un signal **déterministe** : signal qui ne possède pas de bruit, signal théorique.

## Exemples :

Lumière, son, onde gravitationnelle, onde sismique, tension, intensité, absorbance chimique.

**Problème : pourquoi le son est-il échantillonné à 44,1 kHz ?**

## Rappels 

Vérifier connaissances sur les produits scalaires, dans `n`  dimensions, ainsi que les connaissances sur les nombres complexes.

Une fonction est intégrable sur un ensemble ssi l’integrale du module de la fonction est fini.

-   $<,> : L² (\R) \times L² (\R) \rightarrow \R$

-   $<x(t), y(t)> \rightarrow <x,y>$
-   $|| x || = \sqrt{<x,y>}$

## Avance ou retard d’une fonction

$x(t-\tau)$  avec $\tau$ qui représente le retard de la fonction.

-   $\tau>0$ –>décalage de la fonction vers la droite du graphe, et retardée de $\tau$.

---

# Énergie et puissance d’un signal

Un signal est défini comme fonction d’une seule variable `x`.

**Représentation** : $ graph(t, x(t)) $ Est la représentation temporelle du signal $x$.

Restrictions pour $x(t)$ : 

-   $|x(t)|<+\infty $ 
-   $x(t)$  est continue.

L’ensemble des signaux constitue un **espace vectoriel.** On peut donc effectuer des calculs de base, etc.

## Exemple 

Se réferrer à : *I. Exemple 1*

## Énergie

**Définition : **$\int _{R} |x(t)|² $ = $\int_{-T/2}^{T/2}A²dt$.

Un support est dit borné lorsque sa courbe est bornée (ordonnées et absisses).

Tout signal $x$ **sur support borné est d’énergie finie.**

Tout signal T-périodique n’est pas d’énergie finie. (exemple : $x(t)=cos\omega t$).

## Puissance moyenne

**Définition** : $P_x = \lim 1/T \times\int_{-t/2}^{T/2} |x(t)|dt$

La puissance moyenne ne dépend pas du nombre de périodes. On trouvera le même résultat.

**Remarque** : Une puissance moyenne est dite finie, si $P_x<-\infty$.

---

# Corrélation et Convolution

## Auto-corrélation

*Regarder la similarité entre deux signaux.*

### Propriétés

-   $\Gamma _{xx} (\tau) =\space <x(t), x(t-\tau)>\space = \int_{-\infty}^{+\infty}x(t)\times(--(x-\tau))dt$

-   $\Gamma_{xx}(0) = E_x$, ou $=P_x$ si $x \in L^{pm}(\R)$
-   $\Gamma_{xx}(\tau) = \Gamma_{xx}(-\tau)$, car la fonction est symétrique
-   Si $x \in L² (\R)$, alors $\Gamma_{xx}(\tau) <+\infty$
-   $|\Gamma{xx}(\tau)| \leq E_x$

Avec $\tau$ étant le décalage.

### Signal T-périodique

-   $x(t+T) = x(t)$
-   $\Gamma_{xx}(\tau = <x(t), x(t-\tau-T)>$

### Fonction d’inter-corrélation

*Sert à à reconnaître des formes dans des signaux.*

$\Gamma{xy}(\tau)=<x(t),y(t-\tau)>$

### Exemple

Se réferrer à *II. Exemple du radar*.

-   $t_0 : t = 0$ : Le moment oú le signal est envoyé.

## Convolution

-   $(x*y⁻)(\tau) = \int _R x(t)(–y(\tau-t))dt$

### Propriétés

-   Commutativité : $(x*y)(\tau)=(y*x)(\tau)$
-   Bilinéarité : $x*(y+\lambda z) = x*y*\lambda z)$
-   Associativité
-   Élément neutre : $x*n=n*x=x$
-   Symétrie
-   Dérivation : $(x*y)’ = d(x*y)/d\tau$

---

# Série de Fourrier

## Théorème de Dirichlet

>   *Soit $x \in C ([0, T])$ et  T-périodique*
>
>   >   En tout point de continuité de $x$, $S_n(t)$ converge vers $x(t)$ .
>   >
>   >   -   Prérequis :
>   >       -   $S_n(t) = a_0 + \Sigma_{k=1}^N x_k(t)$ avec $a_0 = 1/T \int_0^Tx(t)dt$
>   >       -   $\forall x >= 1$, avec $a_k = 2/T \int_0^Tx(t)\cos(\frac{2\pi k}{T} \times t)dt$ et  $b_k = \frac{2}{T} \int_0^Tx(t)\sin(\frac{2\pi k}{T} \times t)dt$.
>   >   -   $x(t) ~ \Sigma_{k=1}^n(a_k \times \cos(\frac{2\pi k}{T} \times t) + b_k\sin(\frac{2\pi k}{T} \times t)) + a_0$

Par ailleurs, si $x$ est **discontinue** en $t$, alors $S_N$ converge vers $\frac{1}{2}\times (x(t^-) + x(t^+))$.
$$
S_N(t) = \Sigma_{k=-\infty}^{+\infty}C_k e^{\frac{i2\pi k}{T}\times t}\\
C_n = \frac{1}{T} \times \int_0^Tx(t)e^{\frac{-i2\pi k}{T}\times t} \\ (\forall n \in \Z)
$$

>   $R $–>$ \C$
>
>   $ cos\Theta = 1/2 \times (e^{i\Theta} + e^{-i\Theta})$ et $ sin\Theta = 1/2i \times (e^{i\Theta} - e^{-i\Theta})$

Donc,

>   $x(t) = a_0 + \Sigma _{k=1}^{\infty} [\frac{a_k}{2}(e^{i2\pi kt/T} + e^{-i2\pi kt/T}) + \frac{a_k}{2i} (e^{i2\pi kt/T} - e^{-i2\pi kt/T})]$
>
>   $x(t) = a_0 + \Sigma _{k=1}^{\infty} \frac{1}{2}e^{i2\pi kt/T}(a_k - ib_k) +  \Sigma _{k=1}^{\infty} \frac{1}{2}e^{i2\pi kt/T}(a_k + ib_k)$
>
>   $x(t) = a_0 + \Sigma _{k=1}^{\infty} \frac{1}{2}e^{i2\pi kt/T}(a_k - ib_k) +  \Sigma _{-\infty}^{k=1} \frac{1}{2}e^{i2\pi kt/T}(a_k + ib_k)$  –> Changement d’indice sur la deuxième somme
>
>   $x(t) =  \Sigma _{-\infty}^{\infty} \frac{1}{2}e^{i2\pi kt/T}(a_k - ib_k)$ –> On somme les deux indices des deux sommes
>
>   $x(t) =  \Sigma _{-\infty}^{\infty} \frac{1}{2}e^{i2\pi kt/T}C_k$  Avec $C_k = (a_k - ib_k)$

La suite du cours n’est pas nécessaire à ce document, car il s’agit simplement de la démonstration des coefficients de Fourrier, $a_k, b_k$.

## Formule de la Série de Fourrier

>   -   $a_n = 2/T \int_0^T f(t) \cos (nωt) dt $
>   -   $b_n = 2/T \int_0^T f(t) \sin (nωt) dt $
>
>   -   $a_0 = 1/T \int_0^T f(t)dt$

# Transformée de Fourrier

## Définitions

>   -   $ X : \R $ –> $ \C$
>   -   $\nu_n = n/T$
>
>   -   $\nu$ –> $X(\nu) = \int_{\R} x(t)e^{-i2\pi \nu t}dt$
>
>   $\Pi_t : t$ –> ${1 \space \forall t \in [-T/2;T/2]}$, 0 sinon.
>
>   => $F (\Pi_t (t)) = \frac{i}{2\pi \nu} (e^{-i\pi \nu T} -e^{i\pi \nu T})$
>
>   => $F (\Pi_t (t)) = T.sinC(\pi \nu T)$ avec $sinC$ correspondant à $\sin(x)/x$ 

## Propriétés

>   **Involution** : $x(t) = \int_\R X(\nu)e^{i2\pi \nu t} d\nu = F^{-1} (X(\nu))$
>
>   **Parité** : 
>
>   Si $x$ est pair :
>
>   -   $X(\nu) = \int_\R x(t)e^{-i2\pi \nu t}dt$, ce qui, sur $\R$, implique que la partie imaginaire est nulle.
>       -   $= \int_\R x(t)\cos(2\pi \nu t)dt + 0$, avec $0$ correspondant à la partie $i\sin…$
>
>   Si $x$ est impaire :
>
>   -   $X(\nu)= \int_\R x(t)\cos(2\pi \nu t)dt$
>
>   **Relations :**
>
>   -   $x \in i \R$ **pair** $\leftrightarrow \space X \in i\R$ **pair**.
>   -   $x \in i \R$ **impair** $\leftrightarrow \space X \in i\R$ **pair**.
>
>   $X(\nu) \in \C$, $X(\nu) = Re(X) + i\Im(X)$
>
>   $X(\nu) = |X(\nu)|.e^{i\Phi(X)}$, avec $|X|$ le spectre du signal, et $e^X$ la phase du signal.



## $\Delta$ de Dirac

*Complément de cours : Delta de Dirac, 5 graphs*. 

### Propriétés

$\Delta (t - t_0) = {+\infty}$ si $t = t_0$, $0$ sinon.

$x(t).\Delta(t-t_0) = x(t_0).\Delta(t-t_0)$

### Exemple

$F(\Delta (t)) = \int_\R \Delta(t-0) \times e^{-i2\pi\nu t} dt$

$F(\Delta (t)) = 1$
