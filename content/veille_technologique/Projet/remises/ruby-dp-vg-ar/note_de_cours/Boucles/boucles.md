---
title: "Les boucles"
---


Une boucle est un mécanisme qui exécute plusieurs fois un même bloc de code en fonction d'une condition, généralement lorsqu’elle est vraie. Cependant, utiliser une condition incomplète ou mettre la valeur true directement comme condition peut provoquer une boucle infinie. 


## while 

La boucle `while` exécute le même code tant que cette dernière est vraie. La boucle s’arrête lorsque la condition est fausse. 

Exemple d’une boucle `while`:
```bash
i = 1

while i <= 5
  puts i
  i += 1
end
```

Exemple de boucle `while` infinie:
```bash
while true
  puts "Cette boucle tourne indéfiniment"
end
```
```bash
i = 1
while i == 1
  puts "Cette boucle tourne indéfiniment"
end
```

## until
La boucle `until` est l’inverse de while, il exécute tant que cette dernière est fausse. La boucle s’arrête lorsque la condition est vraie. 

Exemple d’une boucle `until`:
```bash
i = 1

while i > 5
  puts i
  i += 1
end
```

Exemple de boucle `until` infinie:
```bash
until false
  puts "Cette boucle tourne indéfiniment"
end
```
```bash
i = 1
while i == 0
  puts "Cette boucle tourne indéfiniment"
end
```

## do...while
La boucle `do... while` exécute du code en boucle jusqu’à que la condition soit fausse. Contrairement à la boucle `while`, la condition est vérifiée à la fin de la boucle, ce qui garantit que le bloc de code s’exécute au moins une fois, même si la condition est fausse dès le départ. 

En ruby, il y a deux façons de l'utiliser, la plus courante est avec `loop do... break if [condition]` et l’alternative (moins recommandé) est avec `begin... end while [condition]`

Exemple avec `loop do... break if [condition]`
```bash
i = 0

loop do
  puts i
  i += 1
  break if i > 3 # Quitte la boucle lorsque i est supérieur à 3
end
```

Exemple avec `begin... end while [condition]`
```bash
i = 0

begin
  puts i
  i += 1
end while i <= 3
```

Différence entre while et do... while 

while ne s’exécute pas une fois
```bash
i = 0

while i > 0
  puts "code non exécuté"
end
```

do...while est exécuté au moins une fois
```bash
i = 0

loop do
  puts "code exécuté une seule fois"
  break if i == 0 
end
```

## for
La boucle `for` est une structure de contrôle qui permet d’itérer sur une collection (plage de nombres, tableau, etc.) en utilisant une variable temporaire qui prend successivement chaque valeur de cette collection en ordre croissant. 

3 façons d'utiliser `for`:
```bash
fruits = ["pommes", "banane", "orange"]

for fruit in fruits
  puts fruit # affiche chaque fruit
end
```
```bash
for i in 1..10
  puts i # affiche chaque numéro
end
```
```bash
(1..10).each do |i|
  puts i # affiche chaque numéro
end
```