# Site de révision DEC — épreuve n°1 (déontologie & réglementation professionnelle)

Site d'une page : `index.html` (HTML/CSS/JS, aucune dépendance). Publié via **GitHub Pages** :
https://tatianamercier-hub.github.io/deontologie-dec/

## Structure des données (dans le `<script>` de `index.html`)

| Tableau JS | Contenu |
|---|---|
| `FICHES` | Les fiches de révision (14 `cat:"ec"` + 15 `cat:"cac"`) |
| `MAPS` | Les cartes mentales (1 par fiche, même ordre) |
| `BANK` | Les questions du QCM |
| `QRC` | Les questions à réponse courte |

**Format d'une fiche** :
`{cat, title, sub, def?, schema?, schemaLbl?, sections?[], essentiel?[], table?, chiffres?, piege?, memo?}`

Les **onglets colorés** d'une fiche = `sections:[{lbl, intro?, items?[], note?}]`
(la couleur est automatique : `fsec-(index%5)+1`).

**Format d'une carte mentale** : `{cat, title, sub, center, branches:[{l, p:[...]}]}`

## Règles de contenu (IMPORTANT)

- **Ne jamais inventer de contenu.** L'utilisatrice dicte le contenu ; Claude ne fait que le **mettre en forme**. Si seuls les titres d'onglets sont donnés, créer les onglets **vides** et attendre le contenu.
- Corriger les coquilles évidentes (fautes de frappe, sigles) et le signaler.
- **Sous-titres** (quand elle dit « titre en gras » ou « titre coloré ») :
  `<div class='fbox-intro fsubh'>Mon titre</div>`
  (la classe `.fsubh` gère la couleur `--ox`, le gras et l'espacement).
- **Listes** : `class='fiche-list'` (puces rondes). Ne pas utiliser `class='cdef'` (tirets).
- **Tableaux** : `class='fiche-table'`, encapsulés dans `<div style='overflow-x:auto'>`.

## Workflow imposé après CHAQUE modification

1. **Valider le JS** : vérifier l'équilibre des accolades/crochets/parenthèses et des guillemets
   (en ignorant commentaires et chaînes), puis afficher **`ANALYSE JS : OK`**.
   Vérifier aussi l'équilibre des balises HTML (`div`/`ul`/`li`/`p`/`table`) dans les `note`.
2. **Commit + push** avec la ligne :
   `Co-Authored-By: Claude Opus 4.8 <noreply@anthropic.com>`

Un commit par étape. Le fichier est en **LF** — préserver les fins de ligne (éviter les diffs globaux).

## Travailler depuis plusieurs ordinateurs

- **En arrivant** : `git pull`
- **En partant** : vérifier que tout est poussé (`git status`)
