---
title: "Les fonctions en Ruby"
---

En Ruby, une fonction — qu’on appelle **méthode** — se définit avec le mot-clé `def` et doit toujours se terminer par `end`.  
Tout le code compris entre ces deux mots forme **le corps de la méthode**.

```bash 

def greeting
    puts "Hello, World!"
    return
end

```
Output :

```bash
Hello, World!
```

## Fonctions avec paramètres

Comme dans la plupart des autres langages, les fonctions en Ruby peuvent recevoir des paramètres, qui permettent de leur transmettre des valeurs lors de l’appel. Ces paramètres sont définis entre les parenthèses après le nom de la méthode. 

```bash 

def greeting(name)
    puts "Hello, #{name}!"
    return
end

greeting("John")
#Output : Hello, John!

greeting("Marry")
#Output : Hello, Mary!

```
Ruby a toutefois une particularité importante : les parenthèses sont optionnelles lors de l’appel d’une fonction. Cela rend le code plus naturel et plus lisible, tout en laissant la liberté d’ajouter les parenthèses si cela améliore la clarté. 

## Retour implcite et retour explicite

Ruby a toutefois une particularité importante : les parenthèses sont optionnelles lors de l’appel d’une fonction. Cela rend le code plus naturel et plus lisible, tout en laissant la liberté d’ajouter les parenthèses si cela améliore la clarté. 


```bash 

def greeting(name)
  return "Hello, #{name}!"
end

greeting("John")
# Output: => Hello, John!


# Returns the value of the last expression evaluated
def greeting(name)
  "Hello, #{name}!"
end

greeting("Mary")
# Output: => Hello, Mary!

```

## Valeurs par défaut

Une valeur par défaut permet à une méthode d’utiliser automatiquement un paramètre prédéfini lorsque aucun argument n’est fourni. Cela rend l’appel plus flexible et évite les erreurs.

```bash 

def greeting(name = "human")
  return "Hello, #{name}!"
end

greeting
# Output: => Hello, human!
```

