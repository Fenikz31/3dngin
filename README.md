# 3DNgin 🎮

Un moteur de jeu vidéo 3D léger, minimaliste, performant et modulaire développé en Rust, spécialement conçu pour les JRPG et jeux d'aventure stylisés.

## 🚀 Caractéristiques

- **Léger et Performant** : Optimisé pour PC, mobile et WebAssembly
- **Modulaire** : Architecture basée sur des crates indépendants
- **Cross-platform** : Windows, Linux, macOS, iOS, Android, Web
- **Orienté JRPG** : Systèmes dédiés aux jeux d'aventure et RPG
- **Rendu Stylisé** : Toon shading et effets cel-shading
- **ECS Architecture** : Entity Component System moderne

## 📋 Roadmap

Voir [docs/roadmap/](docs/roadmap/) pour la planification détaillée :

- ✅ [Phase 1: Foundation](docs/roadmap/01-foundation.md) (Semaines 1-3)
- ⏳ [Phase 2: Rendering](docs/roadmap/02-rendering.md) (Semaines 4-6)
- ⏳ [Phase 3: Scene & Physics](docs/roadmap/03-scene-physics.md) (Semaines 7-9)
- ⏳ [Phase 4: Audio & Assets](docs/roadmap/04-audio-assets.md) (Semaines 10-12)
- ⏳ [Phase 5: Game Systems](docs/roadmap/05-game-systems.md) (Semaines 13-16)
- ⏳ [Phase 6: Polish & Optimization](docs/roadmap/06-polish-optimization.md) (Semaines 17-20)

## 🏗️ Architecture

```
3dngin/
├── crates/
│   ├── 3dngin_core/        # 🔧 Noyau du moteur
│   ├── 3dngin_render/      # 🎨 Système de rendu
│   ├── 3dngin_audio/       # 🔊 Système audio
│   ├── 3dngin_input/       # 🎮 Gestion des entrées
│   ├── 3dngin_physics/     # ⚡ Physique et collisions
│   ├── 3dngin_scene/       # 🌍 Gestion des scènes
│   ├── 3dngin_assets/      # 📦 Chargement des ressources
│   ├── 3dngin_ui/          # 🖥️ Interface utilisateur
│   └── 3dngin_jrpg/        # 🎲 Systèmes spécifiques JRPG
├── examples/               # 📚 Exemples d'utilisation
├── docs/                   # 📖 Documentation
└── tests/                  # 🧪 Tests d'intégration
```

## 🛠️ Technologies Utilisées

- **Rendu** : `wgpu` (cross-platform)
- **Physique** : `rapier3d`
- **Audio** : `rodio`
- **Fenêtrage** : `winit`
- **Math** : `glam`
- **Sérialisation** : `serde`

## 🚦 Démarrage Rapide

> ⚠️ **En cours de développement** - Le moteur n'est pas encore prêt pour utilisation

Une fois la Phase 1 terminée :

```bash
# Cloner le repository
git clone https://github.com/yourusername/3dngin.git
cd 3dngin

# Lancer l'exemple "Hello Engine"
cargo run --example hello_engine

# Lancer les tests
cargo test

# Générer la documentation
cargo doc --open
```

## 🎯 Objectifs JRPG

- **Système de Dialogue** : Conversations branchées avec portraits
- **Inventaire** : Système d'items et d'équipement
- **Combat** : Système de combat au tour par tour
- **Progression** : XP, niveaux, et arbre de compétences
- **Quêtes** : Système de missions et objectifs
- **Sauvegarde** : Persistance des données de jeu

## 🌐 Support Multi-plateforme

| Plateforme | Statut | Notes |
|------------|--------|-------|
| Windows    | ✅ Planifié | Support complet |
| Linux      | ✅ Planifié | Support complet |
| macOS      | ✅ Planifié | Support complet |
| Android    | ⏳ Phase 6 | Optimisations mobiles |
| iOS        | ⏳ Phase 6 | Optimisations mobiles |
| WebAssembly| ⏳ Phase 6 | Navigateurs modernes |

## 📊 Performance Cible

- **PC** : 60 FPS stable, < 100MB RAM
- **Mobile** : 30-60 FPS adaptatif, < 50MB RAM
- **Web** : 30 FPS stable, < 20MB bundle

## 🤝 Contribution

Ce projet est en développement actif. Les contributions seront les bienvenues une fois la Phase 1 terminée.

## 📜 License

Dual-licensed sous MIT et Apache-2.0.

---

**État du projet** : 🔨 En développement - Phase 1 en cours  
**Prochaine milestone** : Moteur de base fonctionnel (Semaine 3) 