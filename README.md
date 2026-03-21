# IArena Educative — Bibliothèque des Lives

Application web statique regroupant les 25 lives mensuels de la communauté IArena Educative (oct. 2023 – mars 2026).

## Déploiement sur GitHub Pages

1. Créer un repo GitHub (ex: `iarena-lives`)
2. Pousser le contenu de ce dossier sur la branche `main`
3. Dans Settings > Pages, sélectionner "Deploy from a branch" > `main` > `/ (root)`
4. Configurer le DNS OVH (voir ci-dessous)

## Configuration DNS OVH pour `lives.rochane.fr`

Dans l'espace client OVH > Zone DNS de `rochane.fr`, ajouter :

```
lives   CNAME   tonpseudo.github.io.
```

(Remplacer `tonpseudo` par ton username GitHub, avec le point final.)

Le fichier `CNAME` dans ce dossier contient déjà `lives.rochane.fr`.
GitHub configurera automatiquement le HTTPS (patience ~10 min).

## Mise à jour du contenu

Modifier le fichier `src/App.jsx` (tableau LIVES), rebuilder avec `npm run build`, copier le contenu de `dist/` dans le repo.
