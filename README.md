# Générateur charte graphique de l'État — MEN/MESRI

Outil autonome (fichier HTML unique, sans serveur, sans dépendance externe) pour produire des documents conformes à la **charte graphique des services déconcentrés de l'État** du ministère de l'Éducation nationale et de l'Enseignement supérieur.


https://julientexier86.github.io/charte-graphique-etat-men/charte_etat_final_2.html

---

## Fonctionnalités

| Onglet | Contenu | Export |
|--------|---------|--------|
| **Signature mail** | Bloc-marque + direction + coordonnées | HTML (Thunderbird / Outlook) |
| **En-tête courrier** | En-tête A4 conforme charte SIG p. 38 | PNG |
| **Note de service** | Mise en page deux colonnes Word | .docx |
| **Communiqué de presse** | CP charte SIG | PNG / .doc |
| **Carte de visite** | Recto conforme | PNG |
| **Logo établissement** | Bloc-marque personnalisé (académie ou établissement) | PNG / HTML |
| **Courrier officiel** | Gabarit dynamique A4 conforme p. 43 | .docx |
| **Réseaux sociaux** | Bannières Instagram (540×540), Twitter/X (960×540), Stories (1080×1920) | PNG |
| **Présentation** | Diapo couverture + contenu 16/9 ou A4 | PNG / **.pptx** |
| **Fond d'écran visio** | Arrière-plan Teams/Zoom 1920×1080 (styles bleu, blanc, split) | PNG |
| **Gabarits officiels** | Modèles Office MEN + gabarit académie de Poitiers | .docx / .pptx |

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
├── charte_etat_final_2.html   # Outil principal (fichier unique ~8 Mo)
├── charte_etat_final.html     # Version antérieure (archive)
└── README.md
```

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

---

## Licence

Usage interne — ministère de l'Éducation nationale et de l'Enseignement supérieur.  
La charte graphique et les éléments visuels de la marque de l'État sont la propriété du **Secrétariat général du gouvernement / SIG**.
