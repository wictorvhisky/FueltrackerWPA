# ⛽ FuelTrack

Application web progressive (PWA) monopage pour inventorier les pleins de carburant par véhicule.

## Fonctionnalités

- 📸 **Photo du compteur** : Prenez une photo, l'OCR (Tesseract.js) tente d'extraire automatiquement le volume et le prix
- 🚗 **Multi-véhicules** : Gérez plusieurs véhicules avec immatriculation et type de carburant
- 📍 **Localisation GPS** : Enregistrement automatique de la position
- 📅 **Date/Heure auto** : Horodatage automatique de chaque plein
- 📊 **Statistiques** : Synthèses mensuelles et annuelles avec graphiques
- 💾 **Stockage local** : Toutes les données restent sur votre appareil
- 📥 **Export** : CSV et JSON pour sauvegardes ou analyses externes
- 🔌 **Mode hors-ligne** : Fonctionne sans connexion grâce au Service Worker

## Déploiement

### Option 1 : GitHub Pages (gratuit)
1. Créez un nouveau repository sur GitHub
2. Uploadez les 3 fichiers (`index.html`, `manifest.json`, `sw.js`)
3. Allez dans Settings > Pages > Source : Deploy from a branch > main
4. Votre app est disponible en quelques minutes à `https://votre-user.github.io/nom-repo/`

### Option 2 : Netlify Drop (gratuit)
1. Allez sur [netlify.com/drop](https://netlify.com/drop)
2. Glissez-déposez le dossier contenant les 3 fichiers
3. L'app est déployée instantanément avec HTTPS

### Option 3 : Serveur local
```bash
python3 -m http.server 8000
# ou
npx serve .
```
Puis ouvrez `http://localhost:8000`

### Option 4 : Docker
```dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
EXPOSE 80
```

## Installation sur mobile

1. Ouvrez l'URL de l'app dans Chrome/Safari
2. Appuyez sur "Ajouter à l'écran d'accueil" / "Installer"
3. L'app s'ouvre en plein écran comme une application native

## Structure des fichiers

```
.
├── index.html      # Application complète (HTML + CSS + JS)
├── manifest.json   # Configuration PWA
├── sw.js           # Service Worker (cache + offline)
└── README.md       # Ce fichier
```

> **Note** : L'application utilise Tesseract.js via CDN pour l'OCR. Une connexion internet est nécessaire pour le premier chargement de cette librairie, mais l'app fonctionne ensuite hors-ligne.
