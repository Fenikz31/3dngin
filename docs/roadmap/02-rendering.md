# Phase 2: Rendering (Semaines 4-6)

## Objectif
Implémenter le système de rendu 3D avec wgpu, incluant la gestion des shaders, meshes, textures et matériaux pour créer une pipeline de rendu efficace et modulaire.

## Modules à Implémenter

### 1. Infrastructure de Rendu (`3dngin_render`)

#### 1.1 Contexte de Rendu
- [ ] **Renderer struct**
  - [ ] Structure principale `Renderer`
  - [ ] Initialisation avec `wgpu::Device`, `wgpu::Queue`
  - [ ] Gestion des surfaces de rendu
  - [ ] Configuration cross-platform (PC, mobile, web)

- [ ] **Render Context**
  - [ ] `RenderContext` avec device, queue, surface
  - [ ] Gestion des formats de pixels
  - [ ] Adaptation aux capacités GPU
  - [ ] Gestion des erreurs de rendu

#### 1.2 Command Buffer System
- [ ] **Command recording**
  - [ ] `RenderCommandBuffer` pour enregistrer les commandes
  - [ ] Système de batching pour optimiser les appels
  - [ ] Gestion des render passes
  - [ ] Synchronisation GPU/CPU

### 2. Système de Shaders

#### 2.1 Shader Management
- [ ] **Shader compilation**
  - [ ] Chargement des fichiers WGSL
  - [ ] Compilation et validation
  - [ ] Cache des shaders compilés
  - [ ] Hot-reload pour le développement

- [ ] **Shader uniforms**
  - [ ] Structure `Uniform` générique
  - [ ] Binding des uniforms aux shaders
  - [ ] Update dynamique des uniforms
  - [ ] Gestion des buffer uniforms

#### 2.2 Shaders de Base
- [ ] **Vertex shader basique**
  - [ ] Transformation MVP (Model-View-Projection)
  - [ ] Gestion des positions et normales
  - [ ] Support des couleurs vertex
  - [ ] Calcul des coordonnées UV

- [ ] **Fragment shader basique**
  - [ ] Rendu de couleurs unies
  - [ ] Sampling de textures
  - [ ] Éclairage Phong/Blinn-Phong basique
  - [ ] Support de la transparence

### 3. Système de Meshes

#### 3.1 Mesh Representation
- [ ] **Mesh struct**
  - [ ] Structure `Mesh` avec vertices, indices
  - [ ] `Vertex` trait pour différents types de vertices
  - [ ] Gestion des buffers GPU
  - [ ] Optimisation des données (interleaving)

- [ ] **Primitive meshes**
  - [ ] Générateurs de cubes, sphères, plans
  - [ ] Cylindres, cônes pour les formes de base
  - [ ] Grilles et heightmaps
  - [ ] Primitives optimisées pour les jeux

#### 3.2 Mesh Loading
- [ ] **Format support**
  - [ ] Chargement OBJ basique
  - [ ] Support GLTF/GLB (via gltf crate)
  - [ ] Format custom optimisé
  - [ ] Validation et nettoyage des meshes

### 4. Système de Caméra

#### 4.1 Camera Types
- [ ] **Perspective camera**
  - [ ] Matrice de projection perspective
  - [ ] Gestion du FOV, near/far planes
  - [ ] Aspect ratio adaptatif
  - [ ] Frustum culling basique

- [ ] **Orthographic camera**
  - [ ] Matrice de projection orthographique
  - [ ] Gestion des bounds
  - [ ] Utilisation pour l'UI et les outils

#### 4.2 Camera Control
- [ ] **View matrix**
  - [ ] Calcul de la view matrix
  - [ ] Gestion de la position, rotation
  - [ ] Look-at et FPS camera
  - [ ] Smooth camera movement

### 5. Système de Matériaux

#### 5.1 Material System
- [ ] **Material struct**
  - [ ] Properties basiques (color, metallic, roughness)
  - [ ] Références aux textures
  - [ ] Paramètres de shader
  - [ ] Matériaux prédéfinis

- [ ] **Material binding**
  - [ ] Binding des matériaux aux meshes
  - [ ] Système de render states
  - [ ] Gestion des blend modes
  - [ ] Optimisation des state changes

#### 5.2 Texture System
- [ ] **Texture loading**
  - [ ] Chargement d'images (PNG, JPEG, etc.)
  - [ ] Génération de mipmaps
  - [ ] Formats de texture compressés
  - [ ] Atlas de textures

- [ ] **Texture types**
  - [ ] Diffuse, normal, specular maps
  - [ ] Cubemaps pour les skyboxes
  - [ ] Render targets
  - [ ] Texture arrays

