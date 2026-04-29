# La Fiesta 25 – Guide d'utilisation

## Structure du projet

```
fiesta25/
├── index.html          ← page d'accueil (liste des albums)
├── album.html          ← page d'un album (ne pas modifier)
├── photos/
│   └── bemorgan/       ← dossier du 1er album
│       └── *.jpg/png   ← dépose tes photos ici
└── README.md           ← ce fichier
```

---

## ✅ Ajouter des photos à un album existant

1. **Copie tes photos** dans le bon dossier, ex: `photos/bemorgan/`
2. **Ouvre `album.html`** dans un éditeur de texte (Notepad, TextEdit...)
3. Cherche la section `ALBUMS_CONFIG` et ajoute les noms de fichiers :

```javascript
bemorgan: {
  name: "Bemorgan",
  tag: "Dimanche soir",
  photos: [
    "photo1.jpg",      ← ajoute chaque nom de fichier ici
    "photo2.jpg",
    "DSC_0042.jpg",
    ...
  ]
},
```

---

## ✅ Ajouter un nouvel album

### Étape 1 — Créer le dossier
Crée un dossier dans `photos/`, ex: `photos/photographe2/`
Dépose les photos dedans.

### Étape 2 — Déclarer l'album dans `index.html`
Ouvre `index.html`, trouve le tableau `ALBUMS` et ajoute :

```javascript
{
  folder: "photographe2",        ← nom du dossier
  name: "Nom Photographe",       ← nom affiché
  tag: "Samedi soir",            ← étiquette de l'album
  cover: "cover.jpg",            ← photo de couverture (optionnel)
  ready: true                    ← false = affiche "Bientôt disponible"
},
```

### Étape 3 — Déclarer les photos dans `album.html`
Ouvre `album.html`, trouve `ALBUMS_CONFIG` et ajoute :

```javascript
photographe2: {
  name: "Nom Photographe",
  tag: "Samedi soir",
  photos: [
    "img1.jpg",
    "img2.jpg",
    ...
  ]
},
```

---

## 🚀 Mettre en ligne gratuitement (GitHub Pages)

1. Crée un compte sur [github.com](https://github.com) (gratuit)
2. Crée un nouveau dépôt ("New repository"), nomme-le `fiesta25`
3. Upload tous les fichiers du projet
4. Va dans **Settings → Pages → Source → Deploy from branch → main**
5. Ton site sera dispo à : `https://ton-pseudo.github.io/fiesta25/`

### Partager un album
L'URL d'un album est toujours :
```
https://ton-pseudo.github.io/fiesta25/album.html?album=bemorgan
```

---

## 📌 Conseils

- **Format des photos** : JPG recommandé. Pour le web, redimensionne à 2000px max pour réduire le temps de chargement (tu peux garder les originaux séparément pour le ZIP).
- **Noms de fichiers** : évite les espaces et accents. Utilise des tirets : `bemorgan-001.jpg`
- **Couverture** : la première photo de la liste sera automatiquement la première à s'afficher.
