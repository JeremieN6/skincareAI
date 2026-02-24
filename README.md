# SkinAI — Diagnostic de peau par Intelligence Artificielle

Application web permettant d'analyser sa peau via l'IA et d'obtenir un diagnostic personnalisé avec des conseils et recommandations de produits.

## Fonctionnalités

- **Diagnostic IA** : Upload de 1 à 3 photos, analyse par Claude (Anthropic) avec vision
- **3 résultats structurés** : Diagnostic dermatologique, conseils de vie, produits recommandés
- **Questions de suivi** : Si les photos sont insuffisantes, l'IA pose des questions complémentaires
- **Système freemium** : 3 diagnostics gratuits/mois, plan Premium illimité
- **Blog** : 4 articles sur les soins de la peau
- **Responsive** : Design mobile-first

## Stack technique

- Vue.js 3 (Composition API, `<script setup>`)
- Tailwind CSS v3
- Vue Router + Pinia
- Anthropic API (Claude avec vision)
- Vite

## Installation

```bash
# Cloner le projet
git clone <url-du-repo>
cd skincareapp

# Installer les dépendances
npm install

# Configurer la clé API
# Créer un fichier .env à la racine avec:
# VITE_ANTHROPIC_API_KEY=sk-ant-votre-cle-api

# Lancer en développement
npm run dev

# Build de production
npm run build
```

## Configuration

1. Créer un compte sur [console.anthropic.com](https://console.anthropic.com)
2. Générer une clé API
3. Copier le fichier `.env` et y ajouter votre clé :

```
VITE_ANTHROPIC_API_KEY=sk-ant-xxxxxxxx
```

## Structure du projet

```
src/
├── assets/data/articles.json        # Articles du blog
├── components/
│   ├── layout/                      # NavBar, Footer
│   ├── landing/                     # Sections de la landing page
│   ├── diagnostic/                  # Composants du diagnostic
│   ├── blog/                        # Composants du blog
│   └── ui/                          # Composants UI réutilisables
├── views/                           # Pages principales
├── services/skinApi.js              # Service API Anthropic
├── stores/auth.js                   # Store Pinia (freemium)
└── router/index.js                  # Configuration des routes
```

## Avertissement médical

SkinAI est un outil d'aide à l'analyse cutanée basé sur l'intelligence artificielle. Il ne constitue en aucun cas un diagnostic médical et ne remplace pas la consultation d'un dermatologue ou d'un professionnel de santé qualifié.
