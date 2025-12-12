+++
title = "Gestion de Contacts"
weight = 1
+++

## Énoncé

Vous devez créer un programme de gestion de contacts en Ruby. Ce programme doit permettre à l'utilisateur d'ajouter, afficher, modifier et supprimer des contacts. Chaque contact possède un nom et un numéro de téléphone.

### Objectifs pédagogiques

- Utiliser les **classes et les objets** en Ruby
- Manipuler les **variables d'instance** et les **accesseurs** (`attr_accessor`)
- Travailler avec les **collections** (tableaux)
- Implémenter un **menu interactif** avec conditions et boucles
- Pratiquer l'**encapsulation** et la modularité du code

**Durée estimée** : 1 heure

---

## Instructions

### Partie 1 : Créer la classe `Contact`

Créez une classe `Contact` avec :
- Un constructeur qui accepte un nom et un numéro de téléphone
- Des accesseurs pour lire et modifier le nom et le téléphone
- Une méthode `to_s` qui retourne une représentation lisible du contact

### Partie 2 : Créer la classe `Carnet`

Créez une classe `Carnet` qui gère une collection de contacts :
- Une variable d'instance `@contacts` (tableau vide au départ)
- Une méthode `ajouter(contact)` pour ajouter un contact
- Une méthode `afficher_tous` pour lister tous les contacts
- Une méthode `chercher(nom)` pour trouver un contact par son nom
- Une méthode `supprimer(nom)` pour supprimer un contact
- Une méthode `modifier(nom, nouveau_nom, nouveau_telephone)` pour modifier un contact

### Partie 3 : Implémenter le menu principal

Créez une fonction `menu_principal` qui affiche un menu interactif permettant :

1. Ajouter un contact
2. Afficher tous les contacts
3. Chercher un contact
4. Modifier un contact
5. Supprimer un contact
6. Quitter

Le programme doit fonctionner en boucle jusqu'à ce que l'utilisateur choisisse de quitter.

---

## Indices

{{% expand title="💡 Cliquez pour voir les indices" %}}

- Utilisez `attr_accessor` pour simplifier vos accesseurs
- La méthode `find` du tableau cherche le premier élément qui satisfait une condition
- Utilisez `downcase` pour ignorer la casse lors de la recherche
- Utilisez une boucle `loop do ... end` pour le menu principal
- Validez que les entrées ne sont pas vides avant de créer un contact

{{% /expand %}}

---

## Corrigé

{{% expand title="✅ Cliquez pour voir le corrigé complet" %}}

> [!warning] Solution
> Essayez de résoudre l'exercice par vous-même avant de consulter le corrigé !

```ruby
# Classe représentant un contact individuel
class Contact
  attr_accessor :nom, :telephone

  def initialize(nom, telephone)
    @nom = nom
    @telephone = telephone
  end

  def to_s
    "#{@nom} - #{@telephone}"
  end
end

# Classe représentant le carnet de contacts
class Carnet
  def initialize
    @contacts = []
  end

  # Ajoute un nouveau contact au carnet
  def ajouter(contact)
    @contacts << contact
  end

  # Affiche tous les contacts
  def afficher_tous
    if @contacts.empty?
      puts "\n⚠️  Le carnet est vide."
    else
      puts "\n📋 === LISTE DES CONTACTS ==="
      @contacts.each_with_index do |contact, index|
        puts "#{index + 1}. #{contact}"
      end
    end
  end

  # Cherche un contact par son nom
  def chercher(nom)
    contact_trouve = @contacts.find { |c| c.nom.downcase == nom.downcase }
    
    if contact_trouve
      puts "\n✅ Contact trouvé : #{contact_trouve}"
    else
      puts "\n❌ Contact '#{nom}' non trouvé."
    end
    
    contact_trouve
  end

  # Supprime un contact par son nom
  def supprimer(nom)
    contact = @contacts.find { |c| c.nom.downcase == nom.downcase }
    
    if contact
      @contacts.delete(contact)
      puts "\n✅ Contact '#{nom}' supprimé avec succès."
    else
      puts "\n❌ Contact '#{nom}' non trouvé."
    end
  end

  # Modifie un contact existant
  def modifier(nom, nouveau_nom, nouveau_telephone)
    contact = @contacts.find { |c| c.nom.downcase == nom.downcase }
    
    if contact
      contact.nom = nouveau_nom
      contact.telephone = nouveau_telephone
      puts "\n✅ Contact '#{nom}' modifié avec succès."
    else
      puts "\n❌ Contact '#{nom}' non trouvé."
    end
  end
end

# Fonction pour afficher le menu et gérer les interactions
def menu_principal
  carnet = Carnet.new

  loop do
    puts "\n" + "="*40
    puts "📱 GESTIONNAIRE DE CONTACTS"
    puts "="*40
    puts "1. ➕ Ajouter un contact"
    puts "2. 📋 Afficher tous les contacts"
    puts "3. 🔍 Chercher un contact"
    puts "4. ✏️  Modifier un contact"
    puts "5. 🗑️  Supprimer un contact"
    puts "6. ❌ Quitter"
    puts "="*40
    print "Choisissez une option (1-6) : "
    
    choix = gets.chomp.to_i

    case choix
    when 1
      # Ajouter un contact
      print "\nNom du contact : "
      nom = gets.chomp
      
      print "Numéro de téléphone : "
      telephone = gets.chomp
      
      if nom.empty? || telephone.empty?
        puts "❌ Erreur : Le nom et le téléphone ne peuvent pas être vides."
      else
        contact = Contact.new(nom, telephone)
        carnet.ajouter(contact)
        puts "✅ Contact '#{nom}' ajouté avec succès."
      end

    when 2
      # Afficher tous les contacts
      carnet.afficher_tous

    when 3
      # Chercher un contact
      print "\nNom du contact à chercher : "
      nom = gets.chomp
      carnet.chercher(nom)

    when 4
      # Modifier un contact
      print "\nNom du contact à modifier : "
      nom = gets.chomp
      
      print "Nouveau nom : "
      nouveau_nom = gets.chomp
      
      print "Nouveau numéro de téléphone : "
      nouveau_telephone = gets.chomp
      
      if nouveau_nom.empty? || nouveau_telephone.empty?
        puts "❌ Erreur : Le nom et le téléphone ne peuvent pas être vides."
      else
        carnet.modifier(nom, nouveau_nom, nouveau_telephone)
      end

    when 5
      # Supprimer un contact
      print "\nNom du contact à supprimer : "
      nom = gets.chomp
      carnet.supprimer(nom)

    when 6
      # Quitter
      puts "\n👋 Au revoir !"
      break

    else
      puts "\n❌ Option invalide. Veuillez choisir entre 1 et 6."
    end
  end
end

# Lancer le programme
menu_principal
```

### Résumé des concepts clés

| Concept | Explication |
|---------|-------------|
| **Classes** | `Contact` et `Carnet` modélisent les entités du programme |
| **`attr_accessor`** | Permet la lecture et modification des attributs d'instance |
| **Tableau** | Stocke la collection de contacts avec `@contacts` |
| **Boucles** | La méthode `loop do ... end` permet l'interaction répétée |
| **Conditions** | `case/when` gère les différentes options du menu |
| **Méthodes utiles** | `.find`, `.delete`, `.each_with_index` pour manipuler les collections |
| **Encapsulation** | Les détails internes sont cachés, seules les méthodes publiques sont utilisées |

### Comment exécuter le programme

Enregistrez le code dans un fichier `contact_manager.rb`, puis exécutez-le :

```bash
ruby contact_manager.rb
```

{{% /expand %}}