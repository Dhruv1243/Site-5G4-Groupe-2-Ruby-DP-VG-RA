---
title: "Lecture et écriture de fichiers en Ruby (FIle I/O)"
---

Ruby offre des outils simples et puissants pour lire, écrire et manipuler des fichiers. Cette fonctionnalité est essentielle pour sauvegarder des données, analyser des informations provenant de fichiers externes ou automatiser différentes tâches. La classe File, intégrée au langage, permet de gérer facilement ces opérations. 

## Lire un fichier :  

La méthode File.read permet de lire l’intégralité du contenu d’un fichier sous forme de chaîne de caractères. 

```bash
contenu = File.read("data.txt")
puts contenu
```
Cette méthode est utile lorsque l'on veut charger tout le texte en mémoire d'un coup

## Écrire dans un fichier :

La méthode File.write permet d’écrire du texte dans un fichier. 
 Si le fichier n’existe pas, il sera créé automatiquement. 
 S’il existe déjà, son contenu sera remplacé. 

```bash
File.write("log.txt", "Bonjour Ruby!")

```
Cela crée le fichier s’il n’existe pas, ou le remplace s’il existe déjà. 

## Lire un fichier ligne par ligne :  

Pour traiter un fichier une ligne à la fois, on utilise File.foreach. 
 Cette approche est idéale pour l’analyse de données ou le traitement de gros fichiers. 

```bash
File.foreach("data.txt") do |ligne|
    puts ligne
end

```

## Ouvrir un fichier avec File.open

La méthode File.open permet d’ouvrir un fichier dans un mode précis (lecture, écriture, ajout, etc.). 
 Utiliser un bloc avec open est recommandé, car Ruby fermera automatiquement le fichier lorsque le bloc se termine. 

```bash
File.open("notes.txt", "w") do |f|
  f.puts "Première ligne"
  f.puts "Deuxième ligne"
end
```

Dans l’exemple ci-dessus : 

- "w" signifie write mode (écriture) 

- f.puts écrit des lignes dans le fichier 

- Le fichier est fermé automatiquement après le bloc 

### Les modes d'ouverture les plus utilisés

| Mode | Description |
|------|-------------|
| `"r"`  | Lire un fichier (lecture seule) |
| `"w"`  | Écrire dans un fichier (écrase le fichier existant) |
| `"a"`  | Ajouter du texte à la fin du fichier |
| `"r+"` | Lire et écrire |
| `"w+"` | Lire et écrire (écrase le fichier existant) |
| `"a+"` | Lire et ajouter |

Voici un exemple complet avec la lecture et écriture


```bash
# Écriture
File.write("infos.txt", "Ruby est puissant !")

# Lecture
contenu = File.read("infos.txt")
puts "Contenu du fichier : #{contenu}"

```

Sortie : 
```bash
Contenu du fichier : Ruby est puissant !

```