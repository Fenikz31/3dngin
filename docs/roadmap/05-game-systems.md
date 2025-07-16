# Phase 5: Game Systems (Semaines 13-16)

## Objectif
Implémenter les systèmes de gameplay spécifiques aux JRPG et jeux d'aventure, incluant l'interface utilisateur, les dialogues, l'inventaire et les systèmes de combat.

## Modules à Implémenter

### 1. User Interface System (`3dngin_ui`)

#### 1.1 UI Framework
- [ ] **UI rendering**
  - [ ] Système de rendu 2D pour l'UI
  - [ ] Gestion des layers et z-order
  - [ ] Culling des éléments UI
  - [ ] Responsive design pour différentes résolutions

- [ ] **Widget system**
  - [ ] Widget de base (Button, Label, Panel)
  - [ ] Layout system (Grid, Stack, Flex)
  - [ ] Event handling (click, hover, focus)
  - [ ] Thème et styling

#### 1.2 Advanced UI Components
- [ ] **Interactive elements**
  - [ ] Sliders et progress bars
  - [ ] Text input fields
  - [ ] Dropdown menus
  - [ ] Scrollable areas

- [ ] **Game-specific UI**
  - [ ] Health/mana bars
  - [ ] Minimap component
  - [ ] Inventory grid
  - [ ] Dialogue boxes

### 2. Dialogue System (`3dngin_jrpg`)

#### 2.1 Dialogue Engine
- [ ] **Dialogue parser**
  - [ ] Format de dialogue (Yarn, Ink, ou custom)
  - [ ] Système de variables
  - [ ] Conditions et branches
  - [ ] Functions et expressions

- [ ] **Dialogue runtime**
  - [ ] State machine des dialogues
  - [ ] Gestion des choix
  - [ ] Historique des dialogues
  - [ ] Système de skip et auto-play

#### 2.2 Character System
- [ ] **Character management**
  - [ ] Base de données des personnages
  - [ ] Portraits et expressions
  - [ ] Système de relations
  - [ ] Flags et états des personnages

- [ ] **Dialogue UI**
  - [ ] Boîte de dialogue stylisée
  - [ ] Typewriter effect
  - [ ] Animation des portraits
  - [ ] Indicateurs de choix

### 3. Inventory System

#### 3.1 Item Management
- [ ] **Item database**
  - [ ] Définition des items
  - [ ] Catégories et types
  - [ ] Propriétés et stats
  - [ ] Craft recipes

- [ ] **Inventory logic**
  - [ ] Système de slots
  - [ ] Stacking des items
  - [ ] Tri et filtrage
  - [ ] Durabilité des items

#### 3.2 Equipment System
- [ ] **Equipment slots**
  - [ ] Armes, armures, accessoires
  - [ ] Système de stats
  - [ ] Bonus sets
  - [ ] Prévisualisation des changements

### 4. Combat System

#### 4.1 Turn-Based Combat
- [ ] **Combat engine**
  - [ ] Initiative et ordre des tours
  - [ ] Système d'actions
  - [ ] Calcul des dégâts
  - [ ] Status effects

- [ ] **Combat AI**
  - [ ] Patterns d'attaque
  - [ ] Système de target selection
  - [ ] Difficulty scaling
  - [ ] Comportements spéciaux

#### 4.2 Skills & Magic
- [ ] **Skill system**
  - [ ] Arbre de compétences
  - [ ] Système d'XP et niveaux
  - [ ] Apprentissage de sorts
  - [ ] Cooldowns et ressources

### 5. Player Progression

#### 5.1 Experience System
- [ ] **Level progression**
  - [ ] Calcul de l'XP
  - [ ] Courbes de progression
  - [ ] Stat growth
  - [ ] Skill points

- [ ] **Character stats**
  - [ ] Stats de base (HP, MP, Attack, Defense)
  - [ ] Stats dérivées
  - [ ] Modificateurs temporaires
  - [ ] Calcul des formules

#### 5.2 Quest System
- [ ] **Quest management**
  - [ ] Définition des quêtes
  - [ ] Objectifs et étapes
  - [ ] Conditions d'achèvement
  - [ ] Récompenses

