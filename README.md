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

## Personnages

Quatre personnages principaux — les Quatre Reliques Primordiales.

### Personnage 1 : Astrax

| Élément | Description |
|---|---|
| Bio | Gardien des cités suspendues, porteur de la dernière étincelle d'une tempête ancestrale. Il cherche les fragments du ciel brisé pour sauver les royaumes du vide. |
| Style | Combat agressif et mobile : éclairs, attaques aériennes et mécanismes électriques. |

| État | Nom | Relique | Armes | Pouvoir |
|---|---|---|---|---|
| Forme de base | **Astrax, l'Éclat Foudroyant** | **Cœur Fulminant** : stocke la charge des attaques et esquives. | **Gantelets Conducteurs** : coups rapides électrifiés. | **Impulsion** : éclairs courts, dash foudroyant, activation de portes et rails d'énergie. |
| Mode Héros (Brave) | **Astrax, Brise-Tempête** | **Surcharge** : libère la charge sans vider toute la jauge. | **Lances d'Orage** : moyenne portée et combos aériens. | **Chaîne Céleste** : éclairs rebondissants ; aimantation aux murs et paratonnerres. |
| Mode Élu | **Astrax, Héritier du Firmament** | **Noyau d'Orage** : absorbe tempêtes, pièges et attaques électriques. | **Hallebarde Fulgurante** : arcs électriques au sol. | **Domaine Magnétique** : attire, repousse ou suspend objets et ennemis métalliques. |
| Mode Divin | **Astrax, Souverain des Sept Tonnerres** | **Tempête Vivante** : cyclone de foudre temporaire. | **Trône-Éclair** : arme de foudre modulable. | **Jugement des Cieux** : tempête ciblant les marques ; traverse les gouffres sous forme de foudre. |

#### Compagnon d'Astrax : Voltrik

| Élément | Description |
|---|---|
| Bio | Faucon mécanique réveillé au sommet d'un paratonnerre antique, accordé au Cœur Fulminant. |
| Rôle | Marquage, mobilité aérienne et activation de réseaux électriques éloignés. |

| État | Nom | Relique | Pouvoir |
|---|---|---|---|
| Forme de base | **Voltrik, l'Étincelle Ailée** | **Plume Conductrice** : repère l'énergie proche. | **Marquage Fulgurant** : marque une cible, active un interrupteur et récupère des objets. |
| Mode Héros (Brave) | **Voltrik, Aile de Tonnerre** | **Arc Chargé** : propage la charge. | **Relais d'Orage** : éclairs en chaîne et plané bref pour Astrax. |
| Mode Élu | **Voltrik, Faucon du Firmament** | **Batterie Céleste** : alimente les structures antiques. | **Perchoirs de Foudre** : plates-formes électriques et circuits cachés révélés. |
| Mode Divin | **Voltrik, Avatar de la Tempête** | **Aile du Ciel Brisé** : fusion avec les nuages. | **Vol du Maelström** : monture de foudre pour gouffres géants et plongée destructrice. |

---

### Personnage 2 : Sah-Ra

| Élément | Description |
|---|---|
| Bio | Exploratrice née dans une oasis bâtie autour d'un réacteur solaire ancien. Sa lumière guide les peuples des terres mortes, mais peut devenir destructrice. |
| Style | Polyvalent : lumière à distance, mêlée, protection, soin limité et création de chemins. |

| État | Nom | Relique | Armes | Pouvoir |
|---|---|---|---|---|
| Forme de base | **Sah-Ra, Porteuse de l'Aube** | **Noyau Héliarque** : transforme l'énergie en chaleur, lumière et vie. | **Sceptre de l'Aube** : lame et tirs précis. | **Rayon Vital** : brûle, éclaire, active les cristaux et révèle murs ou inscriptions cachés. |
| Mode Héros (Brave) | **Sah-Ra, Flamme des Sables** | **Fournaise** : sa chaleur augmente avec l'offensive. | **Chakrams Solaires** : disques de lumière. | **Floraison Ardente** : plantes de soin, de contrôle, de pont ou d'échelle. |
| Mode Élu | **Sah-Ra, Cœur du Zénith** | **Petit Soleil** : absorbe une part des dégâts. | **Arc du Zénith** : flèches courbes ou divisées. | **Chemin de Midi** : couloirs de lumière solide, plates-formes et protection contre poison ou froid. |
| Mode Divin | **Sah-Ra, Impératrice de l'Aube Infinie** | **Soleil Renaissance** : énergie vitale à jauge pleine. | **Couronne des Mille Rayons** : lames orbitantes. | **Terre du Premier Jour** : zone de soin et de ralentissement qui réactive la vie et les machines. |

