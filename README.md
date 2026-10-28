# CloverProject : Donjon Quest

Jeu d'aventure 2D pour PC dans lequel le joueur explore un donjon, accomplit des quêtes et recrute des compagnons et collectionne des armes au fil de sa progression. Le projet est développé à deux dans le cadre d'un parcours d'apprentissage de Godot.

> **État du projet :** phase de game design. Le principe général est posé (donjon, quêtes, compagnons). Les choix listés dans _Points à trancher_ restent ouverts.

## Concept

Au début, le joueur incarne un personnage seul. En explorant le donjon et en accomplissant des quêtes, il gagne de l'expérience et débloque des **compagnons** : des personnages qui le suivent et l'aident ainsi que des armes .

Chaque compagnon apporte une capacité propre utilisable dans le donjon, par exemple franchir un obstacle, atteindre une zone en hauteur ou repérer un passage caché _(exemples à valider)_. Les compagnons servent ainsi à la fois de récompense et de clé pour progresser.

La version minimale du jeu doit permettre de :

- se déplacer dans les salles du donjon et éviter murs et obstacles ;
- affronter des ennemis avec un combat simple ;
- accepter et accomplir des quêtes ;
- gagner de l'expérience et monter de niveau ;
- débloquer au moins un compagnon qui suit le joueur ;
- utiliser la capacité d'un compagnon pour accéder à une nouvelle zone ;
- terminer le donjon en accomplissant la quête finale.

## Informations du projet

| Élément          | Choix                                     |
| ---------------- | ----------------------------------------- |
| Plateforme cible | PC (Windows et Linux)                     |
| Moteur           | Godot 4.7                                 |
| Rendu            | Compatibilité                             |
| Langage          | GDScript                                  |
| Genre            | Aventure 2D, donjon, quêtes et compagnons |
| Versionnement    | Git et GitHub                             |
| Équipe           | 2 personnes                               |
| Planification    | Par sprints, sans date limite             |

Le code est écrit par les membres de l'équipe. Les assets et ressources externes utilisés dans le jeu seront crédités dans ce README avant la publication.

## Installation et lancement

### Prérequis

