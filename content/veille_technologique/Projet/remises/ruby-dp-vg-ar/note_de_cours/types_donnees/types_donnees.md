---
title: "Les Types de Données"
draft: false
type: "cours"
---

Les Types de Données

En Ruby, il existe des différents types de données. Ruby utilise un typage dynamique, ce qui signifie que le programmeur n’a pas besoin d’indiquer un type lors de la création d’une variable. Le type est déterminé automatiquement d’après la valeur assignée, ce qui simplifie le code et rend le langage plus flexible.

## Les Numéros

Ruby peut gérer différents types de nombres, notamment les integers (nombres entiers) et les floats (nombres décimaux). Le langage permet d’effectuer des opérations mathématiques entre ces deux types sans difficulté, et convertit automatiquement les valeurs lorsque c’est nécessaire.

```bash
# type float
distance = 0.1

# les deux types sont compatibles
time = 9.87 / 3600
speed = distance / time

puts "The average speed of a sprinter is #{speed} km/h"
```

Sortie : 

```bash
The average speed of a sprinter is 36.474164133738604 km/h 
```

## Boolean

Le type de donnée Boolean en Ruby sert à représenter une valeur logique, c’est-à-dire une information qui peut être soit vraie (true), soit fausse (false). Ce type est utilisé principalement dans les conditions, les comparaisons et les structures de contrôle. 

```bash
puts 2 + 5 == 7
puts 2 + 8 == 7
```

Sortie : 

```bash
true
false
```

## Strings

Pour déclarer une chaîne de caractères (string) en Ruby, la syntaxe est très simple et semblable à celle de nombreux autres langages. Il suffit d’entourer le texte avec des guillemets, soit doubles (" "), soit simples (' '). Ruby reconnaît automatiquement qu’il s’agit d’un string. 

```bash
# type string
text = "Exemple de texte"

# Affichage du string
puts text
```

Sortie : 
```bash
Exemple de texte
```

## nil
nil est l’équivalent de null dans d’autre langages. Il représente l’absence de valeur ou une valeur vide dans une variable. Lors d’un output, puts affiche une ligne vide tandis que p affiche nil. Également, lors d’une condition, (qu’on verra plus tard), il affiche toujours faux, sauf si la condition est que la variable est égale à nil. 

## Hashes

En Ruby, un Hash est une structure de données qui permet de stocker des informations sous forme de paires clé–valeur. Contrairement aux tableaux (Array) qui utilisent des index numériques, un Hash associe chaque valeur à une clé unique, souvent un symbole ou une chaîne. Les Hashes sont très utiles pour représenter des objets, des configurations ou des données structurées. 

```bash
# Création d'un hachage et itération sur ses paires clé-valeur
hsh = colors = { "red" => 0xf00, "green" => 0x0f0, "blue" => 0x00f }

hsh.each do |key, value|
  print key, " is ", value, "\n"
end

```
Sortie : 
```bash
red is 3840
green is 240
blue is 15
```

## Arrays

En Ruby, un Array est une structure de données qui permet de stocker une liste ordonnée d’éléments. Chaque élément possède une position appelée index, qui commence toujours de 0 et augmente en ordre croissant jusqu’au dernier élément. Il y a également les index négatifs qui commence de –1 pour le dernier élément jusqu’au début de l’élément en ordre décroissant. Également lorsqu’on utilise un index qui sont hors limite du tableau, cela donnera la valeur de nil au lieu d’afficher une erreur contrairement à d’autre langages. Les arrays peuvent contenir n’importe quel type de données : nombres, chaînes de caractères, objets, ou même d’autres arrays. Ils sont particulièrement utiles pour représenter des listes, des collections ou des séquences d’informations. 

```bash
ary = ["fred", 10, 3.14, "This is a string", "last element"]

puts ary[0]
puts ary[1]
puts ary[-1]

ary[0] = "barney"
puts ary[0]

puts ary[9]  # ligne vide
```
Sortie : 
```bash
fred
10
Last element
Barney
```

## Symbols

En Ruby, un Symbol est un type de donnée léger et immuable utilisé principalement comme identifiant ou comme clé dans les Hashes. Contrairement aux chaînes de caractères (String), un symbol ne change jamais et chaque symbol unique n’existe qu’une seule fois en mémoire, ce qui le rend plus performant pour représenter des noms, des labels ou des clés. Les symbols commencent par un deux-points, comme :nom ou :age. 


Dans l’exemple suivant :sk , :no et :hu sont des symbols. 

```bash
# Utilisation de symboles comme clés dans un hachage
domains = { :sk => "GeeksforGeeks", :no => "GFG", :hu => "Geeks" }

puts domains[:sk]
puts domains[:no]
puts domains[:hu]
```
Sortie : 
```bash
GeeksforGeeks
GFG
Geeks
```