---
title: "Les classes et les objets en Ruby "
---

Ruby est un langage parfaitement adapté à la programmation orientée objet, car il supporte les principes essentiels comme l’encapsulation, l’héritage, le polymorphisme et l’abstraction. En POO, une classe sert de modèle, tandis qu’un objet est une instance concrète de cette classe. Par exemple, Animal pourrait être une classe, et des objets comme mammifère ou oiseau représenteraient des instances de cette classe. Ruby utilise ce modèle pour organiser le code de manière claire, modulaire et réutilisable. 


Définir une classe en Ruby. 

En Ruby, créer une classe et des objets est très simple. Il suffit d’utiliser le mot-clé class suivi du nom de la classe. Par convention, le nom d’une classe commence toujours par une lettre majuscule. À l’intérieur, on peut ensuite définir des méthodes et des attributs. 

Voici un exemple pour la syntaxe :  

```bash
class Class_name

end

```
Une classe en Ruby doit toujours se terminer par le mot-clé end. Tout ce qui définit la classe — ses attributs, ses méthodes et l’ensemble de sa logique interne — se trouve entre le mot-clé class et end. 

Voici un exemple :  


```bash
#class name is Animal
class Animal

# class variables

@@type_of_animal = 4
@@no_of_animal = 3
end

```

## Création d’un objet avec la méthode new 

Les classes et les objets sont des éléments essentiels en Ruby. Une seule classe peut servir de modèle pour créer un grand nombre d’objets différents. En Ruby, la création d’un objet se fait simplement à l’aide de la méthode new, qui instancie la classe et retourne un nouvel objet basé sur celle-ci. 

Voici la syntaxe :  

```bash
object_name = Class_name.new

```
Voici un exemple : 

```bash
# class name is box

class Box

# class variable
@@No_of_color = 3
 end

# Two objects of Box classes
sbox = Box.new
nbox = Box.new

```
Ici Box est le nom de la classe et No_of_color est la variable de la classe, sbox et nbox sont les deux objets de la classe box. On utilise “=” suivi par le nom du classe, l’opérateur ‘ . ’ et la méthode new. 