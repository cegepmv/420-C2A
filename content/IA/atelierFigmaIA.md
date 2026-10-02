+++
date = '2026-10-02T09:42:48-04:00'
draft = false
title = "Atelier — De Figma à l'interface"
weight = 21
+++

Pour passer d'une maquette Figma à une page HTML/CSS, il existe plusieurs options, payantes et gratuites.

## Option 1 : Figma + Copilot / ChatGPT (la plus simple)

1. Ouvrez votre maquette dans Figma.
2. Sélectionnez un écran ou un composant.
3. Faites un **export PNG** ou prenez une capture d'écran.
4. Envoyez l'image à Copilot ou ChatGPT avec une demande comme :

	 > Génère une page HTML5 responsive avec le CSS séparé. Utilise Flexbox ou Grid. Respecte les couleurs, les espacements et la structure de cette maquette.

L'IA générera :

- `index.html`
- `style.css`

## Option 2 : Figma MCP + VS Code avec GitHub Copilot (la plus intégrée)

Le **Figma MCP (Model Context Protocol)** permet de connecter directement votre maquette Figma à votre éditeur de code. VS Code peut alors récupérer le contexte de design et générer du code de manière beaucoup plus fidèle qu'une simple capture d'écran.

### Étape 1 : Configuration dans VS Code

Ajoutez le serveur MCP dans votre configuration VS Code :

1. Ouvrez la palette de commandes avec **Cmd + Shift + P** (macOS) ou **Ctrl + Shift + P** (Windows/Linux).
2. Tapez **MCP: Open User Configuration** et ajoutez :

```json
{
	"inputs": [],
	"servers": {
		"figma": {
			"url": "https://mcp.figma.com/mcp",
			"type": "http"
		}
	}
}
```

### Étape 2 : Utiliser le MCP

1. Ouvrez votre chat Copilot dans VS Code.
2. Copiez l'URL d'un frame ou d'un calque dans Figma.
3. Collez-la dans le chat avec une demande comme :

	 > Génère une page HTML5 responsive avec le CSS séparé. Utilise Flexbox ou Grid. Respecte les couleurs, les espacements et la structure de ce design.

Le MCP transmet à Copilot le contexte de design réel (couleurs, typographies, espacements, hiérarchie des composants) au lieu d'une simple analyse visuelle.

## Option 3 : Plugins Figma « Design to Code » (semi-automatique)

Plusieurs plugins Figma génèrent directement du HTML/CSS à partir d'un frame ou d'un composant sélectionné :

- **Figma to Code (gratuit)** : génère HTML, Tailwind, React, Vue, Svelte, etc.
- **Anima (freemium)** : export HTML/CSS/React avec animations et interactions.
- **Locofy (freemium)** : conversion avancée vers React, Next.js, HTML/CSS.
- **Builder.io (payant)** : export vers du code propre et maintenable.
- **TeleportHQ (freemium)** : édition visuelle et export HTML/CSS.

**Mode d'emploi général :**

1. Installez le plugin depuis Figma (menu **Plugins → Browse plugins**).
2. Sélectionnez le frame à convertir.
3. Lancez le plugin et ajustez les options (responsive, unités en rem/px, framework cible).
4. Copiez ou téléchargez le HTML/CSS généré.

---

## Pratique

### Étape 1 : Préparation pour la génération du code

#### Exporter les images et les icônes

Exportez toutes les images et icônes utilisées dans le site. Pour les images, vous pouvez les télécharger depuis Figma et les ajouter à votre dossier `img`.

1. Sélectionnez le calque de l'image dans Figma.
2. Regardez la barre latérale droite, tout en bas. Vous verrez une section appelée **Export**.
3. Cliquez sur le **+** à côté de « Export » pour ajouter un paramètre.
4. Choisissez le format :

	 - **Images** : JPG/PNG en 2x pour la netteté.
	 - **Icônes** : SVG pour pouvoir les colorer via `currentColor`.
	 - **Logo** : SVG ou PNG transparent.

