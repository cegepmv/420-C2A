+++
date = '2026-08-10T09:46:56-04:00'
draft = true
title = 'Atelier — SDD avec SpecKit'
weight = 10
+++

Cet atelier vous guide pas à pas pour créer un site web personnel à partir d'un gabarit HTML/CSS en utilisant la méthode **SDD (Spec-Driven Development)** et l'outil open source **SpecKit** de GitHub, en combinaison avec GitHub Copilot.

**Durée estimée :** 1 h 30 à 2 h  
**Prérequis :** Compte GitHub, GitHub Copilot activé, terminal (PowerShell ou bash), éditeur de code (VS Code recommandé)

---

## Qu'est-ce que le développement piloté par les spécifications (SDD) ?

Dans le développement web traditionnel, on commence souvent par coder directement — puis on se rend compte que le résultat ne correspond pas à ce qu'on voulait. Le **SDD renverse cette logique** : on commence par décrire *ce qu'on veut construire et pourquoi*, avant de toucher au code.

### Le principe fondamental

> **Spécifiez d'abord. Codez ensuite (ou laissez l'IA le faire).**

Avec SDD, chaque étape produit un fichier Markdown qui sert de contexte pour l'étape suivante. L'IA dispose ainsi d'un contexte riche et structuré — au lieu de simples prompts improvisés — ce qui produit un résultat beaucoup plus précis et cohérent.

### Les étapes du processus SDD

| Commande | Rôle |
|----------|------|
| `/speckit.constitution` | Définit les principes directeurs du projet (normes, contraintes) |
| `/speckit.specify` | Décrit **ce qu'on veut construire** (le quoi et le pourquoi, pas le comment) |
| `/speckit.clarify` | Pose des questions sur les points ambigus et affine les spécifications |
| `/speckit.plan` | Produit le plan technique (technologies, architecture) |
| `/speckit.tasks` | Génère une liste de tâches ordonnées prêtes à exécuter |
| `/speckit.implement` | Exécute les tâches — l'IA construit le site |
| `/speckit.converge` | Vérifie que le code produit correspond aux spécifications |

### Pourquoi utiliser SDD plutôt qu'un simple prompt ?

{{< notice style="info" title="SDD vs prompt direct" >}}
Un prompt comme *«Crée-moi un site web de portfolio»* donne un résultat générique que l'IA invente librement. Avec SDD, chaque décision est documentée et tracée dans des fichiers texte. On peut itérer, comparer, corriger — et l'IA ne «perd» jamais le contexte entre les étapes.
{{< /notice >}}

---

## Préparation — Installer SpecKit

SpecKit s'installe via **uv**, un gestionnaire de paquets Python rapide.

**Étapes :**

