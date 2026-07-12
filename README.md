# Générateur charte graphique de l'État — MEN/MESRI

![HTML](https://img.shields.io/badge/HTML-fichier%20autonome-E34F26?logo=html5&logoColor=white) ![Type](https://img.shields.io/badge/Type-site%20statique-0f766e) ![Deploy](https://img.shields.io/badge/Deploy-GitHub%20Pages-222?logo=githubpages&logoColor=white) ![Serveur](https://img.shields.io/badge/Serveur-aucun-2e7d32)

Outil autonome (fichier HTML unique, sans serveur, sans dépendance externe) pour produire des documents conformes à la **charte graphique des services déconcentrés de l'État** du ministère de l'Éducation nationale et de l'Enseignement supérieur.


https://julientexier86.github.io/charte-graphique-etat-men/charte_etat_final_2.html

---

## Fonctionnalités

| Onglet | Contenu | Export |
|--------|---------|--------|
| **Bloc-marque** | Bloc-marque officiel (académie, région, DSDEN, direction, établissement) | PNG / **SVG vectoriel** / HTML |
| **Signature mail** | Bloc-marque + direction + coordonnées | Copie mise en forme / HTML (Thunderbird / Outlook) |
| **En-tête courrier** | En-tête A4 conforme charte SIG p. 38 | PNG / impression A4 |
| **Note de service** | Mise en page deux colonnes Word | .docx / impression A4 |
| **Communiqué de presse** | CP charte SIG | PNG / .doc |
| **Carte de visite** | Recto conforme + **verso QR code vCard** (coordonnées scannables) | PNG recto / PNG verso |
| **Logo établissement** | Bloc-marque personnalisé (académie ou établissement) | PNG / HTML |
| **Courrier officiel** | Gabarit dynamique A4 conforme p. 43, **pagination automatique multi-pages** | .docx / PNG par page / impression A4 |
| **Réseaux sociaux** | Bannières Instagram (540×540), Twitter/X (960×540), Stories (1080×1920) | PNG |
| **Présentation** | Diapo couverture + contenu 16/9 ou A4 | PNG / **.pptx** |
| **Fond d'écran visio** | Arrière-plan Teams/Zoom 1920×1080 (styles bleu, blanc, split) | PNG |
| **Documents types** | **Convocation · ordre du jour · attestation** — gabarits A4 à champs adaptatifs | .doc / PNG / impression A4 / HTML |
| **Gabarits officiels** | Modèles Office MEN (papeterie, présentation 16:9 et 4:3) + diaporama académie de Poitiers | .docx / .pptx |

### Profil partagé et sauvegarde automatique

- **⚙ Mes informations** (carte dépliable en haut de page) : renseignez une fois votre entité, direction, identité et coordonnées, puis **« Appliquer à tous les onglets »** propage ces valeurs dans les 13 onglets.
- **Sauvegarde automatique** : toutes les saisies sont conservées dans le navigateur (localStorage) et restaurées à la visite suivante. Le bouton **« Réinitialiser l'outil »** efface tout.
- **Partage en équipe** : **« Exporter le profil (JSON) »** produit un fichier de configuration à diffuser (par exemple à tout un établissement) ; **« Importer un profil »** le recharge en un clic.

### Exports avancés

- **SVG vectoriel** (onglet Bloc-marque) : picto Marianne en vrais tracés vectoriels (vectorisation potrace du PNG officiel), intitulé et devise en texte éditable, polices embarquées pour l'affichage navigateur. Pour l'imprimerie, vectoriser le texte dans Inkscape/Illustrator.
- **Impression A4** (courrier, en-tête, note) : mise à l'échelle exacte 210 × 297 mm, une feuille par page, polices Marianne incluses.
- **Copie mise en forme** (signature) : colle la signature directement formatée dans le compositeur du client mail (`ClipboardItem`), sans passer par le code HTML.
- **QR code vCard** (carte de visite) : encodeur QR autonome embarqué (mode octet, correction M, versions 1-20), validé bit à bit contre la bibliothèque de référence python-qrcode. Le verso généré contient les coordonnées au format vCard 3.0, importables d'un scan dans n'importe quel téléphone.

### Interface DSFR (Système de Design de l'État)

L'interface utilise le **DSFR officiel v1.11.2** (`@gouvfr/dsfr`), embarqué dans le fichier (feuille de style complète, sans les `@font-face` — les polices Marianne sont déjà incluses — ni fichiers d'icônes externes) :

