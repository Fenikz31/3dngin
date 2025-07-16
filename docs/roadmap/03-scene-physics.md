# Phase 3: Scene & Physics (Semaines 7-9)

## Objectif
Implémenter le système de gestion des scènes avec hiérarchie d'objets, transformations et système de physique pour les interactions et collisions.

## Modules à Implémenter

### 1. Scene Management (`3dngin_scene`)

#### 1.1 Scene Graph
- [ ] **Scene struct**
  - [ ] Structure `Scene` comme container principal
  - [ ] Gestion des entités et hiérarchie
  - [ ] Système de noms et tags
  - [ ] Sérialisation/désérialisation

- [ ] **Node hierarchy**
  - [ ] `SceneNode` avec parent/enfants
  - [ ] Parcours de l'arbre (depth-first, breadth-first)
  - [ ] Opérations sur la hiérarchie (attach, detach)
  - [ ] Recherche et filtrage des nodes

#### 1.2 Transformation System
- [ ] **Transform component**
  - [ ] Position, rotation, scale locale
  - [ ] Matrice de transformation locale
  - [ ] Matrice de transformation globale
  - [ ] Invalidation et mise à jour

- [ ] **Transform hierarchy**
  - [ ] Propagation des transformations
  - [ ] Système de cache pour les matrices
  - [ ] Optimisation des calculs
  - [ ] Gestion des transformations dirty

### 2. GameObject System

#### 2.1 GameObject Architecture
- [ ] **GameObject struct**
  - [ ] Entité avec components
  - [ ] Système de tags et layers
  - [ ] Activation/désactivation
  - [ ] Lifecycle management

- [ ] **Component system**
  - [ ] Ajout/suppression dynamique
  - [ ] Sérialisation des components
  - [ ] Validation des dépendances
  - [ ] Events de lifecycle

#### 2.2 Built-in Components
- [ ] **Mesh Renderer**
  - [ ] Référence au mesh et matériau
  - [ ] Bounding box et culling
  - [ ] Niveau de détail (LOD)
  - [ ] Paramètres de rendu

- [ ] **Collider components**
  - [ ] Box, sphere, capsule colliders
  - [ ] Mesh colliders
  - [ ] Trigger zones
  - [ ] Collision layers

### 3. Physics System (`3dngin_physics`)

#### 3.1 Physics World
- [ ] **Physics integration**
  - [ ] Intégration avec rapier3d
  - [ ] Monde physique 3D
  - [ ] Configuration des propriétés
  - [ ] Synchronisation avec le rendu

- [ ] **Rigidbody component**
  - [ ] Masse, inertie, friction
  - [ ] Kinematic vs Dynamic
  - [ ] Contraintes de mouvement
  - [ ] Forces et impulsions

#### 3.2 Collision Detection
- [ ] **Collision shapes**
  - [ ] Formes primitives (box, sphere, capsule)
  - [ ] Compound shapes
  - [ ] Convex hulls
  - [ ] Heightfields pour les terrains

- [ ] **Collision events**
  - [ ] Callbacks de collision
  - [ ] Trigger events
  - [ ] Raycast et shapecast
  - [ ] Filtrage des collisions

### 4. Character Controller

#### 4.1 Character Movement
- [ ] **Character Controller**
  - [ ] Mouvement kinematic
  - [ ] Gestion des pentes
  - [ ] Détection du sol
  - [ ] Gestion des escaliers

- [ ] **Movement systems**
  - [ ] Marche et course
  - [ ] Saut et gravité
  - [ ] Glissement sur surfaces
  - [ ] Système d'état du mouvement

#### 4.2 AI Movement
- [ ] **Pathfinding basique**
  - [ ] Navigation mesh simple
  - [ ] A* pathfinding
  - [ ] Évitement d'obstacles
  - [ ] Formation et groupes

### 5. Spatial Partitioning

#### 5.1 Spatial Structures
- [ ] **Octree implementation**
  - [ ] Partitionnement spatial 3D
  - [ ] Insertion et suppression
  - [ ] Queries spatiales
  - [ ] Optimisation des performances

