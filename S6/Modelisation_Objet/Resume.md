# Résumé

`Notes très partielles, provenant de la dernière partie du cours 1`.

> **1986 : ** Conférences ACM (Association for Computer Machinery)
>
> **1994** : ANSI comité X3J13

> - Il existe trois couches CLOS (Common Lisp Object System).
>
> - Fonctions génériques, multi-méthodes vs classes MOB1
>
> - Héritage multiple + système de précédence de classe linéarisé
>
> - Combinaison de méthodes
>
> - MOP (Meta Object Protocol), méta-circularité, méta-objets
>
> - Typage dynamique
>
> - Il n'y a pas d'encapsulation, de protection, etc.

> - Cycle de vie dynamique => une classe créée et modifiable à l'exécution, avec un typage dynamique.
> - Pas de méthodes membres
> - Définition fonctionnelle `defclass=macro` + instanciation fonctionnelle.
> - Pas de classe abstraite, ni finale tel que dans `CLOS`.
> - Pas de destructeur, car présence d'un Garbage collector.
> - `make-instance` est une fonction commune à toutes les classes.

> Slot-value pour valeur d'une variable
>
> - Accès fonctionnel, fonction commune à toutes les classes
> - Manque d'abstraction
>
> Accesseurs : fonctions génériques polymorphes, sur toutes les classes quel que soit l'ordre d'héritage.

> Typage dynamique + identification généricité
>
> classe -> Type (type-of), idem pour sub=-type
>
> clases sont toutes des stndard-class t class of
>
> MOP reflexivité
>
> metaclasse = classe d'une classe objets de premiere classe ou de premier ordre

> **Il existe trois types d'héritage** :
>
> - Agrégation simple
> - Composition/agrégation composite
> - Héritage/dérivation : héritage structure et comportement
>
> **Modèles dans CLOS **:
>
> - Héritage implicite : toutes les classes héritent de `t` et de `standard-object` 
>   - `standard-class` : super classe de toutes les classes utilisateurs
>   - `standard-object`: super classe de toutes les instances utilisateur
> - Héritage des slots : accumulation des définitions des slots dans les classes
> - Héritage des options : `initarg=accumulation` etc.
> - Héritage des méthodes : sous-classage -> sous-typage même si les méthodes sont en-dehors des classes
> - Héritage multiple : passage de classes en argument de `defclass`.
> - Instanciation en présence d'héritage : pas de constructeur, fonction `make-instance` => `make-class`.

> Problèmes liés à l'héritage :
>
> - Héritage vs instanciation
> - Ambivalence de l'héritage
>
> Alternatives :
>
> - Héritage par restrictions / programmation différenctielle

> Polymorphisme statique :
>
> - Surcharge : pas de sens en `CLOS` car typage dynamique et variadicité.
> - Masquage : pas de sens en `CLOS` car les méthodes sont en-dehors des classe.
>
> Polymorphisme dynamique :
>
> - Fonctions génériques : `defgeneric`
> - Méthodes : `defmethod`
>   - Définition fonctionnelle : macros
>   - Cycle de vie dynamique + typage dynamique
>   - Méta-object `standard-generic-function`: `standard-method`
>   - Appel d'une fonction générique correspond à l'appel d'une fonction standard
>   - Méthodes : spécialisation sur les arguments obligatoires, par défaut non spécialisés, spécialisés sur une classe `t`.
>   - Méthodes effectives : fonctions génériques, non exécutables et anonymes
>   - Multi-méthodes : spécialisation sur plusieurs arguments
>   - Chaînage de méthodes : `call-next-method` (ordre de spécificité décroissante, niveau d'abstraction plus élevé).

> Relation typage/classage
>
> - OK approche classique OO:
>   - Contravariance