- **En-tête** : bloc-marque officiel `fr-logo` (rendu pur CSS du DSFR).
- **Composants** : onglets `fr-tabs`, boutons `fr-btn` primaire/secondaire, champs `fr-input`/`fr-select`, callouts `fr-callout` (bleu écume / brun caramel).
- **Accessibilité** : rôles ARIA `tablist`/`tab`/`tabpanel`, `aria-selected`, anneau de focus DSFR, navigation clavier ← → entre onglets (RGAA).
- Une fine surcouche CSS adapte le composant onglets au multi-rangées (13 onglets) et conserve la mise en page des aperçus documents ; licence DSFR : usage réservé aux acteurs publics.

---

## Utilisation

1. Ouvrir `charte_etat_final_2.html` dans un navigateur moderne (Chrome, Firefox, Edge, Safari).
2. Sélectionner l'onglet souhaité.
3. Renseigner les champs (intitulé, direction, service, couleur accent…).
4. Cliquer sur **Exporter PNG**, **Télécharger .pptx** ou **Copier HTML** selon le besoin.

> Aucune installation requise. Aucun serveur. Tout est embarqué dans le fichier HTML (polices Marianne, picto République, bibliothèques JS).

---

## Conformité charte graphique

- **Référence** : *Marque de l'État — Charte graphique des services déconcentrés*, SIG.
- **Police** : Marianne (embarquée en WOFF2) — fallback Arial pour les exports Office.
- **Couleurs officielles** :
  - Bleu France `#000091`
  - Rouge Marianne `#E1000F`
  - Bleu nuit `#21215A`
  - Vert `#005841`
  - Jaune `#FFD500`
  - Orange `#EA5433`
- **Marges A4** : 17 mm haut, 17 mm droit, 25,5 mm bas, 17 mm gauche.
- **Bloc-marque** : picto République + intitulé + devise, conforme p. 4–11 de la charte.

---

## Export PPTX (onglet Présentation)

Le bouton **Exporter .pptx** génère un fichier PowerPoint natif directement dans le navigateur, sans serveur :

- Logo Marianne embarqué (PNG)
- Mise en page identique à l'aperçu (colonne blanche 30 % / zone colorée 70 %)
- Police Arial (compatible Office)
- Format 16/9 (960×540 pt) ou A4
- Slide couverture ou slide contenu

---

## Structure du projet

```
Com graphique officielle/
├── charte_etat_final_2.html                # Outil principal (fichier unique ~4 Mo)
├── charte_etat_final.html                  # Version antérieure (archive locale, non versionnée)
├── gabarit-papeterie-men-marianne.docx     # Gabarit Word officiel MEN
├── gabarit-presentation-men-16-9.pptx      # Gabarit PowerPoint MEN 16:9
├── gabarit-presentation-men-4-3.pptx       # Gabarit PowerPoint MEN 4:3
└── README.md
```

> Les gabarits Office sont aussi **embarqués en base64** dans le fichier HTML : l'outil reste 100 % autonome même diffusé seul.

---

## Technologies embarquées

- **html2canvas** — export PNG des aperçus
- **Polices Marianne** — Regular, Bold, Italic (WOFF2, base64)
- **Générateur ZIP/PPTX** maison — production de fichiers `.pptx` sans dépendance
- **Gabarit Word** embarqué — export `.docx` via HTML Office Open XML

---

## Limitations connues

- La police **Marianne** n'est pas disponible nativement dans Microsoft Office ; les exports `.pptx` et `.docx` utilisent **Arial** comme substitut conforme.
- Le picto République est rendu en PNG (pas en SVG vectoriel) dans les exports Office.
- L'export PNG des slides utilise `html2canvas` ; les rendus très complexes peuvent différer légèrement de l'aperçu.
- **Outlook classique (Windows)** n'affiche pas les images intégrées en base64 dans les signatures HTML : utiliser l'option **« Sans picto Marianne »** de l'onglet Signature mail (Thunderbird et Outlook web les affichent normalement).
- La sauvegarde automatique utilise le localStorage : elle est propre à chaque navigateur et n'est pas partagée entre postes.

---

## Licence

Usage interne — ministère de l'Éducation nationale et de l'Enseignement supérieur.  
La charte graphique et les éléments visuels de la marque de l'État sont la propriété du **Secrétariat général du gouvernement / SIG**.
