---
title: "Input/output des messages"

---

En Ruby, l’entrée et la sortie de données servent à communiquer avec l’utilisateur. Pour afficher un message à l’écran, on utilise surtout puts et print. La commande puts affiche un message et retourne automatiquement à la ligne suivante, tandis que print affiche un message sans retour à la ligne. Il y a également p qui affiche la valeur exacte d’une valeur. Par exemple, puts "Bonjour" affiche le message sur une ligne (Bonjour), p affichera la même chose avec la valeur exacte ("Bonjour") et print "Bonjour" laisse le curseur sur la même ligne.

```bash
print "Hello World"
```
Output

```bash
Hello World
```

Pour demander une information à l’utilisateur, on utilise gets, qui permet de lire ce que la personne tape au clavier. 

```bash 

Puts “Quel est ton prénom?” 

Prenom = gets.chomp 

Puts “Bonjour, #{prenom}!” 

``` 

- puts affiche un message à l’écran. 

- gets permet à l’utilisateur d’entrer du texte au clavier. 

- .chomp enlève le saut de ligne automatique. 

- La dernière ligne affiche un message personnalisé avec le prénom entré. 

Output

```bash
Quel est ton prénom ?
John
Bonjour, John !
```

