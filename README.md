# Site officiel de Droit+

Page de présentation et de téléchargement de l'application Android **Droit+** (Droit · Burkina & OHADA).
Site statique (HTML + CSS, sans dépendance externe), prêt pour **GitHub Pages**.

## Contenu du dossier

```
index.html              ← la page du site
Droit-Plus.apk          ← l'application (version 1.0, 3,3 Mo)
.nojekyll               ← indique à GitHub de servir les fichiers tels quels
assets/img/             ← logo, icônes, captures d'écran, image de partage
README.md               ← ce fichier
```

## Mettre le site en ligne (depuis le navigateur, sans ligne de commande)

1. Connecte-toi sur **github.com** et clique sur **New repository**.
2. Nom du dépôt : par exemple `droitplus`. Coche **Public**, puis **Create repository**.
3. Sur la page du dépôt, clique sur **uploading an existing file**.
4. Décompresse le .zip sur ton ordinateur, puis glisse **tout le contenu** du dossier `droitplus-site`
   (index.html, Droit-Plus.apk, .nojekyll, le dossier assets…) dans la fenêtre.
   Les fichiers doivent être à la racine du dépôt, pas dans un sous-dossier.
   *Le fichier `.nojekyll` est caché sur certains ordinateurs : s'il n'apparaît pas, ce n'est pas grave, le site fonctionne sans.*
5. Clique sur **Commit changes**.
6. Va dans **Settings → Pages**. Sous *Build and deployment*, choisis :
   *Source* : **Deploy from a branch**, *Branch* : **main** et **/ (root)**, puis **Save**.
7. Attends 1 à 2 minutes. L'adresse du site s'affiche en haut de la page Pages :
   `https://TON-PSEUDO.github.io/droitplus/`

> Astuce : si tu nommes le dépôt `TON-PSEUDO.github.io`, le site sera directement à l'adresse
> `https://TON-PSEUDO.github.io/`.

## Après la mise en ligne (recommandé)

**Aperçu sur WhatsApp / Facebook.** Pour qu'une belle image s'affiche quand tu partages le lien,
ouvre `index.html` sur GitHub (icône crayon) et remplace la ligne :

```html
<meta property="og:image" content="assets/img/og-image.jpg">
```

par l'adresse complète de ton site, par exemple :

```html
<meta property="og:image" content="https://TON-PSEUDO.github.io/droitplus/assets/img/og-image.jpg">
```

## Publier une nouvelle version de l'application

1. Renomme ton nouvel APK en **`Droit-Plus.apk`** (même nom exactement).
2. Sur GitHub : **Add file → Upload files**, dépose-le et valide : il remplace l'ancien.
3. Mets à jour dans `index.html` :
   - l'**empreinte SHA-256** (dans la section « Vérifier le fichier ») ;
   - la **version** et la **taille** (« Version 1.0 », « 3,3 Mo », qui apparaissent dans le haut de page et le bouton final).

Pour obtenir l'empreinte SHA-256 du nouvel APK :

- **Windows (PowerShell)** : `Get-FileHash Droit-Plus.apk -Algorithm SHA256`
- **macOS / Linux** : `shasum -a 256 Droit-Plus.apk`

Empreinte de la version actuelle (1.0) :
`7c803fee1506275af6d96852f6626d2cd905929dfc42b843a470928ff7c5b82e`

Pour que les utilisateurs puissent installer la mise à jour par-dessus l'ancienne version,
le nouvel APK doit être signé avec **la même clé** que la version 1.0 et avoir un `versionCode` plus élevé.

## Limites de taille sur GitHub

- Envoi par le navigateur : 25 Mo par fichier maximum (l'APK actuel fait 3,3 Mo).
- Si un jour l'APK dépasse 25 Mo, publie-le dans **Releases** (bouton *Create a new release*) et
  remplace `href="Droit-Plus.apk"` dans `index.html` par le lien de téléchargement de la release.
