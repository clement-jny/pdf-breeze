# Documentation du Projet PDFBreeze

## Description

**PDFBreeze** est un outil polyvalent permettant de manipuler des fichiers PDF de manière intuitive et rapide. Ce projet comprend trois principaux moyens d'utilisation :

1. **CLI** (Command Line Interface) : Une interface en ligne de commande qui permet de manipuler les fichiers PDF directement depuis un terminal.
2. **Webapp** : Une application web pour une interface utilisateur conviviale, intégrant les fonctionnalités du CLI en arrière-plan.
3. **Desktop App** : Une application de bureau autonome pour une utilisation hors ligne, basée sur la Webapp et le CLI.

### Fonctionnalités principales :

1. **Scission de PDF** : Découpe un fichier PDF en plusieurs fichiers distincts, chaque page devenant un nouveau fichier PDF.
2. **Conversion PDF vers Images** : Convertit automatiquement les fichiers PDF en images JPG.
3. **Support multiplateforme** : Compatible avec les systèmes Windows, macOS, et Linux.

## Structure du projet

```plaintext
pdf-breeze/
│
├── cli/                # CLI logic
│   ├── server/         # Backend logic for CLI
│   ├── utils/          # Helpers pour la manipulation de PDF
│   └── index.ts        # Point d'entrée CLI
│
├── www/                # Frontend (Web App)
│   ├── src/            # Source du code pour la Web App
│   │   ├── components/ # Composants UI
│   │   ├── pages/      # Pages de l'application
│   │   └── app.tsx     # Point d'entrée Web App
│   └── public/         # Fichiers publics
│
├── desktop/            # Application Desktop (Electron)
│   ├── src/            # Source Desktop App
│   ├── main.ts         # Processus principal (Electron)
│   └── renderer/       # Interface utilisateur (peut réutiliser la Webapp)
│
├── shared/             # Code partagé (Core logic)
│   ├── core/           # Fonctionnalités principales
│   ├── models/         # Modèles de données
│   └── config.ts       # Configurations globales
│
├── tests/              # Tests (unitaires, intégration, E2E)
├── scripts/            # Scripts utilitaires
├── package.json        # Dépendances et métadonnées
├── tsconfig.json       # Configuration TypeScript
└── README.md           # Documentation
```

## Prérequis

- **Node.js** version 16 ou supérieure
- **npm** ou **yarn**
- Bibliothèques nécessaires pour la manipulation de PDF :
  - PDF-lib
  - Sharp

## Installation et Utilisation

### Installation

1. Clonez le dépôt :

```bash
git clone https://github.com/ton-utilisateur/pdf-breeze.git
cd pdf-breeze
```

2. Installez les dépendances :

```bash
npm install
```

### Démarrer avec la CLI

1. Exécutez une commande simple pour scinder un PDF :

```bash
node ./cli/index.js split --input fichier.pdf --output ./output-directory
```

2. Convertissez les fichiers PDF en images :

```bash
node ./cli/index.js convert --input ./output-directory --output ./images
```

### Démarrer avec la Webapp

1. Lancez le serveur :

```bash
npm run dev:webapp
```

2. Accédez à l'interface : Ouvrez votre navigateur à l'adresse `http://localhost:3000`.

### Démarrer avec la Desktop App

1. Construisez et exécutez l'application :

```bash
npm run dev:desktop
```

## Fonctionnalités prévues

- Personnalisation des fichiers PDF :
  - Ajout de filigranes ou de signatures numériques.
- Optimisation des fichiers PDF :
  - Compression pour réduire la taille.
- Mode batch :
  - Support pour traiter plusieurs fichiers PDF simultanément.

## Contribution

Si vous souhaitez contribuer, créez une branche à partir de main, apportez vos modifications et proposez une Pull Request.

Avec PDFBreeze, la gestion de fichiers PDF n’a jamais été aussi simple ! 🚀
