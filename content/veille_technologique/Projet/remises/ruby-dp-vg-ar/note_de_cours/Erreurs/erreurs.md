---
title: "Les erreurs"
---


Lors d'une exécution d'un programme, il peut rencontrer des erreurs qui empechent de rouler le code.



## Erreurs courantes
### SyntaxError
Cette erreur se produit lorsqu’on respecte pas la grammaire du langage.

Exemple :
```bash
def hello
  puts "Salut"
  # manque le end
```

### NameError
Cette erreur se produit lorsque le nom d'une variable, constante ou méthode est introuvable.
Exemple :
```bash
puts x  # x n’est pas défini
```

### NoMethodError
Cette erreur se produit lorsqu'on appelle une méthode qui n'existe pas sur un objet.
Exemple :
```bash
123.upcase   # Integer n’a pas de méthode upcase
```

### ArgumentError
Il se produit quand y a un mauvais nombre d'arguments ou incorrects sont fournis.
Exemple :
```bash
def add(a, b)
end

add(1, 2, 3)  # trop d’arguments
```

### TypeError
Il se produit quand il y a une opération entre deux types incompatibles.
Exemple :
```bash
1 + "2"   # Integer + String
```

### ZeroDivisionError
Il se produit lorsqu'il y a une divison par zéro. 
Exemple :
```bash
x = 10 / 0 # Divison impossible: Erreur
```

## Gérer les erreurs
Pour exécuter du code avec une partie du code qui contient une erreur sans qu'il crashe, on utilise `begin...rescue...end`

Exemple:
```bash
begin
  x = 10 / 0
rescue
  puts "Impossible de diviser par zéro."
end
```

Pour préciser et attraper certains types d'erreurs, on peut écrire le type d'erreur après `rescue`.
Exemple:
```bash
begin
  x = 10 / 0
rescue ZeroDivisionError
  puts "Impossible de diviser par zéro."
end
```

On peut aussi récupérer l'erreur après `rescue`
Exemple:
```bash
begin
  x = 10 / 0
rescue => e
  puts "Erreur : #{e.class} – #{e.message}"
end
```

On peut aussi gérer plusieurs erreurs.
Exemple:
```bash
begin
  puts "1" + 2
rescue TypeError
  puts "Erreur de type."
rescue NameError
  puts "Nom non défini."
rescue => e
  puts "Autre erreur : #{e.class}"
end
```

Il est également possible de créer et déclencher une erreur avec `raise`
Exemple:
```bash
def check_age(age)
  begin
    raise ArgumentError, "Âge négatif interdit" if age < 0
  rescue ArgumentError => e
    puts "Erreur détectée : #{e.message}" # Affiche Âge négatif interdit
  end
end

check_age(-5)
```

On peut utiliser `else` pour du code si aucune erreur s'est produite
Exemples:
```bash
begin
  x = 5 + 5
rescue
  puts "Erreur" # ne sera pas exécuté
else
  puts "Aucune erreur détectée" # sera exécuté
end
```
```bash
begin
  x = 10 / 0
rescue
  puts "Erreur" # sera exécuté
else
  puts "Aucune erreur détectée" # ne sera pas exécuté
end
```

Si on veut toujours exécuter du code qu'il ait une erreur ou non, on utilise `ensure`
Exemple:
```bash
begin
  x = 10 / 0
rescue
  puts "Impossible de diviser par zéro."
ensure
  puts "Fin du programme"
end
```