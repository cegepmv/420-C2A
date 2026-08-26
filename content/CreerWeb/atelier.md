+++
date = '2026-08-07T09:20:17-04:00'
draft = false
title = 'Atelier Web 1 - Navigateur'
weight = 10
+++

Ces exercices se font directement dans votre navigateur, sans aucune installation. Vous n'avez besoin que d'une page web à inspecter — utilisez n'importe quel site public, par exemple [https://www.w3schools.com](https://www.w3schools.com).

---

## Exercice 1 — Essayer le mode développeur

Les navigateurs modernes offrent un outil intégré pour inspecter et comprendre le code HTML d'une page web : les **outils développeur** (DevTools).

**Étapes :**

1. Ouvrez votre navigateur (Chrome, Firefox ou Edge) et accédez à n'importe quelle page web.
2. Ouvrez les outils développeur avec l'une de ces méthodes :
   - Appuyez sur **F12**
   - Ou appuyez sur **Ctrl+Shift+I** (Windows/Linux) / **Cmd+Option+I** (Mac)
   - Ou faites un clic droit sur la page, puis choisissez **Inspecter**
3. Un panneau s'ouvre (généralement en bas ou à droite). Repérez l'onglet **Éléments** (Chrome/Edge) ou **Inspecteur** (Firefox).
4. Dans cet onglet, vous voyez l'arborescence HTML complète de la page. Cliquez sur une balise pour la déplier.
5. Survolez différentes balises dans le panneau : la zone correspondante s'illumine dans la page.

{{< notice style="tip" title="Conseil" >}}
Vous pouvez aussi cliquer sur l'icône en forme de curseur (🔲) en haut à gauche des outils développeur, puis cliquer directement sur un élément de la page pour le sélectionner immédiatement dans le panneau HTML.
{{< /notice >}}

**À observer :** Repérez les balises `<html>`, `<head>`, `<body>` et quelques balises de contenu comme `<h1>`, `<p>` ou `<nav>`.

---

## Exercice 2 — Trouver les images dans la page

Les images en HTML sont insérées avec la balise `<img>`. Cet exercice vous apprend à les repérer et à lire leurs attributs.

**Étapes :**

1. Avec les outils développeur ouverts sur l'onglet **Éléments / Inspecteur**, appuyez sur **Ctrl+F** (ou **Cmd+F** sur Mac) pour ouvrir la recherche dans le code HTML.
2. Tapez `img` dans le champ de recherche.
3. Les occurrences de la balise `<img>` sont surlignées. Naviguez entre elles avec les flèches.
4. Cliquez sur une balise `<img>` pour l'examiner. Repérez ses attributs :
   - `src` — l'adresse (URL) du fichier image
   - `alt` — la description alternative (utile pour l'accessibilité)
   - `width` / `height` — les dimensions si elles sont précisées
5. Survolez la valeur de l'attribut `src` : une prévisualisation de l'image apparaît souvent directement dans les outils développeur.

{{< notice style="info" title="À noter" >}}
Certaines images ne sont pas des balises `<img>` : elles peuvent être définies en CSS (propriété `background-image`). Ces images n'apparaîtront pas dans votre recherche HTML.
{{< /notice >}}

**À livrer :** Notez le `src` et le `alt` de deux images trouvées sur la page inspectée.

---

## Exercice 3 — Modifier le code HTML dans le mode développeur

Les outils développeur permettent de modifier temporairement le HTML d'une page, directement dans le navigateur. Ces modifications n'affectent que votre affichage local et disparaissent au rechargement — c'est un environnement d'expérimentation sans risque.

**Étapes :**

1. Dans le panneau **Éléments / Inspecteur**, localisez une balise de titre, par exemple `<h1>`.
2. Double-cliquez sur le **texte** à l'intérieur de la balise (entre les balises ouvrante et fermante).
3. Modifiez le texte, par exemple remplacez le titre original par votre prénom.
4. Appuyez sur **Entrée** pour confirmer. Le titre change immédiatement dans la page.
5. Maintenant, double-cliquez sur le **nom de la balise** elle-même (le `h1`).
6. Remplacez `h1` par `h3`, puis confirmez avec **Entrée**. Observez comment la taille du titre change.
7. Pour ajouter un attribut, faites un clic droit sur une balise et choisissez **Add attribute** (ou **Ajouter un attribut**). Ajoutez `style="color: red;"` à un paragraphe `<p>` et observez le résultat.

{{< notice style="warning" title="Rappel" >}}
Toutes ces modifications sont **temporaires**. Un simple **F5** (rechargement de la page) remet la page dans son état d'origine. Vous n'avez donc aucun risque de « casser » quoi que ce soit.
{{< /notice >}}

**À essayer en bonus :** Trouvez une balise `<img>` et modifiez son attribut `src` pour le remplacer par l'URL d'une autre image (par exemple `https://picsum.photos/200`). L'image se remplace en direct!