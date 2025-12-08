+++
title = "Exercice : Menu interactif en Ruby"
+++

## Contexte

Dans cet exercice, tu vas créer un menu interactif pour un programme de gestion de tâches. Ce menu permettra à l'utilisateur de choisir différentes actions à effectuer sur une liste de tâches. L'objectif est de compléter le code afin de rendre le menu fonctionnel et interactif.

### Objectifs :
- Créer un **menu interactif** avec plusieurs options.
- Utiliser des **boucles** et des **conditions** pour gérer l'interaction avec l'utilisateur.
- Compléter des **méthodes** pour ajouter, afficher, marquer et supprimer des tâches.

---

## 1. Menu interactif

Tu vas maintenant implémenter le menu interactif. Ce menu permettra à l'utilisateur de :

1. Ajouter une tâche.
2. Afficher toutes les tâches.
3. Marquer une tâche comme terminée.
4. Supprimer une tâche.
5. Quitter.

### Exemple de structure du menu interactif :

```ruby
def menu
  liste = ListeDeTaches.new  # Assure-toi que la classe ListeDeTaches est déjà créée

  loop do
    puts "\n=== Menu ==="
    puts "1. Ajouter une tâche"
    puts "2. Afficher toutes les tâches"
    puts "3. Marquer une tâche comme terminée"
    puts "4. Supprimer une tâche"
    puts "5. Quitter"
    print "Choisissez une option : "
    choix = gets.chomp.to_i

    case choix
    when 1
      # À compléter : ajouter une tâche
      print "Nom de la tâche : "
      nom = gets.chomp
      liste.ajouter_tache(nom)
      puts "Tâche ajoutée !"
    when 2
      # À compléter : afficher les tâches
      liste.afficher_taches
    when 3
      # À compléter : marquer une tâche comme terminée
      print "Numéro de la tâche à marquer comme terminée : "
      index = gets.chomp.to_i
      liste.marquer_terminer(index)
    when 4
      # À compléter : supprimer une tâche
      print "Numéro de la tâche à supprimer : "
      index = gets.chomp.to_i
      liste.supprimer_tache(index)
    when 5
      # Quitter
      puts "Au revoir !"
      break
    else
      puts "Option invalide. Réessayez."
    end
  end
end
```

<details>
  <summary style="cursor: pointer;"><strong>Corrigé</strong></summary>

  ```ruby
  # Classe représentant une tâche
class Tache
  attr_accessor :nom, :terminee

  def initialize(nom)
    @nom = nom
    @terminee = false
  end

  def marquer_terminer
    @terminee = true
  end

  def to_s
    statut = @terminee ? "[X]" : "[ ]"
    "#{statut} #{@nom}"
  end
end

# Classe représentant la liste de tâches
class ListeDeTaches
  def initialize
    @taches = []
  end

  def ajouter_tache(nom)
    @taches << Tache.new(nom)
  end

  def afficher_taches
    if @taches.empty?
      puts "Aucune tâche pour le moment."
    else
      puts "\n=== Liste des tâches ==="
      @taches.each_with_index do |tache, index|
        puts "#{index + 1}. #{tache}"
      end
    end
  end

  def marquer_terminer(index)
    index -= 1
    if index_valide?(index)
      @taches[index].marquer_terminer
      puts "Tâche marquée comme terminée."
    else
      puts "Numéro invalide."
    end
  end

  def supprimer_tache(index)
    index -= 1
    if index_valide?(index)
      tache = @taches.delete_at(index)
      puts "Tâche supprimée : #{tache.nom}"
    else
      puts "Numéro invalide."
    end
  end

  private

  def index_valide?(index)
    index >= 0 && index < @taches.length
  end
end

# MÉTHODE MENU
def menu
  liste = ListeDeTaches.new

  loop do
    puts "\n=== Menu ==="
    puts "1. Ajouter une tâche"
    puts "2. Afficher toutes les tâches"
    puts "3. Marquer une tâche comme terminée"
    puts "4. Supprimer une tâche"
    puts "5. Quitter"
    print "Choisissez une option : "
    choix = gets.chomp.to_i

    case choix
    when 1
      print "Nom de la tâche : "
      nom = gets.chomp
      liste.ajouter_tache(nom)
      puts "Tâche ajoutée !"

    when 2
      liste.afficher_taches

    when 3
      print "Numéro de la tâche à marquer comme terminée : "
      index = gets.chomp.to_i
      liste.marquer_terminer(index)

    when 4
      print "Numéro de la tâche à supprimer : "
      index = gets.chomp.to_i
      liste.supprimer_tache(index)

    when 5
      puts "Au revoir !"
      break

    else
      puts "Option invalide. Réessayez."
    end
  end
end

# Lancer le programme
menu

  ```




</details>