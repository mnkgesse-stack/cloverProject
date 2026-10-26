# Programme du projet : jeu d'exploration de ville et collecte de pièces

**Équipe :** 2 personnes (A et B)
**Cible :** PC
**Stack :** Godot 4 (rendu Compatibilité) + GDScript + Git/GitHub
**Règle d'or :** tout le code est écrit par vous deux. Ce document ne contient que des objectifs, des notions à apprendre et des critères de réussite.
**Sprint : temps relativement indéterminé. À ajuster selon l'avancement du projet**

---

## Vue d'ensemble

| Phase | Objectif | Livrable |
|---|---|---|---|
| Semaine 0 | Préliminaires et game design | Dépôt prêt + document de conception |
| Sprint 1 | Le socle | Un personnage qui se déplace dans une mini-ville |
| Sprint 2 | La boucle de jeu | Collecter des pièces, score, victoire |
| Sprint 3 | La ville | Vraie carte avec quartiers |
| Sprint 4 | Le gameplay riche | Timer, obstacles, menus, mini-carte |
| Sprint 5 | Les finitions | Jeu complet, exporté et publié |

---

## Semaine 0 : Préliminaires

### Objectifs
- Avoir le même environnement de travail chez vous deux.
- Savoir précisément quel jeu vous construisez.

