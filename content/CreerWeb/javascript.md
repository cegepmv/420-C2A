+++
date = '2026-08-06T10:24:31-04:00'
draft = false
title = 'Javascript'
weight = 3
+++

JavaScript est le langage qui rend les pages web interactives. Là où HTML structure le contenu et CSS le met en forme, JavaScript lui donne vie — boutons, animations, formulaires, mises à jour de contenu sans recharger la page.

## Balise script

On intègre du JavaScript dans une page HTML avec la balise `<script>`, idéalement à la fin du `<body>`:

```html
<body>
  ...
  <script src="script.js"></script>
</body>
```

## Afficher un message

```js
console.log("Bonjour!");
```

## Variable

```js
let nom = "Pierre-Paul";
let age = 25;
```

## Condition

```js
if (age >= 18) {
  console.log("Majeur");
} else {
  console.log("Mineur");
}
```

## Fonction

```js
function saluer(nom) {
  console.log("Bonjour " + nom);
}

saluer("Marie");
```

## Interagir avec la page HTML

JavaScript peut modifier le contenu d'une page en direct:

```js
document.getElementById("titre").textContent = "Nouveau titre";
```

```html
<h1 id="titre">Titre original</h1>
```

## Structure complète

Un exemple minimal avec un bouton interactif:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Ma page</title>
  </head>
  <body>
    <h1 id="message">Bonjour!</h1>
    <button onclick="changerMessage()">Cliquer</button>

    <script>
      function changerMessage() {
        document.getElementById("message").textContent = "Vous avez cliqué!";
      }
    </script>
  </body>
</html>
```

Source: https://www.w3schools.com/js/
