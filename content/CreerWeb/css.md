+++
date = '2026-08-06T09:13:12-04:00'
draft = false
title = 'CSS3 (Cascading Style Sheets)'
weight = 2
+++

CSS est le langage qui contrôle l'apparence visuelle des pages HTML. Couleurs, polices, marges, disposition — tout ce qui touche au style est géré par le CSS. Sans CSS, une page web n'affiche que du texte brut sans mise en forme.

## Règle CSS

Une règle CSS est composée d'un **sélecteur** (l'élément à styliser) et de **déclarations** (propriété + valeur).

```css
sélecteur {
  propriété: valeur;
}
```

Exemple — rendre tous les titres `<h1>` en bleu:

```css
h1 {
  color: blue;
}
```
{{< notice style="warning" title="Important" >}}
Il est idéal de centraliser les styles CSS dans des <b>fichiers .css</b> avec des noms <b>significatifs</b>. Cela permet de réutiliser les styles dans plusieurs pages HTML.
{{< /notice >}}

## Classes et identifiants

Pour appliquer un style à un **élément précis** plutôt qu'à tous les éléments du même type, on utilise des **classes** (`.`) ou des **identifiants** (`#`).

| Sélecteur    | Syntaxe CSS | Attribut HTML   | Usage                    |
|--------------|-------------|-----------------|--------------------------|
| Classe       | `.nom`      | `class="nom"`   | Plusieurs éléments       |
| Identifiant  | `#nom`      | `id="nom"`      | Un seul élément unique   |

Exemple CSS avec une classe et un identifiant:

```css
.titre-principal {
  color: darkblue;
  font-size: 2em;
}

#logo {
  width: 120px;
}
```

Utilisation dans le HTML:

```html
<h1 class="titre-principal">Bienvenue</h1>
<img id="logo" src="logo.png" alt="Logo du site">
```

## Couleur et fond

```css
.message-alerte {
  color: red;
  background-color: yellow;
}
```

Utilisation dans le HTML:

```html
<p class="message-alerte">Attention, ce champ est obligatoire.</p>
```

## Texte et police

```css
.contenu-article {
  font-size: 16px;
  font-family: Arial, sans-serif;
  font-weight: bold;
}
```

Utilisation dans le HTML:

```html
<p class="contenu-article">Voici le texte principal de l'article.</p>
```

## Marges et espacement

```css
.bloc-texte {
  margin: 20px;    /* espace à l'extérieur de l'élément */
  padding: 10px;   /* espace à l'intérieur de l'élément */
}
```

Utilisation dans le HTML:

```html
<div class="bloc-texte">
  <p>Ce paragraphe est dans un bloc avec des marges.</p>
</div>
```

## Styles pour les images

```css
.photo-produit {
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 5px;
  width: 150px;
}
```

Utilisation dans le HTML:

```html
<img class="photo-produit" src="chaise.jpg" alt="Chaise en bois">
```

## Comment lier le CSS au HTML

On place le lien vers le fichier CSS dans le `<head>` de la page HTML:

```html
<head>
  <link rel="stylesheet" href="style.css">
</head>
```

{{< notice style="warning" title="Important" >}}
Vous pouvez également vous sauvez du temps en utilisant un gabarit CSS. Il en existe un myriade sur le net. Ce pour tous les goûts: <a href="https://www.w3schools.com/w3css/w3css_templates.asp">Gabarit CSS</a>
{{< /notice >}}

## Structure complète

Un fichier `style.css` minimal combinant sélecteurs d'éléments et classes:

```css
body {
  font-family: Arial, sans-serif;
  background-color: #f5f5f5;
}

h1 {
  color: #333333;
}

.contenu-principal {
  font-size: 16px;
  margin: 10px;
}

.message-important {
  color: red;
  font-weight: bold;
}
```

La page HTML correspondante:

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Ma page</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Titre de la page</h1>
  <p class="contenu-principal">Voici le texte principal.</p>
  <p class="message-important">Ceci est un message important.</p>
</body>
</html>
```

Source: https://www.w3schools.com/css/
