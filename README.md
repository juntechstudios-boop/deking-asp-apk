# Application Android de Deking Asp

Application d'écoute (musiques, clips, actus, contact) avec un espace admin protégé.
Données et fichiers : Supabase (projet « Deking Asp »). Application : Capacitor (vraie app Android).

## 1. Créer le compte admin (une seule fois)

1. Ouvre https://supabase.com/dashboard/project/ztcjgxaiiswutvcwdtsr/auth/users
2. **Add user** → **Create new user**
3. E-mail : `juntechstudios@gmail.com`, choisis un mot de passe, **coche « Auto Confirm User »**.

Seul cet e-mail a le droit de publier. Même si quelqu'un crée un autre compte, il ne pourra rien modifier.

## 2. Obtenir l'APK sans rien installer sur ton ordinateur (GitHub)

1. Crée un dépôt GitHub (privé) et envoie-y tous les fichiers de ce dossier (le dossier `.github` compris).
2. Onglet **Actions** → **Construire l'APK Android** → **Run workflow**.
3. Après environ 5 minutes, ouvre l'exécution terminée et télécharge **deking-asp-apk** (en bas de page).
4. Dézippe, envoie `app-debug.apk` sur le téléphone, ouvre-le et autorise l'installation.

## 3. Ou avec Android Studio

```
npm install
npx cap add android
npx cap sync android
npx cap open android
```
Puis dans Android Studio : **Build > Build APK(s)**. (Node 22 et JDK 21 requis.)

## Utiliser l'espace admin

Dans l'app, appuie **5 fois rapidement sur le logo DEKING ASP** en haut à gauche : l'écran de connexion apparaît.
Après connexion, un cadenas s'affiche en haut à droite. Les fans ne voient jamais cette entrée.

Fichiers : 50 Mo maximum chacun. Pour un gros clip, colle plutôt un lien YouTube.

## Structure

- `www/` : l'application (index.html, app.js, style.css, supabase.js, config.js)
- `capacitor.config.json` : nom et identifiant de l'app (`com.dekingasp.app`)
- `.github/workflows/apk.yml` : construction automatique de l'APK

## Limites actuelles

- C'est un APK de test (« debug »). Pour le Play Store, il faudra un APK signé (compte développeur Google à 25 $).
- Icône par défaut de Capacitor, à remplacer.
- Si la lecture s'arrête quand l'écran se verrouille, il faudra ajouter un plugin de lecture en arrière-plan.
- Supabase gratuit : 1 Go de stockage et 5 Go de transfert par mois. Si l'app devient populaire, il faudra passer à une offre payante.
