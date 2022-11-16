# Typologie des langages

Notes de cours par `Hugo Deplagne`, mise en page par `Thomas Peugnet`.

## Routines

« At the beginning, it was auxiliary functions. »

Généralisation : `modules/objects`

### Procédures

- Aucune valeur de retour
- Effet de bord

### Fonction

- Retourne quelque chose
- Les fonctions **pures** n'ont pas d'effets de bords

### `Nested symptoms`

- Des fonctions à l'intérieur de d'autres fonctions

### Arguments par défaut

- Il est possible de leur donner des valeurs par défaut

### Ordre des arguments

- Il est possible de changer l'odre d'appel des arguments

## Évolution strategy

### Call by value

- Define a variable, then call it in a fuction it coill not be changed.
- Makes a copy into formal parameter takes space
- Evaluation beore call
- Be carefull for side effects

### Call by reference

- Change arguments passed to a function
- Readibilyty & undesirable behaviour

### Call by value-result

- Copy at start
- Copy at exit
- Really safe

### Call by none

- `sum(i, 1, 100, v[i])`
- Passed by none. If change another function, `v[i] wil change

### Call by need

- Manage parameters only when they are needed

### Call by sharing

- `Python`

- ```python
  def f(list):
    list.append(1)
  m = []
  f(m)
  print(m)
  ```

## Return statement

- Keyboard return – Last computed
- Function name – Named return value
- Specific variable  – Form a block

## Programming by contract (Eiffel)

- Precondition, based on arguments, for example
- Post condition, based on variable inside function, for example
- (`assert`, `Invariant, Variant`)

## Inheritance

- Simple inheritance, herit from form at most 1
- Multiple inheritance, more powerful but introduces problems
  - Solution : Eiffel adaptation classes
    - Remaining classes, remove the problematic call
    - Visibility filter, make private some methodes or variables
    - Redefinition classes, redefine methods

