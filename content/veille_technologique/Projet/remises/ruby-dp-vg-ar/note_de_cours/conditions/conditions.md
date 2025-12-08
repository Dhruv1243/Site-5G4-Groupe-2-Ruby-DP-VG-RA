---
title: "Les conditions"
---


Une condition permet d’exécuter différentes actions selon la valeur d’une variable ou le résultat d’une expression.



# Opérateurs logiques

Un opérateur logique est utilisé dans une expression logique pour produire une valeur booléenne (`true` ou `false`).

## Liste des opérateurs logiques

| Opérateur | Description |
|----------|-------------|
| `!` (NON) | Inverse la valeur d’un booléen ou d’une expression |
| `&&` (ET) | Renvoie `true` si **toutes** les conditions sont vraies |
| `||` (OU) | Renvoie `true` si **au moins une** des conditions est vraie |



## Exemples

```bash
puts !true ## retourne false
```

### Opérateur `!`

Inverse la valeur :
- `!true` → `false`
- `!false` → `true`



### Opérateur `&&` (ET)

| A     | B     | Résultat |
|-------|-------|----------|
| false | false | false |
| false | true  | false |
| true  | false | false |
| true  | true  | true |



### Opérateur `||` (OU)

| A     | B     | Résultat |
|-------|-------|----------|
| false | false | false |
| false | true  | true |
| true  | false | true |
| true  | true  | true |



# Opérateurs de comparaison

Un opérateur de comparaison sert à comparer deux valeurs et retourne un booléen.

## Liste des opérateurs de comparaison

| Opérateur | Description |
|-----------|-------------|
| `==` (Égal à) | Vrai lorsque les deux valeurs sont égales |
| `!=` (Différent de) | Vrai lorsque les deux valeurs ne sont pas égales |
| `>` (Supérieur à) | Vrai lorsque `x` est supérieur à `y` |
| `<` (Inférieur à) | Vrai lorsque `x` est inférieur à `y` |
| `>=` (Supérieur ou égal à) | Vrai lorsque `x` est supérieur ou égal à `y` |
| `<=` (Inférieur ou égal à) | Vrai lorsque `x` est inférieur ou égal à `y` |
| `===` (Égalité stricte) | Vrai si les deux valeurs sont entièrement identiques |

# Si ... alors

If (si) vérifie la condition et si c’est vrai, alors (then) un code sera exécuté. 

L’utilisation du then n’est pas obligatoire mais il est surtout utilisé lorsque la condition et le bloc à exécuter sont écrits sur une ligne pour faciliter la lisibilité du code.  

Exemple sans then :

```bash
x = 10

if (x > 5)
  puts "x est supérieur que 5"
end
```

Exemple sans then :

```bash
x = 10

if (x > 5) sans
  puts "x est supérieur que 5"
end
```

Sur une ligne de code

```bash
x = 10

if (x > 5) then puts "x est supérieur que 5" end

```
# Si ... sinon

Pour exécuter du code lorsqu’il est faux, on ajoute else (sinon).  

Exemple sans then :

```bash
x = 4

if (x > 5) then
  puts "x est supérieur que 5"
else 
  puts "x est inférieur ou égal à 5" ## Affiche cette ligne
end
```

# Si ... sinon si 

Si on souhaite exécuter du code en fonction de plusieurs conditions, alors l’utilisation du elsif (sinon si) sera utilisé pour tester d’autres conditions et else sera utiliser 
