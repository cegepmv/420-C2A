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

## Couleur et fond

```css
p {
  color: red;
  background-color: yellow;
}
```

## Texte et police

```css
p {
  font-size: 16px;
  font-family: Arial, sans-serif;
  font-weight: bold;
}
```

## Marges et espacement

```css
p {
  margin: 20px;    /* espace à l'extérieur de l'élément */
  padding: 10px;   /* espace à l'intérieur de l'élément */
}
```

## Styles pour les images

```css
img {
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 5px;
  width: 150px;
}
```

## Comment lier le CSS au HTML

On place le lien vers le fichier CSS dans le `<head>` de la page HTML:

```html
<head>
  <link rel="stylesheet" href="style.css">
</head>
```

## Structure complète

Un fichier `style.css` minimal:

```css
body {
  font-family: Arial, sans-serif;
  background-color: #f5f5f5;
}

h1 {
  color: #333333;
}

p {
  font-size: 16px;
  margin: 10px;
}
```

Source: https://www.w3schools.com/css/
