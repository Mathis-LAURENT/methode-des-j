# Méthode des J : installation hors ligne sur téléphone

Ce dossier contient une application web installable (PWA) :

- `index.html` : l'application
- `manifest.webmanifest` : nom, icône et affichage plein écran
- `sw.js` : service worker qui met l'application en cache pour l'usage hors ligne
- `icons/` : icônes 192 et 512 px

Une PWA doit être servie en **HTTPS** : ouvrir `index.html` directement depuis les fichiers du téléphone ne suffit pas.
Il faut donc la mettre en ligne une fois (gratuit), puis l'installer depuis le téléphone.

## Étape 1 : mettre le dossier en ligne

### Option A : Netlify Drop (la plus simple, sans compte Git)

1. Décompressez `methode-des-j-pwa.zip` sur votre ordinateur.
2. Allez sur https://app.netlify.com/drop
3. Glissez le **dossier décompressé** (celui qui contient `index.html`) dans la zone indiquée.
4. Netlify vous donne une adresse du type `https://nom-aleatoire.netlify.app`. Notez-la.
   (Créer un compte gratuit permet de conserver le site et de choisir son nom.)

### Option B : GitHub Pages

1. Créez un dépôt public sur https://github.com (par exemple `methode-des-j`).
2. Cliquez sur « Add file » puis « Upload files » et déposez **le contenu** du dossier (`index.html`, `sw.js`, `manifest.webmanifest`, `icons/`).
3. Allez dans « Settings » puis « Pages ». Sous « Branch », choisissez `main` et le dossier `/ (root)`, puis « Save ».
4. Après une minute environ, l'application est disponible sur `https://VOTRE-NOM.github.io/methode-des-j/`.

## Étape 2 : installer sur le téléphone

### iPhone (Safari obligatoire)

1. Ouvrez l'adresse de votre site dans **Safari**.
2. Attendez que la page soit entièrement chargée (cela met l'application en cache).
3. Touchez le bouton Partager, puis « Sur l'écran d'accueil », puis « Ajouter ».

### Android (Chrome)

1. Ouvrez l'adresse de votre site dans **Chrome**.
2. Touchez le menu ⋮ puis « Installer l'application » (ou « Ajouter à l'écran d'accueil »).
3. Confirmez : l'icône « J+ » apparaît parmi vos applications.

## Étape 3 : vérifier le mode hors ligne

1. Ouvrez l'application une fois avec Internet.
2. Activez le mode avion et relancez l'application depuis son icône : elle doit s'ouvrir normalement.

## À savoir

- **Vos données** (cours, chapitres, progression) sont enregistrées dans le stockage local du téléphone. Elles ne sont pas synchronisées entre appareils.
- Si vous **videz les données du navigateur** ou **désinstallez l'application**, elles sont effacées.
- Sur iPhone, l'application installée sur l'écran d'accueil a son **propre stockage**, distinct de celui de Safari : commencez à l'utiliser une fois installée.
- **Mettre à jour l'application** : modifiez `index.html`, changez le numéro de version dans `sw.js` (`methode-des-j-v1` en `methode-des-j-v2`), puis remettez les fichiers en ligne. Fermez et rouvrez l'application pour recevoir la nouvelle version.
