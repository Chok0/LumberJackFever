# Lumberjack Fever

**Action-RPG / Exploration en vue top-down 3/4**

> Un bûcheron local pris entre la pression d'une entreprise industrielle et les secrets anciens d'une forêt vivante. Chaque arbre coupé est une décision irréversible qui transforme le monde, alimente la corruption, et rapproche le joueur de la vérité enfouie au cœur de la forêt.

| Statut | Genre | Vue | Style | Durée visée |
|--------|-------|-----|-------|-------------|
| Pré-production | Action-RPG / Exploration | Top-down 3/4 | Pixel art HD (480x270) | 8-15h |

## Jouer le prototype

Ouvrir `index.html` dans un navigateur. Aucune dépendance requise.

ZQSD/flèches : déplacer · Espace : couper / passer les dialogues · C : dash · E : interagir · F : feu de camp · P : planter · R : rituel · I : inventaire · M : musique · TAB : éditeur de tuning · L : session log

## Piliers de design

- **Chaque coup de hache compte** — Irréversible, transforme l'espace.
- **La pression est spatiale** — Devant : forêt dense. Derrière : corruption croissante.
- **Zéro morale explicite** — Conséquences mécaniques, jamais narratives.
- **Lore environnemental** — L'histoire dans le monde, jamais imposée.

## Boucle de gameplay

```
Village/Avant-poste → Enfoncement → Coupe & récolte → Exploration
        ↑                                                    ↓
        └──── Vente & upgrades ←── Retour (survie) ←────────┘
```

**Asymétrie aller/retour** — Le chemin taillé à l'aller n'est plus le même au retour : l'écosystème a réagi aux coupes, la corruption a progressé. Le bois récolté est aussi le carburant du retour (ponts, torches, leurres).

## Système de corruption

La carte elle-même change en fonction des coupes. Pas un compteur abstrait.

| Stade | Visuel | Gameplay |
|-------|--------|----------|
| 1 | Désaturation, sol gris-olive, brume | Avertissement |
| 2 | Champignons noirâtres, mousse morte, mycélium | Faune fuit |
| 3 | Veinures noires connectant les souches | Démons, yeux brillants |

La corruption est aussi une **ressource exploitable** : les essences spirituelles dropent en zone corrompue. Deux façons émergentes de jouer (farming vs purification).

## Ressources

| Ressource | Obtention | Utilisation |
|-----------|-----------|-------------|
| Bois | Coupe (essences variées) | Monnaie, construction, défenses |
| Sève / Résine | Arbres vivants, sans couper | Upgrades, potions, purification |
| Essences spirituelles | Drop corrompus OU zones purifiées | Upgrades avancés, capacités esprits |

## Combat

ARPG a la Zelda. La hache est l'arme unique. Deux lignées (légère / lourde) avec progression par métaux. Les ennemis corrompus sont partiellement végétaux : on les "coupe" plus qu'on ne les combat.

**Le bruit** — Chaque coup active un rayon d'aggro. Fait fuir la faune pacifique, attire les ennemis corrompus, augmente la tension locale.

## Carte et biomes

Village au sud, forêt en éventail vers le nord. Progression par densité et difficulté.

| Biome | Ambiance | Faune/Ennemis |
|-------|----------|---------------|
| **Lisière** (bouleaux) | Verts tendres, tutoriel naturel | Cerfs, lapins, oiseaux |
| **Tempérée** | Dense, variée | Premiers ennemis, esprits curieux |
| **Ancienne** | Arbres géants, canopée épaisse | Structures impossibles, le Gardien |
| **Primordiale** | Mythique, arbres conscients | Le Cœur, pacte brisé |

Sous-biomes latéraux : **Marécage** (cyprès, bois rares) et **Boréal** (épicéas, lacs gelés).

Les transitions sont matérialisées par des murs d'arbres nécessitant un niveau de hache minimum.

## Transport — deux réseaux, un axe moral *(implémenté)*

L'axe moral est de l'infrastructure : chaque camp a son réseau de déplacement rapide.