5. Facultativement, ajustez l'échelle (1x, 2x, 3x) pour une meilleure résolution.
6. Cliquez sur le bouton **Export [nom du calque]** en bas de cette section.
7. L'image se télécharge dans votre dossier **Téléchargements**.

![Section Export dans Figma pour télécharger une image.](/images/atelier-figma-ia/image1.png)

L'image se trouve maintenant dans le dossier Téléchargements. Modifiez son nom pour qu'il soit identique à celui utilisé dans le code, puis déplacez-la dans votre dossier `images`.

#### Exemple

![Exemple d'image utilisée dans la maquette de la clinique vétérinaire.](/images/atelier-figma-ia/image2.png)

```html
<div class="accueil">
	<div class="hero-section">
		<img class="hero-image" src="imag/hero-image.png" />
		<div class="hero-content">
			<div class="title">Clinique vétérinaire vetCare</div>
			<div class="CTA-button">
				<div class="button-text">Prendre rendez-vous</div>
			</div>
		</div>
	</div>
</div>
```

#### Exporter les maquettes

1. Exportez toutes les pages en tant qu'images PNG.
2. Mettez toutes les maquettes dans un dossier.

![Maquettes exportées et regroupées dans un dossier.](/images/atelier-figma-ia/image3.png)

#### Récupérer les styles CSS

1. Importez le style CSS pour tous les calques.
2. Enregistrez les éléments fournis dans un fichier texte.

![Récupération des propriétés CSS des calques dans Figma.](/images/atelier-figma-ia/image4.png)

### Étape 2 : Interroger Copilot / ChatGPT

**Restriction indiquée pour un profil gratuit : deux maquettes.**

#### Prompt 1

```text
À partir de la maquette Figma fournie, crée les pages HTML et CSS correspondantes.

Respecte fidèlement les propriétés de style récupérées de Figma :
- couleurs ;
- typographies ;
- tailles de police ;
- poids des caractères ;
- espacements ;
- marges et paddings ;
- dimensions des éléments ;
- rayons des bordures ;
- bordures ;
- ombres ;
- alignements ;
- largeur des colonnes ;
- espacement entre les cartes.

Utilise les valeurs Figma comme référence prioritaire plutôt que de les estimer visuellement.
Crée un fichier HTML par page et un fichier CSS commun.
Utilise une structure HTML simple et sémantique.
Le résultat doit être responsive tout en conservant le design de la maquette.
```

![Illustration accompagnant la demande de génération à partir des maquettes.](/images/atelier-figma-ia/image5.png)

#### Prompt 2

> Prends en considération les images téléchargées depuis Figma.

N'hésitez pas à demander plus de précisions.

Nous allons ensuite créer dans VS Code tous nos fichiers et coller le code de chaque partie.

### Exemple de résultat

![Exemple de résultat pour le site de la clinique vétérinaire vetCare.](/images/atelier-figma-ia/image6.png)

#### Code HTML

```html
<div class="page">
	<header class="header">
		<div class="header__inner">
			<a href="index.html" class="header__logo">vetcare</a>
			<nav class="header__nav">
				<a href="index.html" class="is-active">accueil</a>
				<a href="services.html">Services</a>
				<a href="equipe.html">Equipe</a>
				<a href="rendez-vous.html">Rendez-vous</a>
				<a href="contact.html">Contact</a>
			</nav>
		</div>
	</header>
	<section class="section" style="padding: 60px 0 0;">
		<div class="hero-image">
			<img class="hero-image__img" src="images/hero-image.png" alt="Vétérinaire examinant un golden retriever">
		</div>
		<div class="hero-title-block">
			<h1 class="hero-title-block__title">Clinique vétérinaire vetCare</h1>
			<a href="rendez-vous.html" class="btn">Prendre rendez-vous</a>
		</div>
	</section>
</div>
```