### Tâches communes
- [ ] Installer Godot 4 (version standard, pas .NET) chacun de son côté.
- [ ] Suivre en entier le tutoriel officiel **« Your first 2D game »** (docs.godotengine.org, section Getting started).
- [ ] Créer le dépôt GitHub (privé ou public) et s'inviter mutuellement comme collaborateurs.
- [ ] Créer le projet Godot (moteur de rendu **Compatibilité**, métadonnées de version **Git**) et faire le premier commit.
- [ ] Rédiger le `README.md` : nom du jeu, concept, contrôles, membres de l'équipe.
- [ ] Créer le tableau **GitHub Projects** (colonnes : À faire / En cours / En revue / Fait) et y mettre les tâches du Sprint 1.
- [ ] Choisir une convention de nommage (par exemple : fichiers en `snake_case`, scènes en `PascalCase` ou l'inverse, mais **la même pour tous**).

### Séance de game design (à faire à deux, sur papier ou document partagé)
Répondez par écrit à ces questions :
1. Quel est le **but** du joueur (collecter X pièces ? battre un chrono ? les deux ?)
2. Comment **gagne-t-on** et comment **perd-on** ?
3. Quelle est la **taille** de la ville (un seul écran ? une grande carte qui défile ?)
4. Quels **obstacles ou dangers** y aura-t-il ?
5. Quelle **ambiance visuelle** (couleurs, style, pixel art ou formes simples) ?
6. Qu'est-ce qui est **indispensable** (MVP) et qu'est-ce qui est **bonus** ?

### Critères de réussite
- Les deux machines peuvent cloner le dépôt et lancer le projet.
- Un document d'une page décrit le jeu (le « GDD » minimal).

---

## Sprint 1 : Le socle

### Objectif
Un personnage contrôlé au clavier qui se déplace dans un petit niveau de test, bute contre les murs, et une caméra qui le suit.

### Notions à apprendre
- Nœuds, scènes, instanciation
- Le nœud de personnage contrôlé (famille `CharacterBody2D`)
- Les corps statiques et les formes de collision (`StaticBody2D`, `CollisionShape2D`)
- La table des entrées (Input Map) dans les paramètres du projet
- La fonction de cycle de vie `_physics_process`
- `Camera2D` et son lissage
- Disposition clavier : pensez à votre clavier **AZERTY** quand vous associez les touches

### Répartition suggérée
| Personne A | Personne B |
|---|---|
| Scène du joueur et déplacement | Niveau de test : murs, sol, bâtiments simples |
| Configuration des entrées | Caméra et réglages de la fenêtre |

### Tâches
- [ ] Créer la scène `Player` avec son visuel (même un simple carré) et sa collision.
- [ ] Configurer les actions de déplacement (haut, bas, gauche, droite) dans la table des entrées.
- [ ] Faire bouger le joueur avec une vitesse réglable depuis l'inspecteur.
- [ ] Créer une scène de niveau avec des murs infranchissables.
- [ ] Ajouter une caméra qui suit le joueur.
- [ ] Définir `Main` comme scène principale.
- [ ] Ouvrir une pull request par fonctionnalité, relue par l'autre.

### Critères de réussite (Definition of Done)
- Le joueur se déplace dans les 4 directions, sans traverser les murs.
- Le déplacement en diagonale n'est pas plus rapide que les autres.
- Le jeu se lance sans erreur dans la console.
- Tout est fusionné dans `main`.

### Pour aller plus loin
- Ajouter une touche de sprint.
- Faire une animation simple selon la direction.

---

## Sprint 2 : La boucle de jeu

### Objectif
Le cœur du jeu : ramasser des pièces, voir son score, gagner.

### Notions à apprendre
- `Area2D` et la détection de chevauchement
- **Les signaux** : émettre, connecter, réagir
- Les groupes de nœuds
- L'interface avec `CanvasLayer` et `Label`
- Instancier une scène par le code (une pièce = une scène)
- Recharger ou changer de scène
- Jouer un son (`AudioStreamPlayer`)

### Répartition suggérée
| Personne A | Personne B |
|---|---|
| Scène `Coin` et détection par le joueur | HUD : affichage du score et du compteur |
| Logique de victoire et de fin de partie | Sons, écran de victoire, bouton rejouer |

### Tâches
- [ ] Créer la scène `Coin` (visuel + zone de détection).
- [ ] Faire disparaître la pièce quand le joueur la touche.
- [ ] Compter les pièces ramassées et afficher le score à l'écran.
- [ ] Placer plusieurs pièces dans le niveau.
- [ ] Détecter la victoire quand toutes les pièces sont collectées.
- [ ] Afficher un écran de victoire avec la possibilité de rejouer.
- [ ] Ajouter un effet sonore à chaque pièce.

### Critères de réussite
- On peut finir une partie du début à la fin.
- Le score est toujours juste, y compris après avoir rejoué.
- Le jeu ne plante pas au redémarrage d'une partie.

### Pour aller plus loin
- Un petit effet visuel quand on ramasse une pièce.
- Des pièces de valeurs différentes.

---

## Sprint 3 : La ville

### Objectif
Remplacer le niveau de test par une vraie ville agréable à explorer.

### Notions à apprendre
- `TileSet` et `TileMapLayer`
- Les couches de collision et les calques physiques
- Le tri en profondeur (Y-sort) pour les objets qui passent devant et derrière
- Les `Marker2D` pour définir des points d'apparition
- Le hasard : `RandomNumberGenerator`
- Organiser une grande scène en sous-scènes

### Répartition suggérée
| Personne A | Personne B |
|---|---|
| Système d'apparition des pièces (positions) | Dessin de la ville avec le TileMap |
| Éventuelle génération aléatoire | Décors, ambiance, quartiers |

### Tâches
- [ ] Choisir ou créer un jeu de tuiles (par exemple un pack libre de droits sur Kenney.nl).
- [ ] Construire un `TileSet` avec ses collisions.
- [ ] Dessiner la ville : routes, bâtiments, parcs, places.
- [ ] Définir plusieurs **quartiers** avec une identité visuelle.
- [ ] Faire apparaître les pièces à des endroits accessibles et variés.
- [ ] Vérifier qu'aucune pièce n'est coincée dans un mur.

### Critères de réussite
- Toute la ville est explorable, sans zone bloquée.
- Aucune pièce n'est inaccessible.
- La caméra reste dans les limites de la carte.

### Pour aller plus loin
- Générer les positions des pièces au hasard à chaque partie.
- Cacher certaines pièces dans des endroits secrets.

---

## Sprint 4 : Le gameplay riche

### Objectif
Rendre le jeu intéressant : de la pression, des obstacles, des menus.

### Notions à apprendre
- `Timer` et compte à rebours
- Mouvement d'ennemis ou de PNJ (patrouille simple avec `Path2D`/`PathFollow2D`, ou navigation avec `NavigationAgent2D`)
- Les **Autoloads** (singletons) pour partager un état global (score, état du jeu)
- La pause du jeu et les modes de traitement des nœuds
- `SubViewport` pour une mini-carte
- Les `Control` et conteneurs pour les menus

### Répartition suggérée
| Personne A | Personne B |
|---|---|
| Timer, ennemis ou obstacles | Menu principal, menu pause |
| Gestion de l'état global (autoload) | Mini-carte et interface |

### Tâches
- [ ] Ajouter un chronomètre et une condition de défaite (temps écoulé).
- [ ] Créer au moins un type d'obstacle ou d'ennemi mobile.
- [ ] Définir ce qui se passe quand le joueur le touche (perte de temps, retour au départ, etc.).
- [ ] Créer des pièces spéciales (bonus de temps, pièce rare).
- [ ] Construire un menu principal (jouer, quitter).
- [ ] Construire un menu pause.
- [ ] Ajouter une mini-carte ou un indicateur de direction vers les pièces restantes.

### Critères de réussite
- On peut gagner **et** perdre.
- Le jeu peut être mis en pause et repris sans bug.
- La difficulté est équilibrée : testez-la sur d'autres personnes.

### Pour aller plus loin
- Plusieurs niveaux ou plusieurs villes.
- Un système de difficulté.

---

## Sprint 5 : Les finitions

### Objectif
Un jeu complet, agréable, stable et publié.

### Notions à apprendre
- Sauvegarde de données (`FileAccess`, `ConfigFile`)
- `AnimatedSprite2D`, `Tween` et particules
- Gestion de la musique et du volume
- Export Godot : modèles d'export, presets
- Publication sur itch.io

### Répartition suggérée
| Personne A | Personne B |
|---|---|
| Sauvegarde du meilleur score, chasse aux bugs | Animations, polish visuel, musique |
| Export Windows/Linux | Page itch.io (description, captures, vidéo) |

### Tâches
- [ ] Sauvegarder et recharger le meilleur score.
- [ ] Ajouter animations et petits effets visuels.
- [ ] Ajouter une musique d'ambiance et un réglage de volume.
- [ ] Faire jouer **au moins 5 personnes** extérieures et noter leurs retours.
- [ ] Corriger les bugs remontés.
- [ ] Exporter le jeu pour Windows et Linux.
- [ ] Publier sur itch.io avec une page de présentation soignée.
- [ ] Mettre à jour le README (installation, contrôles, crédits des assets).

### Critères de réussite
- Le jeu s'installe et se lance sur une machine qui n'a pas Godot.
- Les crédits mentionnent toutes les ressources tierces.
- Une personne extérieure comprend le jeu sans explication.

---

## Rituels de travail

- **Point à deux** : 15 minutes, 2 fois par semaine. Trois questions : qu'est-ce que j'ai fait, qu'est-ce que je fais ensuite, qu'est-ce qui me bloque ?
- **Revue de sprint** : à la fin de chaque sprint, jouez ensemble au jeu et listez ce qui marche et ce qui ne marche pas.
- **Rétrospective** : 10 minutes pour décider d'une chose à améliorer dans votre façon de travailler.
- **Échange de rôles** : à partir du Sprint 3, inversez vos domaines pour que chacune touche à tout.

## Règles Git

1. `main` doit toujours fonctionner.
2. Une branche par fonctionnalité : `feature/nom-court`.
3. Une pull request par fonctionnalité, relue par l'autre avant fusion.
4. Des commits petits, avec un message clair (par exemple : `feat: ajout de la détection des pièces`).
5. **Ne jamais modifier la même scène (`.tscn`) à deux en même temps** : prévenez l'autre avant d'y toucher.
6. Le dossier `.godot/` n'est jamais versionné.

## Que faire quand vous bloquez

1. Lire le message d'erreur en entier dans la console.
2. Chercher la classe concernée dans la doc intégrée (touche F1).
3. Isoler le problème dans une petite scène de test.
4. Chercher le message d'erreur exact en ligne.
5. En dernier recours, me demander : décrivez le comportement attendu, le comportement obtenu, et collez votre code pour que je vous guide, sans que j'écrive la solution à votre place.

## Ressources utiles

- Documentation officielle : docs.godotengine.org
- Assets libres : kenney.nl
- Sons : jsfxr (génération), Audacity (montage)
- Publication : itch.io

## Backlog d'idées bonus

- Mode multijoueur local à deux
- Système de succès
- Météo ou cycle jour/nuit
- Véhicules à conduire dans la ville
- Éditeur de niveau
- Classement en ligne
