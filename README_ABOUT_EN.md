# ALTA MALE LAB — Page About EN
## Guide d'intégration Divi — Version 1.0
*Préparé pour Laurent Cornalino — Octobre 2026*

---

## RÉFÉRENCE VISUELLE

**Aperçu immersif (rendu final attendu) :**
https://altamalelab.github.io/about-reference/apercu/

→ Ce lien montre exactement ce que la page doit rendre une fois intégrée dans WordPress/Divi. C'est la source de vérité visuelle pour cette page.

---

## PRINCIPE D'INTÉGRATION

**Même méthode que la Homepage** : un Module Code Divi par section.

- Chaque section = 1 Module Code (HTML + CSS inlinés)
- Aucun style Divi automatique ne doit interférer
- Le CSS de chaque section commence par un reset scoped : `*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }`
- Toutes les propriétés clés utilisent `!important` pour écraser les styles Divi
- Préfixe de classes CSS : `alta-ab-sXX-` (ex. `alta-ab-s01-`, `alta-ab-s07-`, etc.)

**Google Fonts à charger une seule fois** (dans le header global WordPress ou le Module Code de la S01) :
```html
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@500;600&family=Lato:wght@300;400;700&display=swap" rel="stylesheet">
```

**Police Gaoel** (wordmark nav uniquement) : déjà intégrée en base64 dans le fichier HTML de référence — ne pas modifier.

---

## NAVIGATION GLOBALE

La navigation fixe est **commune à toutes les pages** du site. Elle est déjà intégrée sur la Homepage. Pour la page About :
- Vérifier que le lien "ABOUT" est actif (classe `alta-nav__link--active`)
- Aucune modification de la nav n'est nécessaire si elle est déjà en place

---

## STRUCTURE — 12 SECTIONS

### S01 · WHO WRITES THIS
**Rôle :** Introduction éditoriale — voix du fondateur, question d'ouverture
**Fond :** `#000000`
**Typographie :** Titre H1 Poppins 600, corps Lato 300
**Note :** Le `?` est précédé d'une espace insécable `&nbsp;` (typographie française/suisse)
**Séparateur :** Aucun (première section)

---

### S02 · NOT A BLOG
**Rôle :** Positionnement éditorial — ce que Alta Male Lab n'est pas
**Fond :** `#000000`
**Typographie :** Titre H2 Poppins 500, liste Lato 400
**Séparateur :** Ligne `1px #1F1F1F` en `::before` pseudo-element, max-width 760px centré

---

### S03 · THE LONG GAME
**Rôle :** Définition de la philosophie centrale
**Fond :** `#000000`
**Accent :** Gold `#C8B568` sur le mot-clé "The Long Game"
**Typographie :** Titre H2 Poppins 500, corps Lato 300
**Séparateur :** Ligne `1px #1F1F1F`

---

### S04 · THE ALTA FRAMEWORK
**Rôle :** Présentation des 3 piliers biologiques
**Fond :** `#000000`
**Structure :** 3 blocs verticaux (Metabolic Intelligence / Strength & Muscles / Mind & Nervous System)
**Accent :** Numéros en gold `#C8B568`, titres piliers en `#EDEDED`
**Séparateur :** Ligne `1px #1F1F1F`

---

### S05 · FOR MEN 40+
**Rôle :** Définition de l'audience cible
**Fond :** `#000000`
**Typographie :** Titre H2 Poppins 500, corps Lato 300
**Séparateur :** Ligne `1px #1F1F1F`

---

### S06 · NOT A COACH
**Rôle :** Différenciation — ce que le fondateur n'est pas
**Fond :** `#000000`
**Typographie :** Titre H2 Poppins 500, corps Lato 400
**Séparateur :** Ligne `1px #1F1F1F`

---

### S07 · THE FOUNDER
**Rôle :** Portrait du fondateur — biographie courte + photo
**Fond :** `#000000`
**Structure :** Layout 2 colonnes (texte gauche / portrait droit) sur desktop, colonne unique sur mobile
**Portrait :** Photo Anthony JR Kvaternik, 220×274px, `filter: grayscale(100%)`, intégrée en base64
**Typographie :** Titre H2 Poppins 500, corps Lato 300
**Séparateur :** Ligne `1px #1F1F1F`

> ⚠️ La photo est intégrée en base64 directement dans le HTML pour garantir l'affichage sans dépendance externe. Ne pas remplacer par un lien image Divi.

---

### S08 · THE MANIFESTO
**Rôle :** Extrait manifeste — citation éditoriale forte
**Fond :** `#000000`
**Style :** Citation centrée, Lato 300 italic, couleur `#B8B8B8`
**Séparateur :** Ligne `1px #1F1F1F`

---

### S09 · WHAT YOU FIND HERE
**Rôle :** Contenu de la plateforme — ce que le lecteur va trouver
**Fond :** `#000000`
**Structure :** Liste de rubriques avec descriptif court
**Accent :** Tirets ou puces gold `#C8B568`
**Séparateur :** Ligne `1px #1F1F1F`

---

### S10 · THE ALTA CIRCLE
**Rôle :** Invitation à rejoindre la communauté newsletter
**Fond :** `#000000`
**CTA :** Bouton ou lien texte en gold `#C8B568`, hover `#EDEDED`
**Séparateur :** Ligne `1px #1F1F1F`

---

### S11 · ALTA BODY & MIND ACADEMY
**Rôle :** Pont vers la marque Academy — transformation pratique
**Fond :** `#000000`
**Lien :** Vers le site ABMA (URL à confirmer lors de l'intégration)
**Séparateur :** Ligne `1px #1F1F1F`

---

### S12 · CLOSING — THE LONG GAME
**Rôle :** Clôture éditoriale — aucun footer supplémentaire
**Fond :** `#000000`
**Style :** Texte centré, Lato 300, couleur `#8A8A8A`
**Note :** ⚠️ Aucun footer WordPress standard ne doit apparaître sous cette section — masquer le footer global sur cette page ou le remplacer par un footer minimal ALTA

---

## TOKENS DE DESIGN (rappel)

| Élément | Valeur |
|---|---|
| Fond | `#000000` |
| Texte principal | `#EDEDED` |
| Texte secondaire | `#B8B8B8` |
| Texte discret | `#8A8A8A` |
| Accent gold | `#C8B568` |
| Séparateur | `#1F1F1F` |
| H1 | Poppins 600 |
| H2 | Poppins 500 |
| Body | Lato 400 / 300 |
| Max-width contenu | 760px centré |
| Padding section | 120px–160px vertical |
| Wordmark nav | Gaoel (base64 inline) |

**Interdit :** animations, box-shadow, text-shadow, gradients, border-radius décoratif, effets visuels quelconques.

---

## ORDRE DE TRAVAIL RECOMMANDÉ

1. Ouvrir l'aperçu de référence : https://altamalelab.github.io/about-reference/apercu/
2. Créer une nouvelle page WordPress "About" (ou "À Propos")
3. Passer en mode Divi Builder → "Build from scratch"
4. Désactiver le footer global sur cette page (Page Settings → Divi → Footer → None)
5. Intégrer les 12 sections dans l'ordre S01→S12, chacune dans un Module Code séparé
6. Vérifier le rendu à chaque section sur desktop + mobile
7. Valider le résultat final contre l'aperçu de référence

---

## CONTACT

**AntoNik — Alta Male Lab**
anthony.kvaternik@me.com

*Pour toute question technique sur une section spécifique, référencer le numéro de section (ex. "question sur S07").*
