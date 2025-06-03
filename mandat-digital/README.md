# 🚗 Mandat Digital - CarLink

Application complète de digitalisation de mandat de vente automobile.

---

## 📁 Structure du projet

```
mandat-digital/
├── frontend/              → Application React (formulaire, admin, PDF, signature)
├── backend/               → API Express (fichiers, emails, sécurité JWT)
├── .env.example           → Variables d’environnement
└── README.md              → Guide complet d'installation et de déploiement
```

---

## 🚀 Déploiement

### 1. 📦 Frontend sur Vercel

#### Prérequis :
- Un compte GitHub
- Un compte Vercel : https://vercel.com/signup

#### Étapes :
1. Poussez le dossier `frontend/` sur GitHub
2. Allez sur [vercel.com](https://vercel.com), ajoutez un projet depuis GitHub
3. Configuration :
   - Framework : `React`
   - Build Command : `npm run build`
   - Output Directory : `dist`
   - Root Directory : `frontend`
4. Variables d’environnement :
   - `VITE_API_URL=https://votre-backend-railway.app`

---

### 2. 🛠 Backend sur Railway

#### Prérequis :
- Un compte Railway : https://railway.app

#### Étapes :
1. Créez un projet Railway
2. Ajoutez une base PostgreSQL : Plugins > PostgreSQL
3. Déployez le backend :
   - Soit depuis GitHub
   - Soit en uploadant les fichiers de `backend/`
4. Variables `.env` :
```
PORT=4000
DATABASE_URL=postgresql://...
JWT_SECRET=changez_cette_clé
ADMIN_USER=admin
ADMIN_PASS=adminpass
MAIL_USER=votreemail@gmail.com
MAIL_PASS=motdepasse_gmail_app
```
5. Migrations Prisma :
   ```
   npx prisma migrate deploy
   ```

---

## 🔑 Accès Admin

- URL : `/login`
- Identifiants : définis dans `.env` (`ADMIN_USER` / `ADMIN_PASS`)
- Après connexion, accès au tableau de bord `/admin`

---

## ✉️ Envoi d’emails

- Utilise Gmail via `nodemailer`
- Créez un mot de passe d’application dans votre compte Google

---

## 📄 Exemple `.env`

Voir : `.env.example`

---

## 🧪 Test local

```bash
cd frontend
npm install
npm run dev

cd ../backend
npm install
node server.js
```

---

## 🤝 Assistance

Développé pour CarLink, société de courtage automobile.
Pour tout besoin d’évolution ou assistance, contactez votre développeur.