- [Godot 4](https://godotengine.org/download/) en version standard (pas `.NET`) ;
- Git.

### Récupérer le projet

```bash
git clone <URL_DU_DEPOT>
cd cloverProject/city-discovery
```

Ouvrir ensuite le dossier `city-discovery/` dans Godot. Utiliser **Play Project** (`F5`) pour lancer la scène principale, ou **Play Current Scene** (`F6`) pour lancer la scène ouverte.

> Le projet utilise le moteur de rendu **Compatibilité**. Les deux membres de l'équipe doivent utiliser une version comparable de Godot pour éviter les différences de projet.

## Contrôles prévus

Les actions seront configurées dans l'Input Map de Godot afin de prendre en compte les claviers AZERTY et QWERTY.

| Action                                   | Touches prévues            |
| ---------------------------------------- | -------------------------- |
| Déplacement                              | Flèches ou `ZQSD` / `WASD` |
| Attaque                                  | `Espace` ou clic gauche    |
| Interagir (PNJ, coffres, quêtes)         | `E`                        |
| Journal de quêtes                        | `J`                        |
| Changer de compagnon actif _(à valider)_ | `Tab`                      |
| Sprint _(bonus)_                         | `Maj`                      |
| Pause                                    | `Échap`                    |

Les contrôles pourront être ajustés pendant le Sprint 1. La liste définitive sera mise à jour ici dès qu'elle sera validée dans le jeu.

## Équipe et organisation

Le projet est réalisé par deux personnes. Les rôles sont répartis par fonctionnalité et alternés à partir du Sprint 3 afin que chacun travaille sur toutes les parties du jeu.

| Membre     | Responsabilités principales                                              |
| ---------- | ------------------------------------------------------------------------ |
| Personne A | Joueur, combat et ennemis, progression (expérience, niveaux), sauvegarde |
| Personne B | Donjon et salles, compagnons, quêtes et dialogues, interface et menus    |

Cette répartition est indicative : chaque fonctionnalité est relue par l'autre membre avant sa fusion.

## Feuille de route

Il n'y a pas de date limite. Un sprint se termine lorsque son résultat attendu est atteint et validé à deux, puis on passe au suivant.

### Sprint 0 : Préliminaires et game design

- Créer le dépôt GitHub, le projet Godot et la structure des dossiers (`scenes/`, `scripts/`, `assets/`) ;
- configurer l'Input Map pour AZERTY et QWERTY ;
- trancher les points de la section _Points à trancher_ ;
- rédiger le document de conception (boucle de jeu, personnage, compagnons, quêtes).

**Résultat attendu :** dépôt prêt, décisions prises, document de conception validé.

### Sprint 1 : Le socle

- créer la scène du joueur (`CharacterBody2D`) avec déplacement dans quatre directions ;
- construire une salle de test avec `TileMap` et des murs qui bloquent le joueur ;
- ajouter une caméra qui suit le joueur ;
- mettre en place la pause avec `Échap`.

**Résultat attendu :** personnage contrôlable dans une salle avec collisions, pause fonctionnelle.

### Sprint 2 : Le donjon et le combat

- relier plusieurs salles par des transitions entre scènes ;
- créer un ennemi simple qui se déplace et détecte le joueur ;
- ajouter l'attaque du joueur et les dégâts infligés aux ennemis ;
- gérer les points de vie du joueur et l'écran de défaite.

**Résultat attendu :** donjon de plusieurs salles, combat basique, défaite possible.

### Sprint 3 : Quêtes et progression

- définir la structure d'une quête (titre, objectif, récompense) ;
- réaliser une première quête complète, de bout en bout : un PNJ la donne, le joueur l'accomplit, la récompense est accordée ;
- ajouter l'expérience et les niveaux (gagnés sur les ennemis et les quêtes) ;
- ajouter le premier compagnon, qui suit le joueur.

**Résultat attendu :** une quête jouable, une progression visible, un premier compagnon.

### Sprint 4 : Les compagnons

- donner au compagnon une capacité utilisable (par exemple franchir un obstacle) ;
- créer une zone bloquée, accessible uniquement grâce à cette capacité ;
- réaliser le journal de quêtes (touche `J`) ;
- compléter le menu pause (reprendre, options, quitter) ;
- sauvegarder la progression : quêtes, niveau, compagnons débloqués.

**Résultat attendu :** compagnons utiles dans le donjon, journal de quêtes et sauvegarde fonctionnels.

### Sprint 5 : Les finitions

- compléter le donjon : toutes les zones accessibles, toutes les quêtes terminables ;
- ajouter la quête finale et l'écran de victoire ;
- équilibrer les points de vie, les dégâts et l'expérience ;
- ajouter les effets sonores et la musique, puis créditer tous les assets ;
- faire tester le jeu par au moins cinq personnes extérieures et corriger les problèmes relevés ;
- exporter les versions Windows et Linux, puis publier sur itch.io.

**Résultat attendu :** jeu exporté, testé et publié.

**Priorités de coupe.** Si le temps manque, on retire dans cet ordre : le mode coopératif, les quêtes secondaires, les compagnons supplémentaires. Le cœur (un donjon, un personnage, un compagnon, une quête finale) ne doit jamais être coupé.

### Critères de réussite de la version finale

- le joueur peut terminer le donjon et perdre une partie (points de vie à zéro) ;
- toutes les zones du donjon sont accessibles et chaque quête peut être terminée ;
- chaque compagnon débloqué sert à atteindre au moins une zone ;
- le jeu peut être mis en pause et relancé sans erreur ;
- le jeu fonctionne sur une machine ne possédant pas Godot ;
- les assets et ressources tierces sont crédités ;
- au moins cinq personnes extérieures à l'équipe ont testé le jeu ;
- une version Windows et une version Linux sont exportées ;
- le jeu est publié sur itch.io.

## Points à trancher

Ces choix doivent être décidés à deux avant de coder la fonctionnalité concernée. Une fois tranchés, on remplace la question par la réponse ici.

| Sujet                                      | Options possibles                                   |
| ------------------------------------------ | --------------------------------------------------- |
| Chronomètre                                | Oui, pour la pression / Non, exploration libre      |
| Pièces                                     | Monnaie pour acheter des objets / Pas de pièces     |
| Condition de victoire                      | Quête finale seule / Toutes les quêtes principales  |
| Contrôle des compagnons                    | Ils suivent le joueur / Contrôlables à tour de rôle |
| Lien avec l'horloge réelle (ancienne idée) | Abandonné pour le MVP / Bonus                       |
| Mode coopératif                            | Bonus après le MVP / Dès le départ                  |
| Nom du dossier Godot                       | `city-discovery` (actuel) / `dungeon-quest`         |

## Workflow Git et GitHub

1. `main` doit toujours rester fonctionnelle.
2. Créer une branche par fonctionnalité : `feature/nom-court`.
3. Ouvrir une pull request par fonctionnalité.
4. Faire relire la pull request par l'autre membre avant la fusion.
5. Préférer des commits petits et explicites, par exemple : `feat: ajout de la détection des pièces`.
6. Ne jamais modifier la même scène `.tscn` à deux en même temps.
7. Ne jamais versionner le dossier `.godot/`.

Le tableau GitHub Projects suit les colonnes **À faire**, **En cours**, **En revue** et **Fait**.

## Ressources

- [Documentation officielle de Godot](https://docs.godotengine.org/)
- Tutoriel [Your first 2D game](https://docs.godotengine.org/en/stable/getting_started/first_2d_game/)
- Documentation sur `TileMap` et `CharacterBody2D`, pour le donjon et le personnage
- [Kenney](https://kenney.nl/) pour des assets libres (donjon, RPG)
- [jsfxr](https://sfxr.me/) pour générer des effets sonores
- [Audacity](https://www.audacityteam.org/) pour le montage audio
- [itch.io](https://itch.io/) pour la publication

Les licences et crédits précis des ressources utilisées seront ajoutés au fur et à mesure du développement.

## En cas de blocage

1. Lire entièrement le message d'erreur dans la console.
2. Rechercher la classe concernée dans la documentation intégrée de Godot (`F1`).
3. Reproduire le problème dans une petite scène de test.
4. Rechercher le message d'erreur exact en ligne.
5. Si le problème persiste, décrire le comportement attendu, le comportement obtenu et fournir le code concerné pour demander de l'aide.

## Idées bonus

- mode coopératif à deux joueurs, avec les mêmes récompenses ;
- donjons générés aléatoirement ;
- marchand et boutique ;
- système de succès ;
- éditeur de niveau ;
- classement en ligne.
