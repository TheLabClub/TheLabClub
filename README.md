# The Lab Club

**The Lab Club** est un club de lapdance créé pour **VRChat**.

Ce repository regroupe les ressources utilisées pour le monde, notamment les **presets d'éclairage** et les **visuels associés aux différentes zones du club**.

L'objectif est de centraliser ces ressources afin de faciliter leur gestion, leur modification et l'ajout de nouvelles ambiances ou de nouveaux visuels.

---

## 📁 Structure du projet

```text
TheLabClub/
├── posters/
│   └── world/
│       ├── bridge_screens.png
│       ├── entrance_screens.png
│       └── spawn_screen.png
│
├── light_presets.json
│
└── README.md
```

---

## 💡 `light_presets.json`

Le fichier `light_presets.json` contient les différents **presets de lumière du club**.

Les presets permettent de créer et sauvegarder différentes ambiances lumineuses afin de pouvoir les utiliser rapidement dans le monde VRChat.

Un preset peut notamment contrôler :

- la couleur des lumières ;
- leur intensité ;
- les groupes de lumières concernés ;
- la durée de transition entre deux ambiances.

Cela permet de créer différentes atmosphères pour les différentes parties d'une soirée, d'une animation ou simplement pour modifier l'ambiance générale du club.

### Exemple de preset

```json
{
  "name": "Warm Chill",
  "transition": 2.5,
  "overridenGroups": [
    {
      "name": "Global",
      "color": "#FFA347",
      "intensity": 50
    },
    {
      "name": "Scene",
      "color": "#FF6B1A",
      "intensity": 120
    }
  ]
}
```

Dans cet exemple, le preset `Warm Chill` applique une ambiance chaude avec une transition de **2,5 secondes**.

---

## 🌈 Presets de lumière

Les presets sont stockés dans le tableau `Presets` de `light_presets.json`.

Chaque preset peut contenir les propriétés suivantes :

| Propriété | Description |
|---|---|
| `name` | Nom du preset |
| `transition` | Durée de la transition |
| `overridenGroups` | Groupes de lumières affectés |

### Groupes de lumières

Chaque groupe peut définir sa propre couleur et son intensité :

```json
{
  "name": "Scene",
  "color": "#FFFFFF",
  "intensity": 250
}
```

| Propriété | Description |
|---|---|
| `name` | Nom du groupe de lumières |
| `color` | Couleur de la lumière au format hexadécimal |
| `intensity` | Intensité de la lumière |

### 🎨 Couleurs

Les couleurs utilisent le format hexadécimal classique.

Quelques exemples :

```text
#FFFFFF  → Blanc
#000000  → Noir / lumière éteinte
#FF0000  → Rouge
#00FF00  → Vert
#0000FF  → Bleu
#FFA347  → Orange
#E675FF  → Rose / violet
```

---

## 🔄 Transitions

La propriété `transition` permet de définir la durée du changement entre deux configurations lumineuses.

```json
"transition": 2.5
```

correspond à une transition de **2,5 secondes**.

Les transitions permettent de passer progressivement d'une ambiance lumineuse à une autre plutôt que de changer instantanément la configuration des lumières.

---

## 🖼️ `posters/world/`

Le dossier `posters/world/` contient les **visuels utilisés pour les différentes zones du monde**.

Les images sont directement placées dans ce dossier.

| Fichier | Zone correspondante |
|---|---|
| `bridge_screens.png` | Écrans du **Bridge** |
| `entrance_screens.png` | Écrans de **l'entrée** |
| `spawn_screen.png` | Écran du **Spawn** |

La structure est volontairement simple :

```text
posters/
└── world/
    ├── bridge_screens.png
    ├── entrance_screens.png
    └── spawn_screen.png
```

### 🌉 `bridge_screens.png`

Visuels utilisés pour les écrans du **Bridge**.

### 🚪 `entrance_screens.png`

Visuels utilisés pour les écrans de **l'entrée du club**.

### 🌀 `spawn_screen.png`

Visuel utilisé pour l'écran du **Spawn**.

---

## ➕ Ajouter un nouveau preset

Pour créer une nouvelle ambiance lumineuse, ajoutez un nouvel objet dans le tableau `Presets` de `light_presets.json`.

Exemple :

```json
{
  "name": "Purple Night",
  "transition": 2,
  "overridenGroups": [
    {
      "name": "Global",
      "color": "#3A145C",
      "intensity": 80
    },
    {
      "name": "Scene",
      "color": "#8E2DE2",
      "intensity": 220
    }
  ]
}
```

Il est recommandé d'utiliser un nom clair et facilement identifiable pour chaque preset.

---

## ⛔ Éteindre les lumières

Un preset peut également être utilisé pour éteindre un ou plusieurs groupes de lumières.

Par exemple :

```json
{
  "name": "OFF",
  "overridenGroups": [
    {
      "name": "Global",
      "color": "#000000",
      "intensity": 0
    }
  ]
}
```

Une intensité de `0` permet de désactiver la lumière du groupe concerné.

---

## ➕ Ajouter ou modifier un visuel

Pour ajouter un visuel lié au monde :

1. Placez l'image dans `posters/world/`.
2. Utilisez un nom de fichier explicite.
3. Indiquez clairement la zone à laquelle l'image correspond.
4. Vérifiez son affichage directement dans le monde VRChat.

Exemple :

```text
posters/world/
├── bridge_screens.png
├── entrance_screens.png
├── spawn_screen.png
└── nouveau_visuel.png
```

---

## 🎛️ Gestion des ambiances

Les presets permettent de préparer différentes ambiances pour le club, par exemple :

- ambiance d'ouverture ;
- ambiance calme ;
- ambiance de soirée ;
- ambiance de scène ;
- ambiance colorée ;
- transitions entre différentes animations ;
- extinction complète des lumières.

L'utilisation de presets permet ainsi de modifier rapidement l'ambiance visuelle du club sans devoir reconfigurer manuellement chaque lumière.

---

## 🛠️ Bonnes pratiques

Lors de la modification du projet :

- utilisez des noms explicites pour les presets ;
- gardez une structure de fichiers simple ;
- évitez de modifier inutilement un preset déjà utilisé ;
- créez un nouveau preset lorsqu'une nouvelle ambiance est nécessaire ;
- testez les changements directement dans le monde VRChat ;
- gardez les visuels de `posters/world/` correctement nommés.

---

## 📌 Résumé

| Élément | Utilisation |
|---|---|
| `light_presets.json` | Configuration des presets de lumière |
| `Presets` | Liste des différentes ambiances lumineuses |
| `overridenGroups` | Groupes de lumières modifiés |
| `color` | Couleur d'un groupe |
| `intensity` | Intensité d'un groupe |
| `transition` | Durée du changement d'ambiance |
| `posters/world/` | Visuels liés aux différentes zones du monde |
| `bridge_screens.png` | Visuels du Bridge |
| `entrance_screens.png` | Visuels de l'entrée |
| `spawn_screen.png` | Visuel du Spawn |

---

## 🎧 The Lab Club

**The Lab Club** est un club de lapdance conçu pour **VRChat**, avec un système de lumière permettant de changer rapidement d'ambiance ainsi que des visuels dédiés aux différentes zones du monde.

Ce repository sert à centraliser les ressources nécessaires à la gestion et à l'évolution de ces éléments.

---

## ⚠️ VRChat

The Lab Club est un monde destiné à **VRChat**. Son contenu et son utilisation doivent respecter les règles et conditions d'utilisation de VRChat.
