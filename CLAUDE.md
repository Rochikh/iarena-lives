# IArena Lives — mémo projet

Site statique : **lives.rochane.fr** — bibliothèque des lives mensuels de la communauté IArena Éducative.
Hébergé en GitHub Pages (présence de `.nojekyll` + `CNAME`).

## ⚠️ Point crucial : il n'y a PAS de code source dans ce dépôt

Le dépôt ne contient que le **build compilé** (Vite/React) :

- `index.html` — coquille HTML, charge `assets/index-*.js`
- `assets/index-BYQyvpBD.js` — **bundle JS minifié sur une seule ligne** ⇒ c'est ici que vivent TOUTES les données des lives
- `CNAME`, `.nojekyll`

Le source React/Vite n'est versionné nulle part ici. **On édite donc directement le bundle minifié.**
(Si un jour le source réapparaît, reporter les changements là-bas, sinon le prochain build écrasera tout.)

## Où sont les données

Tableau JS nommé `Rn` dans le bundle. Chaque live = un objet. Repérer un live par `id:NN,date:"AAAA-MM-JJ"`.
Le dernier live est en fin de tableau, juste avant `}],Hu=[...`.

### Schéma d'un objet live

```js
{
  id: 26,
  date: "2026-05-28",                       // AAAA-MM-JJ
  title: "Live #26 — ...",
  subtitle: "...",
  speakers: ["Prénom Nom", ...],            // alimente le filtre global
  topics: ["...", ...],                       // tags, alimente le filtre global
  highlights: ["...", ...],                   // 1 entrée détaillée par intervention + 1 synthèse des échanges
  recording: "https://drive.google.com/file/d/XXX/view" | null,  // null = badge « Sans replay »
  notesUrl: null,                             // bouton « Notes » si renseigné
  visioUrl: "https://meet.google.com/...",  // bouton visio, visible UNIQUEMENT si live à venir
  resources: [{label:"...", url:"..."}, ...]  // optionnel : liens cliquables
}
```

### Logique d'affichage (déjà câblée dans le bundle)

- `r` = live à venir ⇔ `date + T23:00:00 > maintenant` (garde le badge « Prochain live » jusqu'à 21h Paris le jour J).
- **Live à venir** (`r` vrai) : badge « Prochain live », boutons « ▶ Rejoindre la visio » (si `visioUrl`) et « Ajouter à mon calendrier ».
- **Live passé** : ces boutons disparaissent automatiquement. Si `recording` est défini → bouton « ▶ Replay » ; sinon badge « Sans replay ».
- `notesUrl` → bouton « Notes ». `resources` → liste de liens.

## Procédure : mettre à jour le dernier live à partir d'un compte rendu (notes Gemini)

Cas typique : le live existait en mode « annonce de programme » (`recording:null`), la réunion a eu lieu,
l'utilisateur fournit les notes + le lien du replay (Google Drive).

1. Localiser l'objet : chercher `{id:NN,date:"..."` dans `assets/index-BYQyvpBD.js`.
2. Réécrire `title` / `subtitle` / `topics` pour refléter le contenu réel.
3. Récrire `highlights` : **une entrée détaillée par intervenant·e** (format « Prénom Nom — résumé… »)
   + une dernière entrée « Échanges — … » synthétisant les débats. (S'inspirer du style enrichi du Live #25.)
4. Compléter `speakers` (présentateur·rice·s + contributeur·rice·s majeur·e·s des débats).
5. Mettre `recording` = lien replay Google Drive (forme `https://drive.google.com/file/d/XXX/view`).
   Ajouter aussi une ressource « Replay du Live #NN » en tête de `resources` (pratique).
6. **Éditer via un script Python** (pas l'outil Edit ligne par ligne : la ligne minifiée est énorme).
   Construire la nouvelle chaîne avec `json.dumps(..., ensure_ascii=False)` pour les accents/apostrophes,
   puis `data[:start] + new + data[obj_end:]`. Attention à ne pas avaler le `]` qui ferme le tableau `Rn`
   (l'objet se termine par le `}` juste avant `],Hu=`).
7. **Valider la syntaxe** : `node -c assets/index-BYQyvpBD.js` doit dire OK.
8. Commit + push sur la branche de travail. Pas de PR sauf demande explicite.

## Ajouter un NOUVEAU live (à venir)

Insérer un nouvel objet en fin de tableau `Rn` (avant `}]`), avec `recording:null`, `notesUrl:null`,
`visioUrl` renseigné, `resources` optionnel. Incrémenter `id`. Les boutons visio/calendrier apparaîtront
automatiquement tant que le live est à venir.

## Détails utiles

- Bouton calendrier : généré par `Md(e)` → Google Calendar, créneau `T200000/T210000`, `ctz=Europe/Paris`.
- Format de date affiché : `Ad(e.date)` → ex. « 28 mai 2026 ».
- Branche de dev attendue (sessions Claude Code web) : voir la consigne de session ; ne jamais pousser sur `main` sans accord.
