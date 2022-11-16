# Systèmes d’exploitation

`Notes de cours par Thomas Peugnet `.



# Liste des questions qui pourraient tomber en QCM



> Les systèmes d’exploitation actuellement existants :
>
> - GNU/Linux
> - Windows
> - OpenBSD
> - z/OS

> la structure dans le noyau contenant les informations d’un processus ne s’appelle pas :
>
> - Process Central Block
> - Process Data Block
> - Process Identifier Data
> - Process General Identifier Data
>
> => **Aucune de ces réponses**

> Quelles informations sont situées dans l’**ABI** ?
>
> - La façon dont les paramètres de fonctions sont passés
> - La taille des entiers

> Sous UNIX, comment **les processus sont-ils créés ?**
>
> - En utilisant **fork()**
> - En dupliquant les structures existantes dans le noyau

> Dans un système **préemptif**, dans quels cas un processus peut-il être mis en état de « **Prêt**  » ?
>
> - Le processus a consommé tout son quantum de temps
> - Le processus vient d’être créé

> Comment libérer un processus **zombie** ?
>
> - En appelant **wait()** ou **waitpid()** dans le parent.

> Quls sont les états des processus gérés par l’ordonnaceur ?
>
> - En exécution
> - Prêt
> - Endormi

> - data –> Données initialisées
>
> - rodata –> Données initialisées non modifiables
> - Heap –> Données allouées dynamiquement en mémoire
> - text –> Code à éxécuter
> - BBS –> Données non initialisées (à 0)
> - Stack –> Varaibles allouées temporairement

> Si on propose un schéma avec 4 colonnes de 4 lignes, contenant des adresses, et qu’on demande l’adresse physique depuis une adresse virtuelle : 
>
> - Adresse Virtuelle : 0x00402042
> - PDBR : 0x12340000
> - **Adresse Physique :**  0x12340042

> Un fichier est créé et rempli avec 1.000 caractères. Combien d’octets consomme-t-il sur le support physique ?
> Encodage des caractères : 2 octets par caractère
> Taille des blocs : 1 secteur
> Taille de secteurs : 4096 octets
>
> - **4096** octets

> Un fichier a t il été effacé pour arriver à l’état dans lequel se trouve cet FAT ?
>
> Ordre des adresses dans la FAT : 0x0000, 0x0005, **0xFFFF**, 0x0004, 0xFFF7
>
> Ordre des chaines dans le Cluster : Bonjour, Hello, Hallo, Hola, Bonjourno
>
> - **Oui**

> En VFS, combien de **dentry** sont créées pour ce pathname : `/var/log/mod_test/program.log`
>
> - 4

> Sur Linux, le SuperBlock en VFS est toujours représentable par une ou des structures d’un système de fichier concret sous-jacent.
>
> - Vrai

> Selon les standars, les tubes sont bi-directionnels après un `fork()`
>
> - Non

> Ecrire dans un tube lorsqu’il est plein provoque-t-il un arrêt du processus ?
>
> - Seulement si l’écriture est synchrone

> Les IPC nommées peuvent être utilisées grâce à : 
>
> - rendez-vous points

> La famine est un état où…
>
> - Les processus/threads attendent sans pouvoir être sûrs d’entrer dans la section critique.

> Quelles sont les propriétés que doivent respecter les sections critiques pour être correctement gérées ?
>
> - Exclusion mutuelle
> - Attente limiée
> - Progrès

> Les sémaphores sont :
>
> - Des IPC
> - Côté Noyau