1. Installez **uv** depuis [https://docs.astral.sh/uv/](https://docs.astral.sh/uv/) en suivant les instructions pour votre système d'exploitation.

   Sous Windows (PowerShell) :
   ```powershell
   powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
   ```

   Sous macOS / Linux :
   ```bash
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```

2. Installez l'outil **specify-cli** :
   ```bash
   uv tool install specify-cli
   ```

3. Vérifiez l'installation :
   ```bash
   specify --version
   ```

{{< notice style="tip" title="Conseil" >}}
Si `specify` n'est pas reconnu après l'installation, fermez et rouvrez votre terminal pour recharger les variables d'environnement.
{{< /notice >}}

---

## Exercice 1 — Initialiser le projet et définir les principes

Avant d'écrire une seule ligne de spécification, on établit les règles du jeu : les **principes directeurs** du projet. SpecKit crée automatiquement la structure de dossiers et configure l'intégration avec GitHub Copilot.

**Étapes :**

1. Créez un dossier pour votre projet et ouvrez-le dans VS Code :
   ```bash
   mkdir mon-portfolio
   cd mon-portfolio
   code .
   ```

2. Initialisez le projet SpecKit avec l'intégration GitHub Copilot :
   ```bash
   specify init . --integration copilot
   ```
   SpecKit crée un dossier `.specify/` contenant les gabarits de commandes et configure Copilot.

3. Ouvrez le **panneau GitHub Copilot Chat** dans VS Code (icône en haut à droite ou `Ctrl+Alt+I`).

4. Lancez la commande de constitution en décrivant vos principes :
   ```
   /speckit.constitution Le site doit être simple, accessible et lisible sur mobile. Le code HTML et CSS doit être propre et bien commenté. Pas de frameworks JavaScript complexes — HTML, CSS et JavaScript vanilla seulement. Le design doit être professionnel et sobre.
   ```

5. Copilot génère un fichier `constitution.md` dans `.specify/`. Lisez-le et ajustez si nécessaire.

**À observer :** Ouvrez le fichier `.specify/constitution.md` — remarquez comment vos principes ont été structurés. Ce fichier guidera toutes les étapes suivantes.

**À livrer :** Capturez l'écran du fichier `constitution.md` généré dans VS Code.

---

## Exercice 2 — Rédiger les spécifications et clarifier les ambiguïtés

C'est l'étape la plus importante. On décrit **ce qu'on veut** sans parler de technologie. SpecKit produit ensuite des questions pour clarifier les zones grises.

**Étapes — Spécifier :**

1. Dans le chat Copilot, lancez la commande `/speckit.specify` en décrivant votre site portfolio :
   ```
   /speckit.specify Créer un site web personnel de portfolio pour un étudiant en technique informatique. Le site comporte quatre sections : une page d'accueil avec une courte présentation, une page de projets listant 3 projets réalisés, une page de compétences (HTML, CSS, JavaScript, Microsoft 365), et une page de contact avec un formulaire. Le design doit être sobre et moderne avec un menu de navigation.
   ```

2. Copilot génère un fichier `spec.md`. Lisez-le attentivement.

**Étapes — Clarifier :**

3. Lancez la commande de clarification pour identifier les zones ambiguës :
   ```
   /speckit.clarify Concentre-toi sur la navigation, la structure des pages et le formulaire de contact.
   ```

4. Copilot pose une série de questions (par exemple : *Le menu est-il fixe en haut? Le formulaire envoie-t-il un courriel réel?*). Répondez à chaque question dans le chat.

5. Copilot met à jour `spec.md` avec vos réponses. Relisez le fichier mis à jour.

{{< notice style="warning" title="Important" >}}
Ne sautez pas l'étape `/speckit.clarify`. Plus les spécifications sont précises à ce stade, moins vous aurez de surprises lors de l'implémentation. C'est l'équivalent d'un bon cahier des charges en entreprise.
{{< /notice >}}

**À livrer :** Capturez l'écran du fichier `spec.md` final dans VS Code.

---

## Exercice 3 — Planifier la solution et générer les tâches

On choisit maintenant la technologie et l'architecture. C'est la seule étape où on parle de « comment » construire le site.

**Étapes — Plan technique :**

1. Lancez la commande de planification en précisant votre pile technologique :
   ```
   /speckit.plan Utiliser un gabarit HTML5 avec Bootstrap 5 pour la mise en page responsive. Un fichier CSS personnalisé pour les couleurs et la typographie. JavaScript vanilla pour le menu mobile. Les pages sont des fichiers HTML statiques (pas de backend). Le formulaire de contact utilise Formspree pour l'envoi de courriel sans serveur.
   ```

2. Copilot génère un fichier `plan.md` décrivant l'architecture et les choix techniques. Lisez-le.

**Étapes — Liste de tâches :**

3. Générez la liste de tâches ordonnées :
   ```
   /speckit.tasks
   ```

4. Copilot crée un fichier `tasks.md` avec les tâches numérotées dans l'ordre de dépendance (par exemple : *1. Créer la structure HTML de base → 2. Intégrer Bootstrap → 3. Créer le fichier CSS → ...*).

5. Parcourez `tasks.md` : chaque tâche est-elle claire? Ajoutez des précisions manuellement si une tâche vous semble vague.

{{< notice style="tip" title="Conseil" >}}
Vous pouvez exécuter `/speckit.analyze` pour détecter des incohérences entre `spec.md`, `plan.md` et `tasks.md` avant de lancer l'implémentation. Très utile si vous avez beaucoup modifié les fichiers manuellement.
{{< /notice >}}

**À livrer :** Capturez l'écran du fichier `tasks.md` avec la liste des tâches générées.

---

## Exercice 4 — Implémenter le site

L'IA exécute maintenant les tâches dans l'ordre et construit le site. Votre rôle est de vérifier le résultat et de corriger si nécessaire.

**Étapes — Implémentation :**

1. Lancez la commande d'implémentation :
   ```
   /speckit.implement
   ```

2. Copilot commence à créer les fichiers un par un : `index.html`, `projets.html`, `competences.html`, `contact.html`, `style.css`, etc. Observez chaque fichier créé dans l'explorateur de VS Code.

3. Une fois l'implémentation terminée, ouvrez `index.html` dans votre navigateur pour voir le résultat.

**Étapes — Vérification :**

4. Lancez la vérification de cohérence :
   ```
   /speckit.converge
   ```

5. SpecKit compare le code produit avec les spécifications. S'il détecte des écarts (une section manquante, un comportement non implémenté), il ajoute de nouvelles tâches à `tasks.md`.

6. Si de nouvelles tâches ont été ajoutées, relancez :
   ```
   /speckit.implement
   ```
   Répétez jusqu'à ce que `/speckit.converge` confirme que tout est en ordre.

{{< notice style="info" title="Itération" >}}
Il est normal de faire plusieurs cycles implement → converge. Le SDD est une méthode **itérative** : chaque passage affine et complète le résultat. C'est bien plus fiable qu'un prompt unique qui essaie de tout faire d'un coup.
{{< /notice >}}

**À livrer :** Capturez l'écran du site ouvert dans le navigateur montrant au moins deux pages différentes, et le message de confirmation de `/speckit.converge`.

---

## Récapitulatif du processus SDD

```
Idée
  │
  ▼
/speckit.constitution   → principes.md     (les règles du projet)
  │
  ▼
/speckit.specify        → spec.md          (ce qu'on construit)
  │
  ▼
/speckit.clarify        → spec.md (mis à jour)  (plus de précision)
  │
  ▼
/speckit.plan           → plan.md          (comment on le construit)
  │
  ▼
/speckit.tasks          → tasks.md         (liste de tâches)
  │
  ▼
/speckit.implement      → code généré      (le site)
  │
  ▼
/speckit.converge       → vérification     (tout correspond?)
```

Source : [https://github.com/github/spec-kit/](https://github.com/github/spec-kit/)

