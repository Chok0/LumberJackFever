# Lumberjack Fever

**Action-RPG / Exploration en vue top-down 3/4**

> Un bûcheron local pris entre la pression d'une entreprise industrielle et les secrets anciens d'une forêt vivante. Chaque arbre coupé est une décision irréversible qui transforme le monde, alimente la corruption, et rapproche le joueur de la vérité enfouie au cœur de la forêt.

| Statut | Genre | Vue | Style | Durée visée |
|--------|-------|-----|-------|-------------|
| Pré-production | Action-RPG / Exploration | Top-down 3/4 | Pixel art HD (480x270) | 8-15h |

## Jouer le prototype

Ouvrir `index.html` dans un navigateur. Aucune dépendance requise.

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

## Raccourcis

| Type | Avantage | Trade-off |
|------|----------|-----------|
| Rivières | Transport rapide | Sens unique, cargaison limitée |
| Chemins de crête | Au-dessus de la corruption | Exposés (vent, esprits) |
| Passages racinaires | Protégés, sous arbres géants | **Détruits si l'arbre est coupé** |

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

- **Haches** — Deux lignées (légère/lourde), progression par métaux, tronçonneuse ultime
- **Durabilité** — Réparation au forgeron, force l'arbitrage exploration/retour
- **Village** — Forgeron, herboriste/chamane, cartographe. Évolue visuellement selon le style de jeu
- **Regrow** — Certaines essences repoussent (noisetier, aulne, bouleau). Les essences nobles (chêne, séquoia) ne repoussent jamais

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

*Game Design Document v0.5 — Mars 2026 — Adrien (solo dev)*
