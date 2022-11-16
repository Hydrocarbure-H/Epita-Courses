# Tiger - notes

# Comment fonctionne un compilateur

> TC1 - Lexer
>
> TC2 - Parser/AST
>
> TC3 - Binder
>
> TC4 - Type checker
>
> TCL - LLVM

# Analyse lexicale - TC1

String en entrée –> tokens en sortie

=> Permet de supprimer le bruit

`let var a = 12 in a + 1`

> - `let`-> token let
> - `var`-> token var
> - `[a-z]`-> token id
> - `[0-9]` -> token number

Analyseur lexical utilisé pour Tigrou : `Flex`.

# Générateur d'analyse lexicale

`Flex file`-> `Flex` -> `C File`

`Flex file` :

```
%{
	[pre-code C 9nec. def0]
%}...
```

```
yyllex
yytext
yyleng
yywrap
```

