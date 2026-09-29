# GW2 Clean & Sharp – ReShade preset for Guild Wars 2

A lightweight, gameplay-oriented preset focused on **sharpness and minimal aliasing**, not on color grading.
It keeps GW2's art style intact and mostly cleans up jagged edges and shimmering in motion.

**Made for:** 2560 × 1440, in-game interface size "Normal". Works well with Lossless Scaling frame generation.

## What it does

| Order | Effect | Role |
|---|---|---|
| 1 | UIMask_Top | Saves the HUD before any processing |
| 2 | iMMERSE: MXAO | Subtle contact shadows on top of the in-game AO |
| 3 | iMMERSE: Anti Aliasing (SMAA) | Catches edges the in-game SMAA misses |
| 4 | Zenteon: Motion | Motion vectors for the temporal pass |
| 5 | Zenteon: ATA (BETA) | Reduces shimmering in motion (foliage, armor, thin lines) |
| 6 | iMMERSE: Sharpen | Depth-aware sharpening that leaves silhouettes alone |
| 7 | UIMask_Bottom | Restores a crisp, untouched HUD |

## Requirements

- **ReShade with full add-on support** (latest version from reshade.me)
- Effect packages (select them in the ReShade installer):
  - **iMMERSE** by Marty McFly (MXAO, SMAA, Sharpen)
  - **ZenteonFX** by Zenteon (Motion, ATA)
  - **Standard effects** by crosire (UIMask)

## Installation

1. Extract this archive **into your Guild Wars 2 folder** (e.g. `C:\Program Files\Guild Wars 2`).
   The preset `.ini` goes next to `Gw2-64.exe`, the mask goes into `reshade-shaders\Textures`.
2. Run the ReShade installer, select `Gw2-64.exe`, choose **DirectX 10/11/12**.
3. When asked for a preset, browse to the preset `.ini` from this archive: the installer will tick the required effect packages for you.
4. Launch the game, open ReShade (Home key) and select the preset in the dropdown at the top.
5. Open UIMask_Bottom and tick **Display Mask** once: white boxes should sit exactly on your HUD. Untick it afterwards.

**If ReShade does not load:** rename `dxgi.dll` to `d3d11.dll` in the game folder.

## Recommended in-game settings (F11)

| Setting | Value |
|---|---|
| Antialiasing | SMAA High |
| Render Sampling | Supersample |
| Ambient Occlusion | On |
| Bloom, Distortion, Depth Blur, Light Adaptation | Off |
| Motion Blur Power | Minimum |
| Reflections | None (big CPU saving) |
| Character Model Limit / Quality | Lower them in crowded metas |

Optional: cap at 40 FPS (RTSS) + Lossless Scaling x2 for a smooth 80 FPS on CPU-limited setups like mine !

## Notes

- **The HUD mask only fits 2560 × 1440 with interface size "Normal".** Other resolutions or UI sizes need a new mask (paint white boxes over your HUD on a black 1:1 screenshot-sized PNG).
- Moving elements that are not masked (damage numbers, nameplates) can look slightly soft in motion because of the temporal pass.
- A bit of trailing in motion? Lower ATA's **Accumulation value** (0.90 → 0.80) or switch to **NonLocal** mode with `ACCUMULATION_QUALITY` set to 0.
- ArenaNet does not endorse any third-party program. ReShade is widely used in GW2, but use it at your own risk.

## Credits

- Marty McFly – iMMERSE (MXAO, SMAA, Sharpen)
- Zenteon – ZenteonFX (Motion, ATA)
- crosire – ReShade and UIMask

## Changelog

- **v1.0** – Initial release
- **v1.1** – Sharpening 0.40 → 0.25 (removes noise), ATA accumulation 0.90 → 0.85, MXAO quality High + Filter 2








# GW2 Net et Stable – preset ReShade pour Guild Wars 2

Un preset léger, pensé pour jouer, centré sur **la netteté et le minimum d'aliasing** plutôt que sur l'étalonnage des couleurs.
Il respecte la direction artistique de GW2 et nettoie surtout les bords crénelés et le scintillement en mouvement.

