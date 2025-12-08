---
title: "Les variables"
---

## Les variables locales (local variables):  

Les variables locales en Ruby doivent toujours commencer par une lettre minuscule ou un souligné (_). Elles sont accessibles uniquement à l’intérieur du bloc, de la méthode ou du contexte dans lequel elles ont été déclarées. En d’autres termes, leur portée est limitée et elles ne peuvent pas être utilisées en dehors de cette zone. 

```bash
color = "green"
_person = "Shannon"
```

## Les variables d’instance (instance variables):  

Les variables d’instances commence avec un symbole @. Les variables d’instance sont des variables qui appartiennent  a un object. 

```bash
class Personne
   def initialize(nom, age)
     @nom = age  #variable d'instance
     @age = age  #variable d'instance
   end
end
```
Ici, chaque objet Personne aura ses propres valeurs pour @nom et @age. 

 

## Les variables de classes (class variables):  

Les variables de classe commencent par le symbole @@. Elles sont partagées entre toutes les instances d’une même classe ainsi qu’entre ses classes dérivées. Cela signifie que si une variable de classe est modifiée par un objet, la modification est visible par tous les autres objets de cette classe. Elles doivent être initialisées avant d’être utilisées, généralement dans la définition de la classe. 

```bash
class Personne
  @@compteur = 0   # variable de classe

  def initialize
    @@compteur += 1
  end

  def self.total
    @@compteur
  end
end

p1 = Personne.new
p2 = Personne.new

puts Personne.total   # => 2

```
Ici, @@compteur est partagé par tous les objets de la classe Personne. 

 

## Les variables globales (global variables) :  

Les variables globales commencent par le symbole $. Comme leur nom l’indique, elles sont accessibles depuis n’importe quel endroit du programme : à l’intérieur des méthodes, des classes, des modules ou même en dehors de ceux-ci. Leur portée est donc totalement globale. Cependant, leur utilisation est généralement déconseillée, car elles peuvent rendre le code plus difficile à maintenir ou à déboguer. 

```bash
$compteur = 0   # variable globale

class Test
  def incrementer
    $compteur += 1
  end
end

t = Test.new
t.incrementer

puts $compteur   # => 1


```