| Réseau | Déblocage | Avantage | Coût caché |
|--------|-----------|----------|------------|
| **Navettes de l'Entreprise** | Zone suffisamment déboisée → front de taille + dépôt village | TP village ↔ fronts, rachat du bois sur place (70%) | Chaque trajet nourrit la Destruction ; les fronts attirent la corruption |
| **Passages racinaires** | Toucher un arbre sacré enregistre un nœud | TP gratuit entre nœuds découverts (l'Arbre-Chant planté compte) | **Détruits à jamais si l'arbre est coupé** |

Autres raccourcis : **rivières** (radeau/pont via le Castor), **souches-sentier** (+35% de vitesse sur les tuiles coupées — le chemin taillé à l'aller est l'autoroute du retour, jusqu'à la repousse).

Événements aux fronts de taille : les ouvriers de l'Entreprise se font attaquer par la forêt corrompue — les sauver (90 s) rapporte de l'or, échouer inquiète le village.

## Nuit *(implémenté)*

La nuit doit être un choix, pas une panne d'écran.

- **Pleine lune permanente** — silhouettes lisibles ; torche et lanterne achètent le détail, la couleur et la sécurité (voir venir les loups), jamais le droit de jouer.
- **Feu de camp** (F, 4 bûches) — lumière, les loups n'approchent pas des flammes, sommeil sur place jusqu'à l'aube. S'éteint au matin. Le bois est le carburant du retour.
- **La nuit paie** — fleurs lunaires (+1 essence spirituelle) écloses à la nuit tombée, arbres sacrés luminescents. Sortir de nuit est une opportunité, pas une taxe.
- **Loups nocturnes** — meutes, yeux brillants dans le noir, fuient à l'aube.

## Narratif

Les ancêtres ont fait pareil. Le joueur est l'erreur historique. Seul à pouvoir briser le cycle.

**L'Entreprise** — Émissaire amical et ambigu au village. Quotas, deals, prêts. Dépendance croissante.

**Trois fins** : Industrie (victoire amère), Sacrifice (régénération), Fin cachée (exploration complète requise).

## Structure en actes

1. **La Lisière** — L'Entreprise arrive. Tutoriel/contrats. Pas de corruption.
2. **L'Enfoncement** — Quotas. Corruption apparaît. Premier arbre majeur.
3. **La Révélation** — Forêt ancienne. Cycle révélé. Tournant.
4. **Le Cœur** — Forêt primordiale. Choix d'alliance.

## Progression

- **Haches** — Chaque niveau change la *capacité*, pas seulement les chiffres *(implémenté)* : Niv.2 percée (frappe l'arbre derrière), Niv.3 brise les rochers, Niv.4 chute en chaîne. Hache Légendaire (Niv.5) via la quête Théodore/Luthier
- **Durabilité** — Réparation au forgeron, force l'arbitrage exploration/retour
- **Village** — Forgeron, chamane, cartographe, taverne… Les PNJ arrivent progressivement (docteur, luthier, anthropologue) et **jugent le joueur** : dialogues branchés sur les axes moraux cachés — froideur envers le destructeur, chaleur envers le restaurateur, Aldric inversé *(implémenté)*
- **Totems de protection** *(implémenté)* — Chamane, 20 bois + 5 sève (max 3) : refoulent la corruption autour du village et rassurent les villageois
- **Regrow** — Certaines essences repoussent (noisetier, aulne, bouleau). Les essences nobles (chêne, séquoia) ne repoussent jamais. Les arbres plantés (graines du Jardinier) repoussent en un cycle

## Exploration — points d'intérêt *(implémenté, à densifier)*

La forêt doit toujours tirer le joueur un écran plus loin.

- **Camps du grand-père** (3, étagés en profondeur) — arc narratif en 3 chapitres (la Compagnie Von Brandt, la mousse noire, la hache brisée) + récompenses uniques. Raccord avec la quête de la Hache Légendaire
- **Ruines anciennes** (4) — lore des ancêtres (ils ont coupé, puis fui), fouille unique
- **Rythme** — la santé de grand-mère décline par cycle jour/nuit, pas en temps réel : explorer lentement n'est pas puni
- *À venir : caches, clairières secrètes accessibles uniquement sans couper, accroches visuelles en bord d'écran*

## Prototype actuel

Périmètre : un seul biome (lisière), une run aller-retour complète.

**Critères de succès :**
- Le joueur hésite avant de couper un arbre
- Le retour est différent de l'aller
- La corruption est lisible sans explication
- Le joueur a envie de relancer une run

## Structure du repo

```
index.html                      — Jeu (fichier unique, ouvrir dans un navigateur)
spriteLib_roster_complete.html  — Référence sprites ennemis (à intégrer)
README.md                       — Ce fichier
```

## Références

- Boucle core : SteamWorld Dig (descendre, récolter, remonter, upgrader)
- Ambiance : Don't Starve (survie, folie comme ressource)
- Combat : Zelda ARPG
- Pixel art : Eastward, Hyper Light Drifter, CrossCode

---

*Game Design Document v0.6 — Juillet 2026 — Adrien (solo dev)*
*(v0.6 : réseaux de transport moraux, rework nuit/feu de camp, POI d'exploration, capacités de hache, dialogues moraux, totems)*