### 6. Pipeline de Rendu

#### 6.1 Render Pipeline
- [ ] **Forward rendering**
  - [ ] Pipeline de rendu forward basique
  - [ ] Tri des objets (opaque puis transparent)
  - [ ] Depth testing et writing
  - [ ] Multi-sampling (MSAA)

- [ ] **Render passes**
  - [ ] Shadow mapping pass
  - [ ] Geometry pass
  - [ ] Lighting pass
  - [ ] Post-processing pass

#### 6.2 Culling System
- [ ] **Frustum culling**
  - [ ] Calcul du frustum de la caméra
  - [ ] Test d'intersection avec les bounding boxes
  - [ ] Statistiques de culling
  - [ ] Optimisation des calculs

### 7. Éclairage Basique

#### 7.1 Light Types
- [ ] **Directional light**
  - [ ] Lumière directionnelle (soleil)
  - [ ] Calcul des ombres
  - [ ] Cascade shadow maps
  - [ ] Paramètres de couleur et intensité

- [ ] **Point light**
  - [ ] Lumière ponctuelle
  - [ ] Atténuation par distance
  - [ ] Ombres omnidirectionnelles
  - [ ] Optimisation des calculs

#### 7.2 Lighting Calculations
- [ ] **Phong lighting**
  - [ ] Ambient, diffuse, specular
  - [ ] Calcul des normales
  - [ ] Gestion de multiple lights
  - [ ] Optimisations pour mobile

### 8. Rendu Stylisé pour JRPG

#### 8.1 Toon Shading
- [ ] **Cel shading**
  - [ ] Quantification des couleurs
  - [ ] Contours stylisés
  - [ ] Ramp textures pour l'éclairage
  - [ ] Effet cartoon/anime

- [ ] **Outline rendering**
  - [ ] Technique de back-face outline
  - [ ] Outline avec depth buffer
  - [ ] Épaisseur configurable
  - [ ] Couleurs d'outline adaptatives

#### 8.2 Effets Visuels
- [ ] **Particle system basique**
  - [ ] Émission de particules
  - [ ] Billboarding
  - [ ] Effets magiques simples
  - [ ] Optimisation GPU

### 9. Tests et Exemples

#### 9.1 Tests de Rendu
- [ ] **Unit tests**
  - [ ] Tests des matrices de transformation
  - [ ] Tests de chargement de meshes
  - [ ] Tests des shaders
  - [ ] Tests des matériaux

#### 9.2 Exemples Visuels
- [ ] **Exemple "Cube Rotatif"**
  - [ ] Cube texturé qui tourne
  - [ ] Éclairage basique
  - [ ] Contrôle caméra simple

- [ ] **Exemple "Scene Test"**
  - [ ] Multiple objets avec différents matériaux
  - [ ] Plusieurs sources de lumière
  - [ ] Démonstration du culling

## Dépendances Principales

```toml
[dependencies]
# Rendering
wgpu = "0.17"
winit = "0.28"

# Image loading
image = "0.24"

# Math
glam = "0.24"
bytemuck = { version = "1.14", features = ["derive"] }

# Asset loading
gltf = "1.3"

# Utilities
anyhow = "1.0"
```

## Livrables de la Phase 2

- [ ] **Système de rendu fonctionnel**
  - Pipeline de rendu 3D basique
  - Gestion des shaders et matériaux
  - Système de caméra opérationnel

- [ ] **Support des assets**
  - Chargement de meshes et textures
  - Formats standard supportés
  - Optimisation des ressources

- [ ] **Rendu stylisé**
  - Toon shading implémenté
  - Contours stylisés
  - Effets adaptés aux JRPG

- [ ] **Exemples fonctionnels**
  - Démonstrations visuelles
  - Tests de performance
  - Documentation des capacités

## Critères de Validation

- [ ] Affichage d'objets 3D texturés
- [ ] Éclairage fonctionnel et configurable
- [ ] Contrôle de caméra fluide
- [ ] Chargement d'assets externes
- [ ] Rendu stylisé opérationnel
- [ ] Performance acceptable sur hardware cible

## Estimation de Temps

- **Semaine 4** : Infrastructure wgpu, shaders basiques
- **Semaine 5** : Meshes, caméra, matériaux
- **Semaine 6** : Éclairage, rendu stylisé, optimisations

---

**Étape précédente** : [Phase 1 - Foundation](./01-foundation.md)  
**Prochaine étape** : [Phase 3 - Scene & Physics](./03-scene-physics.md) 