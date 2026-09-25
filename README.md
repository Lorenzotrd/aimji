# Aimji Studio

Site vitrine d'Aimji Studio, maison digitale du luxe.

- `index.html` : page complète (HTML, CSS, JS, sans dépendance)
- `hero-scrub.mp4` : film des 9 univers, piloté par le scroll (encodé avec une image clé toutes les 4 images pour un scrub fluide)
- `poster.jpg` : première image du film

## Mettre en ligne

Déploiement statique, aucun build. Sur Vercel : importer le dépôt, framework "Other", pas de commande de build.

## Remplacer le film

Réencoder la nouvelle vidéo avant de la déposer :

```
ffmpeg -i source.mp4 -an -c:v libx264 -preset slow -crf 25 -g 4 -keyint_min 4 -sc_threshold 0 -pix_fmt yuv420p -movflags +faststart hero-scrub.mp4
```

Les timings des univers sont dans le tableau `U` du script de `index.html` (secondes de début et de fin).