**Conçu pour :** 2560 × 1440, taille d'interface « Normale ». Compatible avec la génération d'images de Lossless Scaling.

## Chaîne d'effets

| Ordre | Effet | Rôle |
|---|---|---|
| 1 | UIMask_Top | Sauvegarde le HUD avant tout traitement |
| 2 | iMMERSE: MXAO | Ombres de contact discrètes, en complément de l'AO du jeu |
| 3 | iMMERSE: Anti Aliasing (SMAA) | Rattrape les bords que le SMAA du jeu laisse passer |
| 4 | Zenteon: Motion | Vecteurs de mouvement pour la passe temporelle |
| 5 | Zenteon: ATA (BETA) | Réduit le scintillement en mouvement (feuillage, armure, lignes fines) |
| 6 | iMMERSE: Sharpen | Netteté qui tient compte de la profondeur et épargne les silhouettes |
| 7 | UIMask_Bottom | Recolle un HUD net et intact |

## Prérequis

- **ReShade avec support complet des add-ons** (dernière version sur reshade.me)
- Packs d'effets (à cocher dans l'installeur de ReShade) :
  - **iMMERSE** de Marty McFly (MXAO, SMAA, Sharpen)
  - **ZenteonFX** de Zenteon (Motion, ATA)
  - **Effets standard** de crosire (UIMask)

## Installation

1. Extrais cette archive **dans le dossier de Guild Wars 2** (par exemple `C:\Program Files\Guild Wars 2`).
   Le fichier `.ini` du preset se place à côté de `Gw2-64.exe`, le masque va dans `reshade-shaders\Textures`.
2. Lance l'installeur de ReShade, sélectionne `Gw2-64.exe`, choisis **DirectX 10/11/12**.
3. Quand il demande un preset, pointe vers le `.ini` de cette archive : l'installeur cochera automatiquement les packs d'effets nécessaires.
4. Lance le jeu, ouvre ReShade (touche Début) et sélectionne le preset dans la liste en haut.
5. Dans UIMask_Bottom, coche une fois **Display Mask** : des rectangles blancs doivent recouvrir exactement ton HUD. Décoche ensuite.

**Si ReShade ne se charge pas :** renomme `dxgi.dll` en `d3d11.dll` dans le dossier du jeu.

## Réglages en jeu recommandés (F11)

| Réglage | Valeur |
|---|---|
| Anticrénelage | SMAA élevé |
| Échantillonnage du rendu | Super échantillon |
| Occlusion ambiante | Activée |
| Flou lumineux, Distorsion, Floutage d'arrière-plan, Adaptation à la lumière | Désactivés |
| Intensité du flou cinétique | Minimum |
| Réflexions | Aucune (gros gain CPU) |
| Limite / Qualité des modèles de personnages | À baisser en méta |

Optionnel : caper les FPS à 40 avec RTSS + utiliser Lossless Scaling en frame generation x2 pour avoir 80 FPS stables pour une configuration CPU-limited comme la mienne !
## Remarques

- **Le masque du HUD n'est valable qu'en 2560 × 1440 avec une interface « Normale ».** Pour une autre résolution ou taille d'interface, il faut refaire le masque (rectangles blancs sur fond noir, à la taille exacte de l'écran).
- Les éléments mobiles non masqués (chiffres de dégâts, noms) peuvent paraître un peu doux en mouvement à cause de la passe temporelle.
- Un peu de traînée en mouvement ? Baisse l'**Accumulation value** d'ATA (0,90 → 0,80) ou passe en mode **NonLocal** avec `ACCUMULATION_QUALITY` à 0.
- ArenaNet ne valide aucun programme tiers. ReShade est très utilisé sur GW2, mais son usage reste à tes risques.

## Crédits

- Marty McFly – iMMERSE (MXAO, SMAA, Sharpen)
- Zenteon – ZenteonFX (Motion, ATA)
- crosire – ReShade et UIMask

## Historique

- **v1.0** – Première version
- **v1.1** – Netteté 0,40 → 0,25 (supprime le bruit), accumulation ATA 0,90 → 0,85, MXAO en qualité High + filtre 2


