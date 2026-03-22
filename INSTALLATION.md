# MailPro AI — Guide d'installation complet
## Add-in Outlook Desktop (Windows)

---

## 🗂️ Ce que tu as reçu

| Fichier | Rôle |
|---|---|
| `taskpane.html` | L'interface du panneau latéral dans Outlook |
| `manifest.xml` | Le fichier de configuration que lit Outlook |

---

## ⚙️ ÉTAPE 1 — Héberger le fichier HTML (obligatoire)

Outlook Desktop requiert que le fichier `taskpane.html` soit accessible via une URL **https://**. Deux options simples :

### Option A — GitHub Pages (gratuit, recommandé)
1. Crée un compte sur https://github.com si tu n'en as pas
2. Crée un nouveau dépôt (Repository), appelle-le `mailpro-ai`
3. Active **Settings → Pages → Source : main branch**
4. Upload le fichier `taskpane.html`
5. Ton URL sera : `https://TON-PSEUDO.github.io/mailpro-ai/taskpane.html`

### Option B — Netlify (encore plus simple)
1. Va sur https://netlify.com et crée un compte gratuit
2. Glisse-dépose le fichier `taskpane.html` dans le dashboard
3. Netlify te donne une URL https:// immédiatement

---

## 📝 ÉTAPE 2 — Mettre à jour le manifest.xml

Une fois que tu as ton URL https://, ouvre `manifest.xml` avec le Bloc-notes et remplace les **3 occurrences** de :

```
https://VOTRE-DOMAINE/taskpane.html
```

par ta vraie URL, par exemple :

```
https://mon-pseudo.github.io/mailpro-ai/taskpane.html
```

Sauvegarde le fichier.

---

## 📦 ÉTAPE 3 — Installer l'add-in dans Outlook

### Dans Outlook Desktop :
1. Ouvre Outlook
2. Clique sur **Fichier** (en haut à gauche)
3. Clique sur **Gérer les compléments** (ou Options → Compléments)
4. Une page web s'ouvre dans ton navigateur
5. Clique sur **➕ Ajouter un complément personnalisé**
6. Choisit **"Ajouter depuis un fichier..."**
7. Sélectionne ton fichier `manifest.xml`
8. Accepte l'avertissement de sécurité
9. ✅ Le complément est installé !

---

## 🚀 ÉTAPE 4 — Utiliser MailPro AI

1. Ouvre Outlook et **crée un nouveau mail** (ou Répondre)
2. Dans le ruban du haut, cherche le bouton **"✦ Améliorer le mail"**
3. Un panneau latéral s'ouvre à droite
4. **Écris ton mail** normalement dans le corps du message
5. Choisis ton ton (Professionnel, Formel, Concis, Auto)
6. Clique sur **"✦ Corriger & améliorer mon mail"**
7. L'IA analyse et réécrit ton mail en quelques secondes
8. Clique sur **"↩ Remplacer dans mon mail"** → c'est fait !

---

## 🔑 Note sur la clé API

Le fichier `taskpane.html` utilise l'API Claude d'Anthropic.
Dans le cadre de Claude.ai (interface web), l'authentification est gérée automatiquement.

Si tu utilises cet add-in en dehors de Claude.ai, tu auras besoin d'une clé API Anthropic :
- Crée un compte sur https://console.anthropic.com
- Génère une clé API
- Dans `taskpane.html`, ajoute dans les headers de la requête fetch :
  `"x-api-key": "ta-clé-ici"`

---

## 🛠️ Dépannage

| Problème | Solution |
|---|---|
| Le bouton n'apparaît pas | Redémarre Outlook après l'installation |
| Erreur "Impossible de lire le mail" | Clique dans le corps du mail avant d'appuyer sur le bouton |
| Panneau blanc | Vérifie que l'URL dans manifest.xml est correcte et accessible |
| Erreur connexion IA | Vérifie ta connexion internet |

---

*MailPro AI — Propulsé par Claude (Anthropic)*
