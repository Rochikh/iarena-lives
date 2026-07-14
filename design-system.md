# Design System — d'après Bruxelles Formation

Système de design reconstitué à partir de l'identité visuelle de
**[bruxellesformation.brussels](https://www.bruxellesformation.brussels/)** et de sa
[charte graphique officielle (v1, 2024)](https://www.bruxellesformation.brussels/wp-content/uploads/2024/11/Charte-graphique_Bruxelles-Formation_web.pdf).

> **Note de provenance.** Le domaine officiel étant inaccessible depuis l'environnement de
> travail (politique d'egress → 403), les valeurs ci-dessous ont été reconstituées à partir de
> sources publiques (charte graphique, Brandfetch, recherches). Les **10 couleurs de base** et la
> **typographie** sont conformes à la charte ; les **échelles de nuances (niveaux 1→4)** et les
> **gris neutres** sont *dérivés* (approximation cohérente) — à recaler sur le PDF officiel si un
> accès direct est possible.

---

## 1. Principe directeur

L'identité de Bruxelles Formation repose sur un **logo en « touches de piano »** multicolore.
Les touches reprennent un **spectre colorimétrique** progressif et symbolisent la **diversité des
formations et des parcours**. Le système visuel en découle :

- **Bleu + blanc** = socle institutionnel (couleur primaire de marque).
- **10 couleurs** issues du spectre = système d'accentuation / catégorisation.
- Ton **clair, ouvert, pédagogique** : beaucoup de blanc, aplats de couleur francs, typographie
  contemporaine.

---

## 2. Couleurs

### 2.1 Palette de marque (10 couleurs officielles)

Chaque teinte existe en **4 niveaux** dans la charte, du plus foncé (niveau 1) au plus clair
(niveau 4). Le niveau 2 correspond à la teinte de référence.

| Couleur    | Réf. (niv. 2) | Niv. 1 (foncé) | Niv. 3 (clair) | Niv. 4 (très clair) |
|------------|---------------|----------------|----------------|---------------------|
| Jaune      | `#edcb0c`     | `#9a8408`      | `#f5e279`      | `#fcf6d3`           |
| Vert       | `#4eae33`     | `#337121`      | `#9ed28f`      | `#dff0da`           |
| Turquoise  | `#47b7a4`     | `#2e776b`      | `#9ad7cd`      | `#def2ef`           |
| **Bleu**   | `#1c5ea9`     | `#123d6e`      | `#82a6d0`      | `#d6e2f0`           |
| Mauve      | `#524797`     | `#352e62`      | `#a09ac6`      | `#e0deec`           |
| Violet     | `#3f2880`     | `#291a53`      | `#9589b9`      | `#dcd8e8`           |
| Rose       | `#f296ab`     | `#9d626f`      | `#f8c5d1`      | `#fdecf0`           |
| Fuchsia    | `#e03134`     | `#922022`      | `#ee8e8f`      | `#f9dada`           |
| Rouge      | `#900b0d`     | `#5e0708`      | `#c2797a`      | `#ebd3d3`           |
| Orange     | `#f5810c`     | `#9f5408`      | `#faba79`      | `#fde8d3`           |

> Les niveaux 1/3/4 sont dérivés. Le **Bleu `#1c5ea9`** est la couleur institutionnelle principale.

### 2.2 Couleurs sémantiques (rôles)

| Rôle                 | Valeur      | Usage                                             |
|----------------------|-------------|---------------------------------------------------|
| Primaire             | `#1c5ea9`   | Marque, liens, boutons principaux, en-têtes       |
| Primaire (hover)     | `#123d6e`   | État survol/actif du primaire                     |
| Primaire (surface)   | `#d6e2f0`   | Fonds légers, encadrés, badges bleus              |
| Accent               | `#f5810c`   | Appels à l'action secondaires, mise en avant      |
| Succès               | `#4eae33`   | Validation, statut positif                        |
| Alerte / erreur      | `#e03134`   | Erreurs, avertissements forts                     |
| Info                 | `#47b7a4`   | Messages informatifs, tags neutres-positifs       |

### 2.3 Neutres (dérivés)

| Token          | Valeur      | Usage                                  |
|----------------|-------------|----------------------------------------|
| `ink-900`      | `#111827`   | Texte principal sur fond clair         |
| `ink-700`      | `#374151`   | Texte courant                          |
| `ink-500`      | `#6b7280`   | Texte secondaire, légendes             |
| `line-200`     | `#e5e7eb`   | Bordures, séparateurs                  |
| `surface-100`  | `#f5f7fa`   | Fond de section alterné                 |
| `surface-0`    | `#ffffff`   | Fond principal                          |

### 2.4 Règles d'usage couleur

- **Fond clair** → logo en version couleur ; **fond coloré/photo** → logo en blanc.
- Décliner un document en **camaïeu monochrome** d'une des 10 teintes pour garder l'unité (comme
  les gabarits PowerPoint officiels).
- Garder le **bleu + blanc** comme base ; les autres couleurs servent d'accents/catégories, pas de
  fond dominant.
- Viser un contraste **AA** minimum (texte ≥ 4.5:1) : sur les teintes vives (jaune, rose,
  turquoise clair), écrire en `ink-900`, pas en blanc.

---

## 3. Typographie

**Police de marque : [Space Grotesk](https://fonts.google.com/specimen/Space+Grotesk)**
(Florian Karsten, 2018) — utilisée pour les **titres et textes courts**. 5 graisses disponibles
(300→700). Caractère contemporain, légèrement technique (hérité d'un monospace).

- **Titres / accroches** : Space Grotesk (500–700).
- **Corps de texte** : Space Grotesk (400) en textes courts ; pour de longs paragraphes web,
  pile sans-serif système en repli pour la lisibilité et la performance.

```css
--font-display: "Space Grotesk", system-ui, sans-serif;
--font-body: "Space Grotesk", system-ui, -apple-system, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
```

### Échelle typographique (base 16 px, ratio ~1.25)

| Token   | Taille   | Ligne | Graisse | Usage             |
|---------|----------|-------|---------|-------------------|
| `xs`    | 0.75rem  | 1.4   | 400     | Légendes, badges  |
| `sm`    | 0.875rem | 1.5   | 400     | Texte secondaire  |
| `base`  | 1rem     | 1.6   | 400     | Corps             |
| `lg`    | 1.25rem  | 1.5   | 500     | Chapô, intro      |
| `xl`    | 1.5rem   | 1.3   | 600     | H3                |
| `2xl`   | 2rem     | 1.2   | 600     | H2                |
| `3xl`   | 2.75rem  | 1.1   | 700     | H1                |
| `4xl`   | 3.5rem   | 1.05  | 700     | Titre hero        |

---

## 4. Tokens (espacement, rayons, ombres)

| Espacement | Valeur  |   | Rayon      | Valeur   |   | Ombre       | Valeur                                   |
|------------|---------|---|------------|----------|---|-------------|------------------------------------------|
| `space-1`  | 4px     |   | `radius-sm`| 6px      |   | `shadow-sm` | `0 1px 2px rgba(17,24,39,.08)`           |
| `space-2`  | 8px     |   | `radius-md`| 12px     |   | `shadow-md` | `0 4px 12px rgba(17,24,39,.10)`          |
| `space-3`  | 12px    |   | `radius-lg`| 20px     |   | `shadow-lg` | `0 12px 32px rgba(17,24,39,.14)`         |
| `space-4`  | 16px    |   | `radius-pill`| 999px  |   |             |                                          |
| `space-6`  | 24px    |   |            |          |   | Conteneur   | `max-width: 1200px`                      |
| `space-8`  | 32px    |   |            |          |   | Gouttière   | 24px (desktop) / 16px (mobile)           |
| `space-12` | 48px    |   |            |          |   |             |                                          |
| `space-16` | 64px    |   |            |          |   |             |                                          |

Breakpoints : `sm 640` · `md 768` · `lg 1024` · `xl 1280`.

---

## 5. Composants

### Boutons
- **Primaire** : fond `#1c5ea9`, texte blanc, `radius-pill`, padding `12px 24px`, hover `#123d6e`.
- **Secondaire** : bordure 1.5px `#1c5ea9`, texte `#1c5ea9`, fond transparent → hover fond `#d6e2f0`.
- **Accent** : fond `#f5810c`, texte blanc, hover `#9f5408`.
- Focus visible : `outline: 3px solid #82a6d0; outline-offset: 2px`.

### Cartes (formations, lives…)
- Fond blanc, `radius-lg`, `shadow-sm`, bordure `line-200`.
- **Filet de couleur** en tête (4px) piochant dans les 10 teintes = catégorisation.
- Titre en Space Grotesk 600, méta en `ink-500`, tags en badges niveau 4.

### Badges / tags
- `radius-pill`, padding `4px 12px`, `text-xs` 500.
- Fond niveau 4 + texte niveau 1 de la même teinte (ex. bleu : fond `#d6e2f0` / texte `#123d6e`).

### En-tête / navigation
- Fond blanc, logo à gauche, nav horizontale, CTA primaire à droite.
- Lien actif souligné en `#1c5ea9` (2px) ou en gras.

### Pied de page
- Fond `#123d6e` (bleu niveau 1) ou `#1c5ea9`, texte blanc/`#d6e2f0`, liens soulignés au survol.

---

## 6. Tokens CSS prêts à l'emploi

```css
:root {
  /* ── Marque : 10 couleurs (réf. niveau 2) ── */
  --c-yellow: #edcb0c;  --c-green: #4eae33;  --c-turquoise: #47b7a4;
  --c-blue: #1c5ea9;    --c-mauve: #524797;  --c-violet: #3f2880;
  --c-pink: #f296ab;    --c-fuchsia: #e03134; --c-red: #900b0d;
  --c-orange: #f5810c;

  /* Bleu — déclinaison */
  --blue-1: #123d6e; --blue-2: #1c5ea9; --blue-3: #82a6d0; --blue-4: #d6e2f0;
  --orange-1: #9f5408; --orange-2: #f5810c; --orange-3: #faba79; --orange-4: #fde8d3;

  /* ── Sémantique ── */
  --color-primary: var(--c-blue);
  --color-primary-hover: var(--blue-1);
  --color-primary-surface: var(--blue-4);
  --color-accent: var(--c-orange);
  --color-success: var(--c-green);
  --color-danger: var(--c-fuchsia);
  --color-info: var(--c-turquoise);

  /* ── Neutres ── */
  --ink-900: #111827; --ink-700: #374151; --ink-500: #6b7280;
  --line-200: #e5e7eb; --surface-100: #f5f7fa; --surface-0: #ffffff;

  /* ── Typographie ── */
  --font-display: "Space Grotesk", system-ui, sans-serif;
  --font-body: "Space Grotesk", system-ui, -apple-system, "Segoe UI", Roboto, Arial, sans-serif;
  --fs-base: 1rem; --fs-lg: 1.25rem; --fs-xl: 1.5rem;
  --fs-2xl: 2rem; --fs-3xl: 2.75rem; --fs-4xl: 3.5rem;

  /* ── Espacement / rayons / ombres ── */
  --space-1: 4px; --space-2: 8px; --space-3: 12px; --space-4: 16px;
  --space-6: 24px; --space-8: 32px; --space-12: 48px; --space-16: 64px;
  --radius-sm: 6px; --radius-md: 12px; --radius-lg: 20px; --radius-pill: 999px;
  --shadow-sm: 0 1px 2px rgba(17,24,39,.08);
  --shadow-md: 0 4px 12px rgba(17,24,39,.10);
  --shadow-lg: 0 12px 32px rgba(17,24,39,.14);
  --container: 1200px;
}

/* Import de la police */
@import url("https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&display=swap");
```

---

## 7. Sources

- [bruxellesformation.brussels](https://www.bruxellesformation.brussels/)
- [Charte graphique officielle v1 (2024, PDF)](https://www.bruxellesformation.brussels/wp-content/uploads/2024/11/Charte-graphique_Bruxelles-Formation_web.pdf)
- [Charte graphique version 2019 (PDF)](https://www.bruxellesformation.brussels/wp-content/uploads/2019/06/Charte-graphique-BF-VERSION2019_V2-public.pdf)
- [Logos & assets — Bruxelles Formation](https://www.bruxellesformation.brussels/publications/logos/)
- [Space Grotesk — Google Fonts](https://fonts.google.com/specimen/Space+Grotesk)
- [Bruxelles Formation — Brandfetch](https://brandfetch.com/bruxellesformation.brussels)
