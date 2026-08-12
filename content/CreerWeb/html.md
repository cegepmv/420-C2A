+++
date = '2026-08-06T09:13:07-04:00'
draft = false
title = 'HTML5 (HyperText Markup Language)'
weight = 1
+++

HTML est le langage de base utilisé dans tout le net. Toute les pages lues par Firefox, Google Chrome ou Safari contiennent du HTML. On construit une page web avec ce standard qui existe depuis le début de la création de la toile. La structure peut être simple, distribuée sur plusieurs pages. On peut référer d'autres pages avec un lien.

## Balise HTML

On utilise une balise d'ouverture et de fermeture pour chaque élément HTML. Pour un titre, ça donne: 

```html
<html>
...
</html>
```



```html
<h1>Mon titre</h1>
```

## L'entête

Dans l'entête, on doit y mettre un titre. De plus, on peut mettre le lien vers le fichier de style CSS, la description du site (mots clés, description, auteur de la page, encodage, etc.), le lien vers le fichier de scripts (JavaScript).

```html
<head>
<title>Page Title</title>
</head>
```

## Body

Dans le body de la page, c'est là que l'on y met le contenu. Ce peut être des paragraphes, des images, des liens, un tableau, un vidéo, etc.

### Titre
```html
<h1>Mon titre</h1>
```

### Paragraphe
```html
<p>Mon paragraphe</p>
```

### Lien
```html
<a href="https://www.exemple.com">Cliquez ici</a>
```

### Image
```html
<img src="photo.jpg" alt="Description de l'image">
```

{{< notice style="warning" title="Important" >}}
Le lien vers la source de l'image peut être relatif ou absolu. 
{{< /notice >}}

### Liste non ordonnée (puces)
```html
<ul>
  <li>Pomme</li>
  <li>Banane</li>
  <li>Orange</li>
</ul>
```

### Liste ordonnée (numéros)
```html
<ol>
  <li>Premier</li>
  <li>Deuxième</li>
  <li>Troisième</li>
</ol>
```

## Structure complète

Voici à quoi ressemble une page HTML minimale:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Ma page</title>
  </head>
  <body>
    <h1>Bonjour!</h1>
    <p>Voici mon premier paragraphe.</p>
    <a href="https://www.exemple.com">Un lien</a>
  </body>
</html>
```

## Sauvegarde et validation

Il est suggéré de tester la cohérence et le fonctionnement avec un navigateur web. Pour se faire, vous pouvez sauvegarder les fichiers .html, .css et .js dans un dossier local. Enfin, vous pouvez charger dans un navigateur le fichier index.html. Vous aurez un aperçu du rendu avant la publication sur un hébergeur.


{{< notice style="warning" title="Important" >}}
Il est toujours recommandé de tester l'intégration complète de votre site web <b>localement</b> avant de le publier sur le net. Lorsqu'une <b>erreur</b> se trouve sur votre site web, les robots qui scannent votre contenu peuvent pénaliser votre <b><i>rang</i></b> s'il y a des erreurs et des incohérences.
<br/>
<b>Source de l'information</b>: <a href="https://sirlinksalot.co/is-my-website-penalized/">sirlinksalot.co</a>

{{< /notice >}}

Source: https://www.w3schools.com/html/
