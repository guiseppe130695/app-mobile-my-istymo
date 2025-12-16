# 📱 React Native (Expo) – Application Mobile

Ce projet utilise **Expo Router** (file-based routing) pour mettre en place une architecture propre, scalable et professionnelle, pensée pour une application connectée à un backend **WordPress (Headless)**.

---

## 🎯 Objectif

Mettre en place une **base solide** pour :

* une application mobile Android & iOS
* une navigation basée sur les fichiers (file-based routing)
* une architecture modulaire et scalable
* une évolution future (auth, WordPress API, state management, etc.)

---

## 🧱 Architecture du projet

### Structure principale

```txt
my-istymo/
 ├── app/                    # Routes Expo Router (file-based routing)
 │   ├── _layout.tsx         # Layout racine avec Stack Navigator
 │   ├── (tabs)/             # Groupe de navigation par tabs
 │   │   ├── _layout.tsx     # Layout des tabs
 │   │   ├── index.tsx       # Écran Home
 │   │   └── explore.tsx     # Écran Explore
 │   └── modal.tsx           # Écran modal
 │
 ├── src/                    # Code source principal (logique métier)
 │   ├── api/                # Services API et appels HTTP
 │   ├── components/         # Composants réutilisables
 │   ├── hooks/              # Hooks personnalisés
 │   ├── navigation/         # Configuration navigation avancée
 │   ├── screens/            # Composants d'écrans (si nécessaire)
 │   ├── store/              # State management (Redux, Zustand, etc.)
 │   └── utils/              # Fonctions utilitaires
 │
 ├── components/             # Composants UI partagés
 ├── constants/              # Constantes (thème, couleurs, etc.)
 ├── hooks/                  # Hooks partagés (thème, color scheme)
 └── assets/                 # Images, fonts, etc.
```

---

## 🧭 Rôle de chaque dossier

### `app/` - Routes Expo Router

Contient la structure de navigation basée sur les fichiers :

* `_layout.tsx` → Layout racine avec Stack Navigator
* `(tabs)/` → Groupe de navigation par tabs
  * `index.tsx` → Écran d'accueil
  * `explore.tsx` → Écran d'exploration
* `modal.tsx` → Écran modal

👉 Expo Router génère automatiquement les routes à partir de la structure de fichiers.

---

### `src/` - Logique métier

Architecture modulaire pour séparer les préoccupations :

#### `src/api/`
Services API et appels HTTP vers le backend WordPress :
* Configuration des endpoints
* Gestion des requêtes (GET, POST, etc.)
* Intercepteurs et gestion d'erreurs

#### `src/components/`
Composants réutilisables spécifiques à l'application :
* Composants métier
* Composants de formulaire
* Composants de liste, etc.

#### `src/hooks/`
Hooks personnalisés pour la logique métier :
* Hooks de données (usePosts, useAuth, etc.)
* Hooks de navigation personnalisés
* Hooks de gestion d'état

#### `src/navigation/`
Configuration avancée de navigation (si nécessaire) :
* Types de navigation
* Helpers de navigation
* Guards et middlewares

#### `src/screens/`
Composants d'écrans réutilisables (optionnel si on utilise directement les fichiers dans `app/`) :
* Composants d'écran réutilisables
* Variantes d'écrans

#### `src/store/`
State management global :
* Store Redux / Zustand / Context
* Actions et reducers
* Sélecteurs

#### `src/utils/`
Fonctions utilitaires :
* Helpers de formatage
* Validations
* Transformations de données
* Constantes métier

---

### `components/` - Composants UI partagés

Composants UI réutilisables à la racine :
* Composants de base (themed-text, themed-view, etc.)
* Composants UI (collapsible, icon-symbol, etc.)

---

### `constants/` - Constantes

Configuration globale :
* Thème et couleurs
* Constantes d'application

---

### `hooks/` - Hooks partagés

Hooks génériques à la racine :
* `use-color-scheme` → Détection du thème (dark/light)
* `use-theme-color` → Accès aux couleurs du thème

---

## 🚀 Point d'entrée

Le fichier `app/_layout.tsx` est le point d'entrée de l'application :

* Configure le ThemeProvider
* Définit le Stack Navigator racine
* Gère le StatusBar

---

## ▶️ Lancer le projet

```bash
npm run start
```

Puis :

* `a` → Android
* `i` → iOS
* `w` → Web
* QR Code → Expo Go (mobile)

Autres commandes :

```bash
npm run android    # Lancer directement sur Android
npm run ios        # Lancer directement sur iOS
npm run web        # Lancer directement sur Web
npm run lint       # Vérifier le code
```

---

## 🔜 Évolutions prévues

Cette architecture permet d'ajouter facilement :

* 🔐 Authentification (JWT WordPress) → `src/api/auth.ts`
* 📰 Récupération des articles WP → `src/api/posts.ts`
* 🗄️ State management → `src/store/`
* 🔔 Notifications push → `src/utils/notifications.ts`
* 🎨 Thème personnalisé → `constants/theme.ts`
* 📱 Navigation avancée → `src/navigation/`

---

## ✅ Bonnes pratiques

* **Séparation des préoccupations** : Logique métier dans `src/`, routes dans `app/`
* **Composants réutilisables** : Centraliser dans `components/` ou `src/components/`
* **API centralisée** : Tous les appels API dans `src/api/`
* **State management** : Utiliser `src/store/` pour l'état global
* **Hooks personnalisés** : Logique réutilisable dans `src/hooks/`
* **File-based routing** : Profiter d'Expo Router pour la navigation

---

## 🏗️ Stack technique

* **React Native** 0.81.5
* **Expo** ~54.0.29
* **Expo Router** ~6.0.19 (file-based routing)
* **TypeScript** 5.9.2
* **React Navigation** (via Expo Router)
* **WordPress Headless** (API)

---

💡 Cette architecture est conçue pour être **scalable**, **maintenable** et prête pour un projet professionnel.
