# Phase 1: Foundation (Semaines 1-3)

## Objectif
Établir les fondations solides du moteur avec l'architecture de base, la configuration du projet et les systèmes essentiels.

## Modules à Implémenter

### 1. Configuration du Workspace Cargo
- [ ] **Initialisation du workspace**
  - [ ] Créer `Cargo.toml` racine avec workspace
  - [ ] Configurer les crates membres
  - [ ] Définir les dépendances communes
  - [ ] Configurer les features flags pour différentes plateformes

- [ ] **Structure des crates**
  - [ ] `3dngin_core/` : Noyau du moteur
  - [ ] `3dngin_render/` : Système de rendu (stub)
  - [ ] `3dngin_input/` : Gestion des entrées (stub)
  - [ ] Autres crates (stubs pour définir l'architecture)

- [ ] **Configuration de développement**
  - [ ] `rustfmt.toml` pour le formatage du code
  - [ ] `clippy.toml` pour les lint rules
  - [ ] `.gitignore` adapté au projet Rust
  - [ ] Configuration VS Code/Cursor avec `rust-analyzer`

### 2. Module Core (`3dngin_core`)

#### 2.1 Boucle Principale du Moteur
- [ ] **Engine struct**
  - [ ] Structure principale `Engine`
  - [ ] Méthodes `new()`, `run()`, `update()`, `render()`
  - [ ] Gestion du delta time
  - [ ] Fixed timestep pour la physique

- [ ] **Application trait**
  - [ ] Trait `Application` pour les jeux
  - [ ] Callbacks : `init()`, `update()`, `render()`, `cleanup()`
  - [ ] Exemple d'implémentation basique

#### 2.2 Système d'Événements
- [ ] **Event system**
  - [ ] Enum `Event` pour les différents événements
  - [ ] `EventBus` pour la distribution des événements
  - [ ] Système d'abonnement/désabonnement
  - [ ] Priorités des événements

- [ ] **Types d'événements**
  - [ ] Événements fenêtre (resize, close, focus)
  - [ ] Événements input (keyboard, mouse, gamepad)
  - [ ] Événements système (pause, resume)
  - [ ] Événements custom pour les jeux

#### 2.3 Gestion du Temps
- [ ] **Time management**
  - [ ] Structure `Time` avec delta, elapsed, fps
  - [ ] Gestion du frame rate (vsync, cap)
  - [ ] Système de pause/resume
  - [ ] Timers et compteurs

### 3. Système de Fenêtrage (`3dngin_core`)

#### 3.1 Window Management
- [ ] **Window abstraction**
  - [ ] Wrapper autour de `winit::Window`
  - [ ] Configuration de fenêtre (taille, titre, fullscreen)
  - [ ] Gestion des événements de fenêtre
  - [ ] Support multi-fenêtre (optionnel)

- [ ] **Context management**
  - [ ] Contexte de rendu (préparation pour wgpu)
  - [ ] Gestion des surfaces de rendu
  - [ ] Adaptation aux différentes plateformes

#### 3.2 Input basique
- [ ] **Input abstraction**
  - [ ] Enum `Key` pour les touches clavier
  - [ ] Enum `MouseButton` pour les boutons souris
  - [ ] Structure `InputState` pour l'état des entrées
  - [ ] Conversion des événements winit

### 4. Infrastructure de Logging

#### 4.1 Système de Logging
- [ ] **Logger configuration**
  - [ ] Intégration avec `log` crate
  - [ ] Configuration des niveaux de log
  - [ ] Formatage des messages
  - [ ] Sortie console et fichier

- [ ] **Profiling hooks**
  - [ ] Macros pour le profiling
  - [ ] Mesure des performances critiques
  - [ ] Préparation pour l'optimisation

### 5. Système ECS Basique

#### 5.1 Entity Component System
- [ ] **Core ECS**
  - [ ] Entity ID system
  - [ ] Component trait et storage
  - [ ] System trait pour le traitement
  - [ ] World comme container principal

- [ ] **ECS utilities**
  - [ ] Queries pour filtrer les entités
  - [ ] Commands pour la création/destruction
  - [ ] Resources globales
  - [ ] Gestion des dépendances entre systèmes

### 6. Tests et Exemples

#### 6.1 Tests Unitaires
- [ ] **Tests pour chaque module**
  - [ ] Tests du moteur principal
  - [ ] Tests des événements
  - [ ] Tests du système de temps
  - [ ] Tests ECS basiques

#### 6.2 Exemples de Base
- [ ] **Exemple "Hello Engine"**
  - [ ] Fenêtre noire qui se ferme avec ESC
  - [ ] Affichage des FPS dans la console
  - [ ] Test des événements de base

- [ ] **Exemple "Input Test"**
  - [ ] Test des entrées clavier/souris
  - [ ] Affichage des événements reçus
  - [ ] Test de fermeture propre

## Dépendances Principales

```toml
[dependencies]
# Core dependencies
log = "0.4"
env_logger = "0.10"
anyhow = "1.0"

# Window and input
winit = "0.28"

# Math
glam = "0.24"

# Utilities
serde = { version = "1.0", features = ["derive"] }
```

## Livrables de la Phase 1

- [ ] **Workspace Cargo fonctionnel**
  - Configuration complète du projet
  - Structure des crates définie
  - Compilation sans erreurs

- [ ] **Moteur minimaliste**
  - Boucle principale fonctionnelle
  - Gestion des événements
  - Système de fenêtrage basique

- [ ] **Infrastructure de base**
  - Logging configuré
  - ECS basique opérationnel
  - Tests unitaires passants

- [ ] **Documentation**
  - README du projet
  - Documentation API (rustdoc)
  - Guide de démarrage

## Critères de Validation

- [ ] Le moteur démarre et affiche une fenêtre
- [ ] Les événements sont correctement capturés
- [ ] Le delta time est calculé précisément
- [ ] Les tests unitaires passent
- [ ] La documentation est générée sans erreurs
- [ ] L'exemple "Hello Engine" fonctionne

## Estimation de Temps

- **Semaine 1** : Configuration workspace, structure de base
- **Semaine 2** : Moteur principal, événements, fenêtrage
- **Semaine 3** : ECS, tests, documentation, polish

---

**Prochaine étape** : [Phase 2 - Rendering](./02-rendering.md) 