#### Compagnon de Sah-Ra : Nefru

| Élément | Description |
|---|---|
| Bio | Scarabée solaire né autour d'un fragment du Noyau Héliarque, attiré par les lieux où la vie s'est éteinte. |
| Rôle | Lumière, soin, flore utilitaire et restauration de mécanismes. |

| État | Nom | Relique | Pouvoir |
|---|---|---|---|
| Forme de base | **Nefru, le Scarabée Lumineux** | **Scarabée d'Or** : collecte la lumière. | **Lueur Chercheuse** : éclaire et révèle objets cachés ou énergie solaire. |
| Mode Héros (Brave) | **Nefru, Gardien Doré** | **Carapace Protectrice** : condense la lumière. | **Halo Gardien** : bouclier bref et soin léger après esquive parfaite. |
| Mode Élu | **Nefru, Scarabée du Zénith** | **Graine de Midi** : réveille la flore ancienne. | **Jardin Solaire** : plantes-ponts, lianes, pièges ou sources de soin. |
| Mode Divin | **Nefru, Sphinx Ailé de l'Aube** | **Cœur de Renaissance** : lumière réparatrice à grande échelle. | **Éveil des Ruines** : restaure un mécanisme majeur et ouvre une nouvelle région. |

---

### Personnage 3 : Kurojin

| Élément | Description |
|---|---|
| Bio | Ancien éclaireur d'un archipel noyé dans la brume, Kurojin recherche les fragments de sa mémoire et de son âme. |
| Style | Assassin tactique : marques, doubles, infiltration et contrôle de l'obscurité. |

| État | Nom | Relique | Armes | Pouvoir |
|---|---|---|---|---|
| Forme de base | **Kurojin, l'Ombre Errante** | **Cœur du Vide** : recueille l'énergie des cibles marquées et zones obscures. | **Lames Jumelles du Crépuscule** : attaques rapides et contres. | **Pas Obscur** : téléportation entre ombres, extinction de lumières et marque d'ennemi. |
| Mode Héros (Brave) | **Kurojin, Chasseur d'Éclipse** | **Faim Nocturne** : les marques drainent l'énergie ennemie. | **Kusarigamas d'Ombre** : chaînes et lames. | **Double Silencieux** : clone qui répète une attaque, maintient un levier ou distrait les gardiens. |
| Mode Élu | **Kurojin, Gardien du Croissant Noir** | **Lune Absente** : élargit les ombres disponibles. | **Naginata Nocturne** : traînées ralentissantes. | **Royaume Sans Lumière** : zone d'ombre pour échanger avec le double et révéler les passages secrets. |
| Mode Divin | **Kurojin, Prince de l'Éclipse Éternelle** | **Nuit Souveraine** : lien coûteux avec le royaume des ombres. | **Lame de la Lune Éteinte** : brise les barrières magiques. | **Éclipse Éternelle** : furtivité renforcée, doubles chasseurs et accès aux portes d'ombre antiques. |

#### Compagnon de Kurojin : Yami

| Élément | Description |
|---|---|
| Bio | Renard spectral né d'un souvenir perdu de Kurojin, capable de reconnaître les ombres liées à son passé. |
| Rôle | Détection, leurres, portails d'ombre et amplification des marques. |

| État | Nom | Relique | Pouvoir |
|---|---|---|---|
| Forme de base | **Yami, le Renard de Brume** | **Perle de Brume** : capte les traces spirituelles. | **Piste Fantôme** : détecte passages cachés et détourne un ennemi. |
| Mode Héros (Brave) | **Yami, Renard aux Deux Queues** | **Reflet Trompeur** : crée une illusion. | **Leurres Jumeaux** : faux Kurojin pour détourner ennemis, pièges et mécanismes. |
| Mode Élu | **Yami, Kitsune de la Lune Noire** | **Passage Spectral** : relie les zones d'ombre. | **Porte du Renard** : franchit les barrières, vole un bonus ennemi et laisse un portail. |
| Mode Divin | **Yami, Esprit des Neuf Éclipses** | **Couronne des Neuf Lunes** : neuf flammes d'ombre. | **Chasse des Neuf Ombres** : marque les ennemis ; les vaincre prolonge l'Éclipse de Kurojin. |

