# 🤝 Guide de Contribution - ReputAI

Merci de votre intérêt pour contribuer à ReputAI ! Ce guide vous aidera à comprendre comment participer au développement de cette solution de gestion des avis Google pour restaurants.

## 📋 Table des Matières

- [Code de Conduite](#code-de-conduite)
- [Comment Contribuer](#comment-contribuer)
- [Configuration de l'Environnement](#configuration-de-lenvironnement)
- [Standards de Code](#standards-de-code)
- [Tests](#tests)
- [Pull Requests](#pull-requests)
- [Rapport de Bugs](#rapport-de-bugs)
- [Demande de Fonctionnalités](#demande-de-fonctionnalités)
- [Questions et Support](#questions-et-support)

## 📜 Code de Conduite

### Notre Engagement

En participant à ce projet, vous vous engagez à maintenir un environnement ouvert et accueillant pour tous, peu importe l'âge, la taille, le handicap, l'ethnicité, l'identité et l'expression de genre, le niveau d'expérience, l'éducation, le statut socio-économique, la nationalité, l'apparence personnelle, la race, la religion ou l'identité et l'orientation sexuelles.

### Nos Standards

Exemples de comportements qui contribuent à créer un environnement positif :

- Utiliser un langage accueillant et inclusif
- Respecter les différents points de vue et expériences
- Accepter gracieusement la critique constructive
- Se concentrer sur ce qui est le mieux pour la communauté
- Faire preuve d'empathie envers les autres membres

Exemples de comportements inacceptables :

- L'utilisation de langage ou d'imagerie sexualisés
- Le trolling, les commentaires insultants/désobligeants
- Le harcèlement public ou privé
- Publier des informations privées d'autrui
- Autres comportements qui pourraient être considérés comme inappropriés

## 🚀 Comment Contribuer

### Types de Contributions

Nous accueillons différents types de contributions :

- **🐛 Bug Reports** : Signaler des problèmes
- **💡 Feature Requests** : Proposer de nouvelles fonctionnalités
- **📝 Documentation** : Améliorer la documentation
- **🧪 Tests** : Ajouter ou améliorer les tests
- **🔧 Code** : Corriger des bugs ou ajouter des fonctionnalités
- **🎨 UI/UX** : Améliorer l'interface utilisateur
- **🌐 Localisation** : Traduire l'application

### Processus de Contribution

1. **Fork** le projet
2. **Clone** votre fork localement
3. **Créez** une branche pour votre contribution
4. **Développez** votre fonctionnalité
5. **Testez** votre code
6. **Commitez** vos changements
7. **Poussez** vers votre fork
8. **Ouvrez** une Pull Request

## ⚙️ Configuration de l'Environnement

### Prérequis

- Node.js 18+
- PostgreSQL 14+
- Git
- Docker (optionnel)

### Installation

```bash
# 1. Fork et clone
git clone https://github.com/votre-username/reputai.git
cd reputai

# 2. Installer les dépendances
cd api && npm install
cd ../web && npm install

# 3. Configuration de l'environnement
cp api/.env.example api/.env
cp web/.env.local.example web/.env.local

# 4. Configurer la base de données
cd api
npx prisma migrate dev
npx prisma generate

# 5. Lancer les services
npm run start:dev  # Dans api/
npm run dev         # Dans web/
```

### Avec Docker

```bash
# Lancer tous les services
docker-compose up -d

# Voir les logs
docker-compose logs -f api
```

## 📏 Standards de Code

### Général

- **Lisibilité** : Le code doit être facile à lire et à comprendre
- **Consistance** : Suivre les conventions établies dans le projet
- **Documentation** : Commenter le code complexe
- **Tests** : Toute nouvelle fonctionnalité doit être testée

### TypeScript/JavaScript

- Utiliser **TypeScript** strict
- Préférer les **fonctions fléchées** pour les callbacks
- Utiliser **const** et **let** au lieu de **var**
- Utiliser **async/await** au lieu de **Promises.then()**
- Préférer les **template literals** aux concaténations

### NestJS (Backend)

- Suivre l'architecture **modulaire**
- Utiliser les **decorators** appropriés
- Implémenter la **validation** des DTOs
- Gérer les **erreurs** de manière appropriée
- Utiliser les **guards** et **interceptors**

### Next.js (Frontend)

- Utiliser l'**App Router**
- Préférer les **Server Components** quand possible
- Utiliser les **hooks** React appropriés
- Implémenter la **gestion d'état** de manière efficace
- Optimiser les **performances** (lazy loading, etc.)

### Formatage

```bash
# Backend
cd api
npm run format
npm run lint

# Frontend
cd web
npm run format
npm run lint
```

## 🧪 Tests

### Backend (NestJS)

```bash
cd api

# Tests unitaires
npm run test

# Tests e2e
npm run test:e2e

# Couverture de code
npm run test:cov

# Tests avec watch mode
npm run test:watch
```

### Frontend (Next.js)

```bash
cd web

# Tests unitaires
npm run test

# Tests e2e
npm run test:e2e

# Tests de types
npm run type-check

# Tests de linting
npm run lint
```

### Standards de Tests

- **Couverture minimale** : 80%
- **Tests unitaires** : Pour chaque service/méthode
- **Tests d'intégration** : Pour les endpoints API
- **Tests e2e** : Pour les workflows complets
- **Mocks** : Pour les dépendances externes

## 🔀 Pull Requests

### Avant de Soumettre

- [ ] Votre code suit les standards du projet
- [ ] Vous avez ajouté des tests pour les nouvelles fonctionnalités
- [ ] Tous les tests passent
- [ ] Vous avez mis à jour la documentation
- [ ] Votre PR résout un problème ou ajoute une fonctionnalité

### Template de PR

```markdown
## Description
Brève description des changements

## Type de changement
- [ ] Bug fix
- [ ] Nouvelle fonctionnalité
- [ ] Breaking change
- [ ] Documentation

## Tests
- [ ] Tests unitaires passent
- [ ] Tests e2e passent
- [ ] Tests manuels effectués

## Checklist
- [ ] Code formaté avec Prettier
- [ ] Linting sans erreurs
- [ ] Tests ajoutés/modifiés
- [ ] Documentation mise à jour

## Screenshots (si applicable)
```

### Processus de Review

1. **Automatique** : Tests et linting
2. **Review** : Au moins un maintainer doit approuver
3. **Merge** : Après approbation et résolution des conflits

## 🐛 Rapport de Bugs

### Template de Bug Report

```markdown
## Description du Bug
Description claire et concise du bug

## Étapes pour Reproduire
1. Aller à '...'
2. Cliquer sur '...'
3. Faire défiler jusqu'à '...'
4. Voir l'erreur

## Comportement Attendu
Description claire de ce qui devrait se passer

## Comportement Actuel
Description de ce qui se passe actuellement

## Screenshots
Si applicable, ajoutez des captures d'écran

## Environnement
- OS: [ex: iOS, Windows, macOS]
- Navigateur: [ex: Chrome, Safari]
- Version: [ex: 22]
- Version de l'API: [ex: 1.0.0]

## Informations Supplémentaires
Toute autre information pertinente
```

## 💡 Demande de Fonctionnalités

### Template de Feature Request

```markdown
## Résumé
Description claire et concise de la fonctionnalité souhaitée

## Motivation
Pourquoi cette fonctionnalité est-elle nécessaire ?

## Propositions de Solution
Description des solutions envisagées

## Alternatives Considérées
Autres solutions ou fonctionnalités alternatives

## Informations Supplémentaires
Captures d'écran, maquettes, etc.
```

## ❓ Questions et Support

### Ressources

- **Documentation** : [docs.reputai.com](https://docs.reputai.com)
- **Issues** : [GitHub Issues](https://github.com/reputai/reputai/issues)
- **Discussions** : [GitHub Discussions](https://github.com/reputai/reputai/discussions)
- **Email** : dev@reputai.com

### Communauté

- **Discord** : [Rejoindre le serveur](https://discord.gg/reputai)
- **Twitter** : [@ReputAI](https://twitter.com/ReputAI)
- **LinkedIn** : [ReputAI](https://linkedin.com/company/reputai)

## 🏆 Reconnaissance

### Contributeurs

Les contributeurs sont reconnus dans :

- Le fichier [CONTRIBUTORS.md](CONTRIBUTORS.md)
- La page "À propos" de l'application
- Les releases GitHub
- La documentation

### Badges

- **First Contribution** : Première PR acceptée
- **Bug Hunter** : 5+ bugs corrigés
- **Feature Developer** : 3+ fonctionnalités ajoutées
- **Documentation Hero** : Améliorations significatives de la doc
- **Test Champion** : Couverture de tests élevée

## 📄 Licence

En contribuant, vous acceptez que vos contributions soient sous la même licence que le projet (MIT).

## 🙏 Remerciements

Merci à tous les contributeurs qui rendent ReputAI meilleur chaque jour !

---

**Ensemble, transformons la gestion des avis Google pour les restaurants ! 🍽️✨**
