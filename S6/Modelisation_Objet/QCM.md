# QCM - Modélisation Objet



> Qu’est-ce qu’une méthode binaire ?
>
> - Dans l’approche classique, une méthode polymorphe prenant un argument de même classe que sa classe de définition.

> De quelle couche logiciel CLOS `initialize-instance` fait-elle partie ?
>
> - 3

> Qu’est-ce au’une `initform` dans CLOS ?
>
> - Une expression dont la valeur sert à initialiser un slot par défaut.

> Pourquoi `slot–value`est-il considéré comme un mécanisme de bas niveau ?
>
> - Il est nécessaire de connaître le nom du slot afin d’y accéder, donc on manque d’abstraction.

> Par rapport aux méthodes classiques, quelles sont les caractéristiques de celles de CLOS ?
>
> - On n’exécute jamais une méthode directement
> - On peut spécialiser sur plusieurs arguments (multi-méthodes)
> - Les méthodes ne font pas partie des classes

> Une multi-méthode c’est :
>
> - Une méthode spécialisable sur plusieurs arguments

> Un `before-method` c’est :
>
> - Une méthode exécutée pour ses effets de bord, avant les effets primaires

> Comment créer une méthode par défaut dans CLOS ?
>
> - Il suffit de ne pas spécialiser les arguments

> Qu’est-ce qu’un `reade` en CLOS ?
>
> - Une fonction générique d’accès en lecture à un slot

> De quelle couche de CLOS `make-instance` fait-elle partie ?
>
> - 2

> Pour quelles raisons une foncton classique, appliquée à des objts, offre-t-elle déjà une forme de généricité :
>
> - Parce que les méthodes de CLOS sont extérieures aux classes
> - À cause du typage dynamique

> Qu’est-ce qu’un `writer` en CLOS :
>
> - Une fonction générique d’accès en écriture à un slot

> En quoi les attributs de classe dans CLOS sont-ils différents de l’approche classique ?
>
> - Il n’existe pas de mécanisme pour y accéder à travers une classe plutôt qu’à travers une instance
> - La notion de méthode de classe (ne pouvant accéder qu’aux attributs de classe) n’existe pas

> Que fait la fonction `call-next-method` :
>
> - Si elle existe, elle appelle la prochaine méthode dans l’ordre des méthodes applicables

> Que se pase-t-il si l’on définit une méthode sans que la fonction générique correspondante existe :
>
> - La fonction générique est créée automatiquement

> Que fait la fonction `change-class` :
>
> - Elle change la classe d’une instance

> Qu’estce que l’option `:allocation d’un slot:`
>
> - C’est l’option spécifiant si un slot est local à une instane ou partagé par toutes les instances d’une classe

> De quelle couche logicielle de CLOS `defgeneric` fait-elle partie :
>
> - 1

> Quelles forme de polymorphisme existent dans CLOS :
>
> - La généricité due au typage dynamique
> - La ré-écriture

> Comment s’appelle la classe racine de outes les classes dans CLOS :
>
> - `t` 