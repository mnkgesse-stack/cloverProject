# CloverProject - City Discovery

Jeu d'exploration en 2D dans lequel le joueur parcourt une ville fictive pour
collecter des pièces. Le projet est développé progressivement dans le cadre
d'un parcours d'apprentissage de Godot.

> **État du projet :** préparation du socle. Le projet Godot est initialisé ;
> le déplacement, la ville et la boucle de collecte restent à développer.

## Concept

Le joueur explore une ville avec une horlogerie du monde réel composée de plusieurs quartiers et/ou niveaux et ramasse toutes
les pièces avant la fin du temps imparti. La version minimale du jeu doit
permettre de :

- se déplacer librement dans une ville ou un donjon(pas encore fixé);
- éviter les murs et les obstacles ;
- affronter des ennemis;
- collecter des pièces et suivre son score ;
- gagner lorsque toutes les pièces sont récupérées ;
- perdre lorsque le chronomètre arrive à zéro;
- récupérer des récompenses spéciales en fonction des ennemis;
- synchronisation de l'horlogerie du monde et du monde réel(pas encore fixé);
- possibilités de mener des explorations des équipes par équipe de maximum de 2 personnes mais les récompenses ne changeront pas.


## Informations du projet

| Élément | Choix |
|---|---|
| Plateforme cible | PC (Windows et Linux) |
| Moteur | Godot 4.7 |
| Rendu | Compatibilité |
| Langage | GDScript |
| Versionnement | Git et GitHub |
| Équipe | 2 personnes |
| Rythme conseillé | 1 sprint de 2 semaines |

Le code est écrit par les membres de l'équipe. Les assets et ressources
externes utilisés dans le jeu seront crédités dans ce README avant la
publication.

## Installation et lancement

### Prérequis

- [Godot 4](https://godotengine.org/download/) en version standard (pas
  `.NET`) ;
- Git.

### Récupérer le projet

```bash
git clone <URL_DU_DEPOT>
cd cloverProject/city-discovery
```

Ouvrir ensuite le dossier `city-discovery/` dans Godot. Utiliser **Play
Project** (`F5`) pour lancer la scène principale, ou **Play Current Scene**
(`F6`) pour lancer la scène ouverte.

> Le projet utilise le moteur de rendu **Compatibilité**. Les deux membres de
> l'équipe doivent utiliser une version comparable de Godot pour éviter les
> différences de projet.

## Contrôles prévus

Les actions seront configurées dans l'Input Map de Godot afin de prendre en
compte les claviers AZERTY et QWERTY.

| Action | Touches prévues |
|---|---|
| Déplacement | Flèches ou `ZQSD` / `WASD` |
| Sprint (bonus) | `Shift` |
| Pause | `Échap` |

Les contrôles pourront être ajustés pendant le Sprint 1. La liste définitive
sera mise à jour ici dès qu'elle sera validée dans le jeu.

## Équipe et organisation

Le projet est réalisé par deux personnes. Les rôles sont répartis par
fonctionnalité et alternés à partir du Sprint 3 afin que chacun travaille sur
toutes les parties du jeu.

| Membre | Responsabilités principales |
|---|---|
| Personne A | Joueur et déplacement, pièces, logique de jeu, timer et sauvegarde |
| Personne B | Niveaux et ville, caméra, interface, menus et polish visuel |

Cette répartition est indicative : chaque fonctionnalité est relue par l'autre
membre avant sa fusion.

## Feuille de route

| Phase | Objectif | Résultat attendu |
|---|---|---|
| Semaine 0 | Préliminaires et game design | Dépôt prêt et document de conception |
| Sprint 1 | Le socle | Personnage contrôlable dans une mini-ville avec collisions |
| Sprint 2 | La boucle de jeu | Pièces, score et écran de victoire |
| Sprint 3 | La ville | Carte complète avec routes, bâtiments et quartiers |
| Sprint 4 | Le gameplay riche | Chronomètre, obstacles, menus et mini-carte |
| Sprint 5 | Les finitions | Jeu exporté, testé et publié |

### Critères de réussite de la version finale

- le joueur peut gagner et perdre une partie ;
- la ville est entièrement explorable et aucune pièce n'est inaccessible ;
- le jeu peut être mis en pause et relancé sans erreur ;
- le jeu fonctionne sur une machine ne possédant pas Godot ;
- les assets et ressources tierces sont crédités ;
- au moins cinq personnes extérieures à l'équipe ont testé le jeu ;
- une version Windows et une version Linux sont exportées ;
- le jeu est publié sur itch.io.

## Workflow Git et GitHub

1. `main` doit toujours rester fonctionnelle.
2. Créer une branche par fonctionnalité :
   `feature/nom-court`.
3. Ouvrir une pull request par fonctionnalité.
4. Faire relire la pull request par l'autre membre avant la fusion.
5. Préférer des commits petits et explicites, par exemple :
   `feat: ajout de la détection des pièces`.
6. Ne jamais modifier la même scène `.tscn` à deux en même temps.
7. Ne jamais versionner le dossier `.godot/`.

Le tableau GitHub Projects suit les colonnes **À faire**, **En cours**,
**En revue** et **Fait**.

## Ressources

- [Documentation officielle de Godot](https://docs.godotengine.org/)
- Tutoriel [Your first 2D game](https://docs.godotengine.org/en/stable/getting_started/first_2d_game/)
- [Kenney](https://kenney.nl/) pour des assets libres
- [jsfxr](https://sfxr.me/) pour générer des effets sonores
- [Audacity](https://www.audacityteam.org/) pour le montage audio
- [itch.io](https://itch.io/) pour la publication

Les licences et crédits précis des ressources utilisées seront ajoutés au fur
et à mesure du développement.

## En cas de blocage

1. Lire entièrement le message d'erreur dans la console.
2. Rechercher la classe concernée dans la documentation intégrée de Godot
   (`F1`).
3. Reproduire le problème dans une petite scène de test.
4. Rechercher le message d'erreur exact en ligne.
5. Si le problème persiste, décrire le comportement attendu, le comportement
   obtenu et fournir le code concerné pour demander de l'aide.

## Idées bonus
- système de succès ;
- météo ou cycle jour/nuit ;
- véhicules à conduire ;
- éditeur de niveau ;
- classement en ligne.