- [ ] **Quest UI**
  - [ ] Journal des quêtes
  - [ ] Tracking des objectifs
  - [ ] Indicateurs de progression
  - [ ] Notifications

### 6. World Interaction

#### 6.1 NPC System
- [ ] **NPC behavior**
  - [ ] Patterns de mouvement
  - [ ] Schedules et routines
  - [ ] Interaction states
  - [ ] Dialogue triggers

- [ ] **NPC AI**
  - [ ] Pathfinding pour NPCs
  - [ ] Réactions aux événements
  - [ ] Emotions et states
  - [ ] Group behaviors

#### 6.2 World Events
- [ ] **Event system**
  - [ ] Triggers globaux
  - [ ] Conditions temporelles
  - [ ] Story progression
  - [ ] Cutscenes basiques

### 7. Menu Systems

#### 7.1 Main Menu
- [ ] **Navigation**
  - [ ] Menu principal
  - [ ] Options et settings
  - [ ] Save/Load screens
  - [ ] Controller support

#### 7.2 Game Menus
- [ ] **In-game menus**
  - [ ] Pause menu
  - [ ] Status screen
  - [ ] Equipment menu
  - [ ] Sistema de sauvegarde

### 8. Save System

#### 8.1 Game State
- [ ] **Save data**
  - [ ] Sérialisation du state
  - [ ] Compression des saves
  - [ ] Validation des données
  - [ ] Backward compatibility

- [ ] **Save slots**
  - [ ] Multiple save slots
  - [ ] Screenshots de saves
  - [ ] Metadata des saves
  - [ ] Import/export

### 9. Scripting System

#### 9.1 Game Scripts
- [ ] **Script engine**
  - [ ] Lua intégration (via mlua)
  - [ ] API pour les scripts
  - [ ] Sandbox sécurisé
  - [ ] Hot-reload des scripts

- [ ] **Script utilities**
  - [ ] Cutscene scripting
  - [ ] Event handlers
  - [ ] Condition evaluation
  - [ ] Debug interface

### 10. Localization Integration

#### 10.1 Game Text
- [ ] **Text management**
  - [ ] Intégration avec le système de loc
  - [ ] Dialogue localization
  - [ ] Menu text
  - [ ] Dynamic text formatting

### 11. Mobile Adaptations

#### 11.1 Touch Controls
- [ ] **Touch UI**
  - [ ] Adaptation des contrôles
  - [ ] Virtual joystick
  - [ ] Gesture recognition
  - [ ] Responsive layouts

## Dépendances Principales

```toml
[dependencies]
# UI
egui = "0.23"  # Alternative UI framework
# ou custom UI system

# Scripting
mlua = "0.9"

# Data management
serde = { version = "1.0", features = ["derive"] }
serde_json = "1.0"
ron = "0.8"

# Text processing
regex = "1.0"
unicode-segmentation = "1.0"

# Utilities
anyhow = "1.0"
uuid = "1.0"
```

## Livrables de la Phase 5

- [ ] **Système UI complet**
  - Framework UI fonctionnel
  - Widgets essentiels
  - Responsive design

- [ ] **Gameplay systems**
  - Dialogue system opérationnel
  - Inventory et equipment
  - Combat turn-based

- [ ] **Progression systems**
  - XP et niveaux
  - Quest system
  - Save/Load robuste

- [ ] **JRPG features**
  - NPC interactions
  - World events
  - Scripting support

## Critères de Validation

- [ ] UI responsive et intuitive
- [ ] Dialogues fluides et expressifs
- [ ] Inventory system complet
- [ ] Combat équilibré et fun
- [ ] Progression satisfaisante
- [ ] Save/Load fiables
- [ ] Performance stable avec tous les systèmes

## Estimation de Temps

- **Semaine 13** : UI framework, widgets basiques
- **Semaine 14** : Dialogue system, character management
- **Semaine 15** : Inventory, combat, progression
- **Semaine 16** : Menu systems, save system, polish

---

**Étape précédente** : [Phase 4 - Audio & Assets](./04-audio-assets.md)  
**Prochaine étape** : [Phase 6 - Polish & Optimization](./06-polish-optimization.md) 