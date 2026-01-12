# 🚀 CLI Perso - Générateur de Projets Full-Stack

CLI personnalisée pour créer rapidement des projets full-stack avec ton stack préféré.

## ✨ Fonctionnalités

- 🎨 **Choix du Frontend** : SolidJS, Next.js, React, Vue.js
- 🏗️ **Choix du Backend** : NestJS, NestJS+Prisma, Hono, Hono+Prisma, Express, Express+Prisma
- 🗄️ **Base de données** : PostgreSQL, MariaDB, SQLite, ou aucune
- 🐳 **Docker Compose** : Configuration automatique pour les bases de données
- 📦 **Installation automatique** : Option d'installer les dépendances directement

## 📋 Prérequis

- Node.js 18+ ou Bun
- Docker (optionnel, pour les bases de données)

## 🔧 Installation

```bash
npm i -g dualsync
# ou
bun i -g dualsync
```

## 🚀 Utilisation

```bash
dual new <nom-du-projet>
```

### Exemple

```bash
dual new mon-app
```

La CLI te guidera à travers les choix :
1. **Frontend** : Quel framework frontend ?
2. **Backend** : Quel framework backend ?
3. **Database** : Quelle base de données ?
4. **Installation** : Installer les dépendances maintenant ?

## 📁 Structure Générée

```
mon-app/
├── frontend/           # Application frontend
│   ├── package.json
│   └── src/
├── backend/            # Application backend
│   ├── package.json
│   ├── src/
│   ├── prisma/        # Si Prisma est sélectionné
│   └── .env.example
├── docker-compose.yml  # Si une base de données est sélectionnée
└── .gitignore
```

## 🎯 Templates Disponibles

### Frontend
- **SolidJS** - Framework réactif et performant
- **Next.js** - Framework React avec SSR/SSG
- **React** - React Router v7
- **Vue.js** - Framework progressif avec Vite

### Backend
- **NestJS** - Framework enterprise-grade
- **NestJS + Prisma** - NestJS avec ORM Prisma 7
- **Hono** - Framework ultra-léger pour Bun
- **Hono + Prisma** - Hono avec ORM Prisma 7
- **Express** - Framework minimaliste (architecture MVC)
- **Express + Prisma** - Express avec ORM Prisma 7

### Bases de Données
- **PostgreSQL** - Base de données relationnelle robuste
- **MariaDB** - Fork MySQL performant
- **SQLite** - Base de données embarquée
- **Aucune** - Pas de base de données

## 🐳 Utilisation Docker

Si tu as sélectionné une base de données, un fichier `docker-compose.yml` est généré :

```bash
cd mon-app
docker-compose up -d
```

## 📝 Configuration Prisma

Pour les backends avec Prisma :

```bash
cd backend

# Copier le fichier .env.example
cp .env.example .env

# Modifier DATABASE_URL dans .env

# Générer le client Prisma
npm run db:generate

# Pousser le schéma vers la DB
npm run db:push

# Ouvrir Prisma Studio
npm run db:studio
```

## 🏃 Démarrer le Projet

### Frontend
```bash
cd mon-app/frontend
npm run dev        # Démarre sur http://localhost:5173
```

### Backend
```bash
cd mon-app/backend
npm run dev        # Démarre sur http://localhost:3000
```

## 🛠️ Scripts Disponibles

### Backend (avec Prisma)
- `npm run dev` - Mode développement
- `npm run build` - Build production (si disponible)
- `npm run db:generate` - Générer client Prisma
- `npm run db:push` - Pousser schéma vers DB
- `npm run db:migrate` - Créer migration
- `npm run db:studio` - Ouvrir Prisma Studio

## 🔒 Variables d'Environnement

Chaque backend avec base de données inclut un fichier `.env.example` :

```env
DATABASE_URL="postgresql://user:password@localhost:5432/my_database"
PORT=3000
NODE_ENV=development
```

## 📦 Architecture

### Backend Express/Express+Prisma
Structure MVC complète :
- `controllers/` - Gestion des requêtes/réponses
- `services/` - Logique métier
- `routes/` - Définition des routes
- `src/db.ts` - Client Prisma (si applicable)

### Backend Hono/Hono+Prisma
Architecture légère et performante optimisée pour Bun

### Backend NestJS/NestJS+Prisma
Architecture modulaire enterprise avec dependency injection

## 🤝 Contribution

N'hésite pas à personnaliser les templates selon tes besoins !

## 📄 Licence

ISC
