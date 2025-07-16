# 3DNgin - Moteur de Jeu 3D en Rust

## Vue d'ensemble

**3DNgin** est un moteur de jeu vidéo 3D léger, minimaliste, performant et modulaire développé en Rust. Il est spécialement conçu pour les plateformes PC et mobile (avec support WebAssembly) et optimisé pour les JRPG et jeux d'aventure stylisés.

## Objectifs du Projet

### Caractéristiques Principales
- [x] **Léger et Minimaliste** : Architecture simple, fonctionnalités essentielles uniquement
- [x] **Performant** : Optimisé pour les ressources limitées (mobile, web)
- [x] **Modulaire** : Système de composants réutilisables et extensibles
- [x] **Cross-platform** : PC (Windows, Linux, macOS), Mobile (iOS, Android), Web (WebAssembly)
- [x] **Orienté JRPG** : Systèmes dédiés aux jeux d'aventure et RPG stylisés

### Architecture Technique
- **Langage** : Rust (sécurité mémoire, performance)
- **Rendu** : wgpu (API graphique cross-platform)
- **Architecture** : Entity Component System (ECS)
- **Gestion fenêtres** : winit
- **Physique** : rapier3d
- **Audio** : rodio

## Structure du Projet

```
3dngin/
├── crates/
│   ├── 3dngin_core/     # Noyau du moteur
│   ├── 3dngin_render/   # Système de rendu
│   ├── 3dngin_audio/    # Système audio
│   ├── 3dngin_input/    # Gestion des entrées
│   ├── 3dngin_physics/  # Physique et collisions
│   ├── 3dngin_scene/    # Gestion des scènes
│   ├── 3dngin_assets/   # Chargement des ressources
│   └── 3dngin_jrpg/     # Systèmes spécifiques JRPG
├── examples/            # Exemples d'utilisation
├── docs/               # Documentation
└── tests/              # Tests d'intégration
```

## Roadmap Générale

### Phase 1: Foundation (Semaines 1-3)
- [ ] Configuration du workspace Cargo
- [ ] Module core avec boucle principale
- [ ] Système de fenêtrage basique
- [ ] Gestion des événements
- [ ] Infrastructure de logging

### Phase 2: Rendering (Semaines 4-6)
- [ ] Système de rendu 3D basique
- [ ] Gestion des shaders
- [ ] Chargement de meshes
- [ ] Système de caméra
- [ ] Matériaux et textures

### Phase 3: Scene & Physics (Semaines 7-9)
- [ ] Scene graph et hiérarchie d'objets
- [ ] Système de transformation
- [ ] Détection de collisions
- [ ] Physique basique (mouvement, gravité)

### Phase 4: Audio & Assets (Semaines 10-12)
- [ ] Système audio (sons, musique)
- [ ] Pipeline de chargement d'assets
- [ ] Sérialisation/désérialisation
- [ ] Système de ressources

### Phase 5: Game Systems (Semaines 13-16)
- [ ] Système d'interface utilisateur
- [ ] Système de dialogue
- [ ] Gestion des inventaires
- [ ] Système de combat
- [ ] Sauvegarde/chargement

### Phase 6: Polish & Optimization (Semaines 17-20)
- [ ] Optimisations performance
- [ ] Profiling et debugging
- [ ] Documentation complète
- [ ] Exemples et tutoriels
- [ ] Tests automatisés

## Fichiers de Planification

- [Phase 1: Foundation](./01-foundation.md)
- [Phase 2: Rendering](./02-rendering.md)
- [Phase 3: Scene & Physics](./03-scene-physics.md)
- [Phase 4: Audio & Assets](./04-audio-assets.md)
- [Phase 5: Game Systems](./05-game-systems.md)
- [Phase 6: Polish & Optimization](./06-polish-optimization.md)

## Métriques de Succès

- [ ] Moteur fonctionnel sur PC, mobile et web
- [ ] Exemple de JRPG simple jouable
- [ ] Documentation complète pour développeurs
- [ ] Performance acceptable sur hardware modeste
- [ ] Architecture maintenir et extensible