---

### Personnage 4 : Ketzar

| Élément | Description |
|---|---|
| Bio | Cartographe des cités-montagnes de l'Ouest, Ketzar cherche les lois oubliées du monde. Chaque découverte modifie sa force et sa lecture du terrain. |
| Style | Mobile et analytique : vent, vol, runes et faiblesses ennemies. |

| État | Nom | Relique | Armes | Pouvoir |
|---|---|---|---|---|
| Forme de base | **Ketzar, Voyageur des Vents** | **Spirale Éthérée** : transforme les découvertes en Écailles de Savoir. | **Bâton-Serpent** : bâton flexible prolongé par le vent. | **Souffle Ascendant** : rafales, plané court, courants ascendants et déplacement d'objets légers. |
| Mode Héros (Brave) | **Ketzar, Aile des Ruines** | **Écailles de Savoir** : révèle les faiblesses des ennemis étudiés. | **Fouet des Alizés** : attire, repousse ou désarme. | **Œil du Cartographe** : révèle courants, murs fragiles et traces ; guide les projectiles. |
| Mode Élu | **Ketzar, Maître des Mille Routes** | **Grimoire du Vent** : combine les Écailles pour des effets temporaires. | **Lance du Serpent Céleste** : crée des tornades. | **Porte des Courants** : tunnel de vent vers sommets, zones empoisonnées et mécanismes à rediriger. |
| Mode Divin | **Ketzar, Serpent des Mille Horizons** | **Loi du Ciel** : permet de choisir une règle naturelle à altérer brièvement. | **Corps du Dragon-Vent** : forme de serpent-dragon aérien. | **Décret des Horizons** : modifie gravité, vitesse des projectiles ou direction des vents et ouvre les chemins finaux. |

#### Compagnon de Ketzar : Aru

| Élément | Description |
|---|---|
| Bio | Jeune serpent-plume découvert dans une carte vivante. Il mémorise les routes invisibles révélées par les découvertes de Ketzar. |
| Rôle | Courants d'air, vol, traduction de runes et accès aux sanctuaires célestes. |

| État | Nom | Relique | Pouvoir |
|---|---|---|---|
| Forme de base | **Aru, le Serpenteau des Brises** | **Plume Spirale** : ressent vents, runes et passages oubliés. | **Guide des Courants** : indique les courants, récupère les objets et révèle les prises cachées. |
| Mode Héros (Brave) | **Aru, Plume des Alizés** | **Souffle Porteur** : emmagasine la force des vents découverts. | **Rafale Complice** : repousse ennemis, déplace blocs et prolonge le vol de Ketzar. |
| Mode Élu | **Aru, Oracle des Hautes Routes** | **Mémoire des Ruines** : déchiffre langues et itinéraires anciens. | **Vision de l'Oracle** : traduit symboles, révèle faiblesses des boss et routes vers trésors. |
| Mode Divin | **Aru, Dragon des Horizons** | **Aile du Monde** : fusion temporaire avec la Spirale Éthérée. | **Union des Mille Vents** : fusionne avec Ketzar pour voler librement, créer des tornades et activer les sanctuaires finaux. |

---
### Mondes

#### Mondes 
|Nom | Caractéristique principal |Elements internes | Boss final |Récompenses de fin| 
|---|---|---|---|---|
| **Temple du Dieu Soleil**|  essence solaire| dunes de sables, créatures de lumière, ruines ancestraux,...| Tonatiuh Tyran solaire (ça se meut, ça va en éméttant de la chaleur et de la lumière)| Horloge universelle(permet de connaître exactement le temps et les cycles saisonniers peu importe le monde)
| **

    

### Règle de progression commune

| Ressource | Fonction |
|---|---|
| **Résonance** | Jauge ultime : augmente via combats stylés, zones secrètes, énigmes et Fragments de Relique. |
| **Fragments de Relique** | Déverrouillent les formes Héros, Élu et Divin des personnages. |
| **Noyaux Compagnons** | Cachés dans des zones facultatives ; ils font évoluer les compagnons suivant les quatre mêmes états. |


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
git clone <https://github.com/mnkgesse-stack/cloverProject.git>
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
