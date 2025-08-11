# 🍽️ ReputAI - Gestion Automatique des Avis Google pour Restaurants

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Node.js](https://img.shields.io/badge/Node.js-18+-green.svg)](https://nodejs.org/)
[![Next.js](https://img.shields.io/badge/Next.js-15+-black.svg)](https://nextjs.org/)
[![NestJS](https://img.shields.io/badge/NestJS-10+-red.svg)](https://nestjs.com/)

> **Transformez vos avis Google en opportunités de fidélisation client avec l'IA**

## 🎯 Qu'est-ce que ReputAI ?

ReputAI est une solution complète de gestion des avis Google conçue spécifiquement pour les restaurants. Elle combine le scraping intelligent, la génération d'IA et la gestion de réputation pour vous aider à :

- **Automatiser** la récupération de vos avis Google
- **Générer** des réponses personnalisées et professionnelles
- **Gérer** votre ligne éditoriale et ton de marque
- **Publier** directement sur Google Business Profile
- **Analyser** l'impact de vos interactions

## 🚀 Fonctionnalités Principales

### 🔍 Scraping Intelligent
- Extraction automatique des avis depuis Google Maps
- Support des avis en plusieurs langues
- Gestion des erreurs et retry automatique
- Stockage local et en base de données

### 🤖 Génération IA
- Réponses personnalisées avec GPT-4
- Adaptation au ton de votre marque
- Instructions personnalisables
- Mode mock pour les tests

### 📱 Interface Moderne
- Dashboard unifié et responsive
- Gestion des avis et réponses
- Génération individuelle ou en lot
- Filtres et recherche avancés

### 🔒 Sécurité & Conformité
- Validation des entrées
- Protection contre la traversée de répertoires
- Gestion sécurisée des tokens
- Logs d'audit complets

## 🏗️ Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Frontend      │    │      API        │    │   Base de       │
│   (Next.js)     │◄──►│   (NestJS)      │◄──►│   Données       │
│                 │    │                 │    │   (PostgreSQL)  │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Scraping      │    │   OpenAI API    │    │   Stockage      │
│   (Playwright)  │    │   (GPT-4)       │    │   Local         │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

## 🛠️ Technologies Utilisées

### Backend
- **NestJS 10+** : Framework Node.js robuste et scalable
- **PostgreSQL** : Base de données relationnelle
- **Prisma** : ORM moderne et type-safe
- **Playwright** : Scraping web avec Chromium
- **OpenAI** : Génération de réponses avec GPT-4

### Frontend
- **Next.js 15** : Framework React avec App Router
- **TypeScript** : Typage statique pour la robustesse
- **Tailwind CSS** : Framework CSS utilitaire
- **Responsive Design** : Optimisé mobile et desktop

## 📋 Prérequis

- **Node.js** 18+ 
- **PostgreSQL** 14+
- **Compte OpenAI** avec clé API
- **Compte Google Business Profile** (optionnel)

## 🚀 Démarrage Rapide

### 1. Cloner le projet
```bash
git clone <repository-url>
cd reputai
```

### 2. Configuration de l'environnement
```bash
# Copier les fichiers d'environnement
cp api/.env.example api/.env
cp web/.env.local.example web/.env.local

# Configurer vos clés API
# api/.env
OPENAI_API_KEY="sk-..."
DATABASE_URL="postgresql://user:password@localhost:5432/reputai"

# web/.env.local
NEXT_PUBLIC_API_URL="http://localhost:3000"
```

### 3. Lancer l'API
```bash
cd api
npm install
npx prisma migrate dev
npm run start:dev
```

### 4. Lancer le Frontend
```bash
cd web
npm install
npm run dev
```

### 5. Accéder à l'application
- **API** : http://localhost:3000
- **Frontend** : http://localhost:3001

## 📖 Documentation

- **[API Documentation](api/README.md)** - Guide complet de l'API backend
- **[Frontend Documentation](web/README.md)** - Guide de l'interface utilisateur
- **[Architecture](docs/architecture.md)** - Détails techniques (à venir)
- **[API Reference](docs/api-reference.md)** - Référence des endpoints (à venir)

## 🔌 Utilisation

### Scraping d'Avis
1. Entrez l'URL Google Maps de votre restaurant
2. Définissez le nombre maximum d'avis à récupérer
3. Cliquez sur "Scrape & Save Local"

### Génération de Réponses
1. Chargez vos avis depuis un fichier local
2. Personnalisez le ton et les instructions
3. Générez des réponses individuelles ou en lot
4. Approuvez et publiez sur Google

### Gestion de la Marque
- Définissez votre ligne éditoriale
- Créez des templates de réponses
- Personnalisez le ton selon le contexte

## 🧪 Tests

```bash
# Tests API
cd api
npm run test
npm run test:e2e

# Tests Frontend
cd web
npm run test
npm run lint
```

## 🚀 Déploiement

### Développement
- Hot reload automatique
- Mode mock IA disponible
- Base de données locale

### Production
- Docker support
- Variables d'environnement sécurisées
- Monitoring et logs
- Scaling horizontal

## 🔮 Roadmap

### Phase 1 (1-2 mois) - MVP
- [x] Scraping Google Reviews
- [x] Génération IA des réponses
- [x] Interface utilisateur de base
- [ ] Intégration Google Business Profile
- [ ] Système d'approbation

### Phase 2 (3-6 mois) - Production
- [ ] Multi-plateformes (TripAdvisor, Yelp)
- [ ] Analytics et rapports
- [ ] API publique
- [ ] Mobile app

### Phase 3 (6+ mois) - Évolution
- [ ] IA multi-langues
- [ ] Prédiction de sentiment
- [ ] Marketplace de templates
- [ ] Intégrations tierces

## 💰 Modèles de Tarification

### Starter (Gratuit)
- 100 avis/mois
- Réponses basiques
- Support communautaire

### Professional (29€/mois)
- 1000 avis/mois
- Réponses personnalisées
- Support prioritaire
- Analytics de base

### Enterprise (Sur mesure)
- Volume illimité
- Fonctionnalités avancées
- Support dédié
- Intégrations personnalisées

## 🤝 Contribution

Nous accueillons les contributions ! Voir notre [guide de contribution](CONTRIBUTING.md) pour plus de détails.

1. Fork le projet
2. Créer une branche feature
3. Commit vos changements
4. Push vers la branche
5. Ouvrir une Pull Request

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.

## 📞 Support

- **Documentation** : [docs.reputai.com](https://docs.reputai.com)
- **Issues** : [GitHub Issues](https://github.com/reputai/reputai/issues)
- **Email** : support@reputai.com
- **Discord** : [Rejoindre la communauté](https://discord.gg/reputai)
- **Téléphone** : +33 1 XX XX XX XX

## 🙏 Remerciements

- **OpenAI** pour GPT-4
- **Google** pour l'API Business Profile
- **NestJS** et **Next.js** pour les frameworks
- **La communauté open source** pour les contributions

---

**ReputAI** - Votre réputation en ligne, gérée intelligemment.

*Fait avec ❤️ pour les restaurateurs du monde entier*
