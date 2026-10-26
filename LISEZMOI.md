# Sax Trainer — installation

## Contenu du dossier

| Fichier | Rôle |
|---|---|
| `index.html` | Toute l'appli (HTML + CSS + JS, aucune dépendance) |
| `manifest.webmanifest` | Nom, couleurs, mode plein écran, portrait |
| `sw.js` | Service worker : cache hors ligne (cache-first, versionné) |
| `icon-180.png`, `icon-192.png`, `icon-512.png` | Icônes (déjà générées) |
| `icon.svg` | Source de l'icône, si tu veux la modifier |

## 1. Héberger (gratuit, HTTPS)

**Netlify Drop (le plus simple)**
1. Va sur https://app.netlify.com/drop
2. Glisse-dépose **le dossier entier** `sax-trainer`.
3. Netlify te donne une adresse en `https://…netlify.app`. Crée un compte gratuit pour qu'elle reste en ligne durablement.

**Retirer le badge « Powered by Netlify »** : depuis le 19 août 2026, Netlify l'ajoute aux nouveaux sites du plan gratuit. Pour le couper : sur Netlify, ouvre ton projet → **Project configuration → General → Powered by Netlify badge** → désactive → Save. Pas besoin de redéployer. Si l'option n'apparaît pas sur ton compte, GitHub Pages n'ajoute aucun badge.

**Ou GitHub Pages** : crée un dépôt, envoie les fichiers à la racine, puis Settings → Pages → branche `main`.

## 2. Installer sur l'iPhone

1. Ouvre l'adresse dans **Safari** (pas Chrome).
2. Bouton **Partager** → **« Sur l'écran d'accueil »** → Ajouter.
3. Lance l'appli **depuis l'icône** : plein écran, et elle marche ensuite sans connexion.

## Bon à savoir

- **Tes données restent sur le téléphone**, liées à l'appli installée. Si tu la supprimes de l'écran d'accueil, elles sont effacées. Fais un **export** de temps en temps (Bibliothèque → Données → Exporter → « Enregistrer dans Fichiers » / iCloud). L'appli te le rappelle après 30 jours sans export.
- **Le métronome marche aussi en mode silencieux.** Si tu n'entends rien, monte le volume « média » de l'iPhone.
- **Mettre à jour l'appli** : modifie les fichiers, change `VERSION` dans `sw.js` (ex. `'v2'`), puis redépose le dossier. Ferme et relance l'appli deux fois pour voir la nouvelle version.
- **Régler le tirage** : les constantes (15, 11, 0,5, 30) sont dans l'objet `CONFIG` en haut du script de `index.html`. La fonction `computeWeights` se teste dans la console : `SaxTrainer.computeWeights(...)`.
- **Modifier l'icône** : édite `icon.svg`, puis exporte-le en PNG 180, 192 et 512 px (par ex. sur https://svgtopng.com ou avec `rsvg-convert -w 180 icon.svg -o icon-180.png`).