- [ ] **Spatial queries**
  - [ ] Range queries
  - [ ] Nearest neighbor
  - [ ] Intersection tests
  - [ ] Frustum culling optimisé

### 6. Animation System

#### 6.1 Transform Animation
- [ ] **Animation clips**
  - [ ] Keyframes pour transforms
  - [ ] Interpolation (linear, bezier)
  - [ ] Animation curves
  - [ ] Looping et ping-pong

- [ ] **Animation controller**
  - [ ] State machine basique
  - [ ] Blending d'animations
  - [ ] Animation events
  - [ ] Transition conditions

#### 6.2 Skeletal Animation (Préparation)
- [ ] **Bone structure**
  - [ ] Hiérarchie d'os
  - [ ] Bind poses
  - [ ] Inverse kinematics basique
  - [ ] Vertex skinning

### 7. Gameplay Systems

#### 7.1 Interaction System
- [ ] **Interaction components**
  - [ ] Interactable objects
  - [ ] Proximity detection
  - [ ] Interaction prompts
  - [ ] Actions et callbacks

- [ ] **Pickup system**
  - [ ] Items ramassables
  - [ ] Système d'inventaire simple
  - [ ] Trigger zones
  - [ ] Effets visuels

#### 7.2 Trigger System
- [ ] **Trigger zones**
  - [ ] Zones d'activation
  - [ ] Events on enter/exit
  - [ ] Conditions d'activation
  - [ ] Scripting hooks

### 8. Terrain System

#### 8.1 Terrain Rendering
- [ ] **Heightmap terrain**
  - [ ] Génération depuis heightmap
  - [ ] Multiple textures
  - [ ] Texture splatting
  - [ ] LOD pour les terrains

- [ ] **Terrain physics**
  - [ ] Collision avec heightfield
  - [ ] Végétation et décoration
  - [ ] Optimisation des collisions
  - [ ] Streaming de terrain

### 9. Tests et Exemples

#### 9.1 Physics Tests
- [ ] **Unit tests**
  - [ ] Tests de collision
  - [ ] Tests de mouvement
  - [ ] Tests de hiérarchie
  - [ ] Tests d'animation

#### 9.2 Exemples Interactifs
- [ ] **Exemple "Physics Playground"**
  - [ ] Cubes qui tombent
  - [ ] Balles qui rebondissent
  - [ ] Démonstration des joints

- [ ] **Exemple "Character Demo"**
  - [ ] Personnage contrôlable
  - [ ] Plateformes et obstacles
  - [ ] Collectibles et interactions

## Dépendances Principales

```toml
[dependencies]
# Physics
rapier3d = "0.17"
nalgebra = "0.32"

# Scene management
serde = { version = "1.0", features = ["derive"] }
ron = "0.8"

# Math
glam = "0.24"

# Utilities
anyhow = "1.0"
```

## Livrables de la Phase 3

- [ ] **Système de scène fonctionnel**
  - Hiérarchie d'objets
  - Transformations et matrices
  - Serialization des scènes

- [ ] **Physique intégrée**
  - Collision detection
  - Rigidbody dynamics
  - Character controller

- [ ] **Gameplay systems**
  - Interactions basiques
  - Animations simples
  - Terrain support

- [ ] **Exemples jouables**
  - Démos interactives
  - Tests de performance
  - Validation des systèmes

## Critères de Validation

- [ ] Objets physiques réalistes
- [ ] Hiérarchie de scène fonctionnelle
- [ ] Character controller responsive
- [ ] Collisions précises et stables
- [ ] Animations fluides
- [ ] Performance acceptable avec nombreux objets

## Estimation de Temps

- **Semaine 7** : Scene graph, transformations, GameObject
- **Semaine 8** : Physics integration, collisions, character controller
- **Semaine 9** : Animations, terrain, optimisations

---

**Étape précédente** : [Phase 2 - Rendering](./02-rendering.md)  
**Prochaine étape** : [Phase 4 - Audio & Assets](./04-audio-assets.md) 