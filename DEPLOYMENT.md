# Caddr - Application de Gestion de Routine Journalière

## 🚀 Déploiement sur Netlify

### Étapes de déploiement :

1. **Connectez votre dépôt GitHub à Netlify**
   - Allez sur [Netlify](https://app.netlify.com)
   - Cliquez sur "Add new site" > "Import an existing project"
   - Connectez votre dépôt GitHub

2. **Configurez les variables d'environnement**
   - Dans Netlify, allez dans "Site configuration" > "Environment variables"
   - Ajoutez la variable suivante :
     - `VITE_GEMINI_API_KEY` = votre clé API Gemini

3. **Configuration de build (normalement automatique grâce à netlify.toml)**
   - Build command: `npm install && npm run build`
   - Publish directory: `dist`

4. **Déployez**
   - Netlify va automatiquement déployer votre site

### 📝 Obtenir une clé API Gemini

1. Allez sur [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Créez une nouvelle clé API
3. Copiez la clé et ajoutez-la dans les variables d'environnement Netlify

### 🔧 Développement local

```bash
# Installer les dépendances
npm install

# Créer un fichier .env.local à la racine
echo "VITE_GEMINI_API_KEY=votre_clé_api" > .env.local

# Lancer le serveur de développement
npm run dev
```

### 🐛 Problèmes résolus

- ✅ Structure de fichiers corrigée (dossier `src/`)
- ✅ Configuration Vite optimisée
- ✅ Variables d'environnement corrigées (utilisation de `import.meta.env`)
- ✅ Configuration Netlify ajoutée
- ✅ Redirections SPA configurées

### 📦 Structure du projet

```
caddr/
├── src/
│   ├── index.tsx          # Point d'entrée
│   ├── App.tsx            # Composant principal
│   ├── types.ts           # Types TypeScript
│   ├── utils.ts           # Fonctions utilitaires
│   └── services/
│       └── geminiService.ts  # Service API Gemini
├── index.html
├── package.json
├── vite.config.ts
├── netlify.toml           # Configuration Netlify
└── .env.example           # Exemple de variables d'environnement
```

### ⚠️ Important

- Ne jamais commit le fichier `.env.local` ou `.env` (ils sont dans .gitignore)
- Toujours préfixer les variables d'environnement Vite avec `VITE_`
- La clé API Gemini doit être configurée dans Netlify pour que l'app fonctionne en production
