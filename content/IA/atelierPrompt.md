+++
date = '2026-08-10T15:10:20-04:00'
draft = false
title = 'Atelier — SDD avec un chatbot'
weight = 20
+++

Cet atelier reproduit la méthode **SDD (Spec-Driven Development)** de l'atelier SpecKit, mais **sans aucune installation** — uniquement avec un chatbot IA gratuit et un éditeur de texte. Le résultat est identique : un site web personnel à partir d'un gabarit HTML/CSS Bootstrap, construit étape par étape à partir de vos spécifications.

**Durée estimée :** 1 h 30 à 2 h  
**Prérequis :** Accès à un chatbot IA gratuit, VS Code ou tout éditeur de texte, navigateur web

{{< notice style="tip" title="Quel chatbot utiliser ?" >}}
Choisissez l'un de ces outils gratuits — ils fonctionnent tous de la même façon pour cet atelier :
- **Microsoft Copilot** — [copilot.microsoft.com](https://copilot.microsoft.com) (recommandé : accessible avec votre compte du Cégep)
- **ChatGPT** — [chat.openai.com](https://chat.openai.com) (compte gratuit suffisant)
- **Claude** — [claude.ai](https://claude.ai) (compte gratuit suffisant)
{{< /notice >}}

---

## Qu'est-ce que le développement piloté par les spécifications (SDD) ?

Dans le développement web traditionnel, on commence souvent par coder directement — puis on se rend compte que le résultat ne correspond pas à ce qu'on voulait. Le **SDD renverse cette logique** : on commence par décrire *ce qu'on veut construire et pourquoi*, avant de toucher au code.

### Le principe fondamental

> **Spécifiez d'abord. Codez ensuite (ou laissez l'IA le faire).**

Avec SDD, chaque étape produit un fichier Markdown que vous sauvegardez localement. Ce fichier devient le **contexte** que vous collez dans le chatbot à l'étape suivante. L'IA dispose ainsi d'un historique structuré — au lieu de devoir tout réexpliquer à chaque message.

### Les étapes du processus SDD (version manuelle)

| Phase | Fichier produit | Ce que vous faites |
|-------|-----------------|--------------------|
| **Constitution** | `constitution.md` | Décrire vos principes → demander à l'IA de les structurer |
| **Specify** | `spec.md` | Décrire le projet → l'IA rédige la spécification complète |
| **Clarify** | `spec.md` mis à jour | L'IA pose des questions → vous répondez → elle affine |
| **Plan** | `plan.md` | Choisir la technologie → l'IA génère le plan technique |
| **Tasks** | `tasks.md` | L'IA découpe le plan en tâches ordonnées |
| **Implement** | Fichiers du site | Tâche par tâche, l'IA génère le code |
| **Converge** | — | L'IA compare le code au spec et identifie les manques |

### Pourquoi structurer les prompts plutôt que tout demander d'un coup ?

{{< notice style="info" title="SDD vs prompt direct" >}}
Un prompt comme *«Crée-moi un site web de portfolio»* donne un résultat générique que l'IA invente librement. En découpant en phases et en conservant le contexte dans des fichiers, chaque décision est documentée. On peut itérer, comparer, corriger — et le chatbot ne manque aucun détail puisqu'on lui fournit tout le contexte accumulé.
{{< /notice >}}

---

## Préparation — Créer la structure de dossiers

Aucune installation n'est requise. Il suffit de créer l'espace de travail manuellement.

**Étapes :**

1. Créez un dossier `mon-portfolio/` sur votre bureau ou dans vos documents.
2. À l'intérieur, créez un sous-dossier `.specify/` — c'est là que vous sauvegarderez vos fichiers de spécification.
3. Ouvrez le dossier `mon-portfolio/` dans VS Code (`Fichier → Ouvrir le dossier`).
4. Ouvrez votre chatbot IA dans un onglet de navigateur et commencez une **nouvelle conversation** — gardez-la ouverte pendant tout l'atelier.

```
mon-portfolio/
├── .specify/
│   ├── constitution.md   (à créer à l'exercice 1)
│   ├── spec.md           (à créer à l'exercice 2)
│   ├── plan.md           (à créer à l'exercice 3)
│   └── tasks.md          (à créer à l'exercice 3)
├── index.html            (à créer à l'exercice 4)
├── projets.html
├── competences.html
├── contact.html
└── style.css
```

---

## Exercice 1 — Définir les principes directeurs

Avant d'écrire une seule ligne de spécification, on établit les règles du jeu : les **principes directeurs** du projet. C'est ce qui guide toutes les décisions à venir.

**Étapes :**

1. Dans votre chatbot, envoyez le prompt suivant en remplaçant les crochets par vos propres valeurs :

   > Tu vas m'aider à créer un site web en utilisant la méthode SDD (Spec-Driven Development).
   > Première étape : génère un fichier `constitution.md` structuré en Markdown pour mon projet, basé sur ces principes :
   > — Le site doit être simple, accessible et lisible sur mobile
   > — Le code HTML et CSS doit être propre et bien commenté
   > — Pas de frameworks JavaScript complexes : HTML, CSS et JavaScript vanilla seulement
   > — Le design doit être professionnel et sobre
   > Formate le résultat avec des titres, des listes et des sections claires.

2. Le chatbot génère un fichier `constitution.md` structuré. **Copiez le contenu complet** de la réponse.

3. Dans VS Code, créez le fichier `.specify/constitution.md` et collez-y le contenu.

4. Relisez-le et ajoutez ou modifiez manuellement un principe si nécessaire.

**À observer :** Remarquez comment l'IA a reformulé et structuré vos principes. Ce fichier sera collé dans chaque prompt suivant comme contexte de base.

**À livrer :** Capturez l'écran du fichier `constitution.md` ouvert dans VS Code.

---

## Exercice 2 — Rédiger les spécifications et clarifier les ambiguïtés

C'est l'étape la plus importante. On décrit **ce qu'on veut** sans parler de technologie. L'IA produit ensuite des questions pour clarifier les zones grises.

**Étapes — Spécifier :**

1. Dans la **même conversation** du chatbot, envoyez ce prompt (collez le contenu de `constitution.md` à la place de `[CONSTITUTION]`) :

   > Sur la base de ces principes directeurs :
   > [CONSTITUTION]
   >
   > Génère une spécification détaillée (`spec.md`) en Markdown pour le projet suivant :
   > Créer un site web personnel de portfolio pour un étudiant en technique informatique. Le site comporte quatre sections : une page d'accueil avec une courte présentation, une page de projets listant 3 projets réalisés, une page de compétences (HTML, CSS, JavaScript, Microsoft 365), et une page de contact avec un formulaire. Le design doit être sobre et moderne avec un menu de navigation.
   >
   > Ne mentionne aucune technologie. Concentre-toi uniquement sur le QUOI et le POURQUOI : objectif, utilisateurs cibles, contenu de chaque page, comportements attendus.

2. Copiez la réponse et créez le fichier `.specify/spec.md` dans VS Code.

**Étapes — Clarifier :**

3. Dans la même conversation, envoyez ce prompt :

   > Sur la base de cette spécification :
   > [SPEC — copier le contenu de spec.md]
   >
   > Identifie 5 à 8 zones ambiguës ou sous-spécifiées et pose-moi des questions précises pour les clarifier. Une question à la fois ou sous forme de liste numérotée.

4. Le chatbot pose des questions (par exemple : *Le menu est-il fixe en haut de la page pendant le défilement? Le formulaire de contact envoie-t-il un courriel réel?*). Répondez à chacune dans le chat.

5. Demandez ensuite à l'IA de mettre à jour la spécification :

   > Mets à jour le fichier `spec.md` en intégrant mes réponses. Génère la version complète et finale du fichier.

6. Remplacez le contenu de `.specify/spec.md` par la nouvelle version.

{{< notice style="warning" title="Important" >}}
Ne sautez pas l'étape de clarification. Plus les spécifications sont précises à ce stade, moins vous aurez de surprises lors de l'implémentation. C'est l'équivalent d'un bon cahier des charges en entreprise.
{{< /notice >}}

**À livrer :** Capturez l'écran du fichier `spec.md` final dans VS Code.

---

## Exercice 3 — Planifier la solution et générer les tâches

On choisit maintenant la technologie et l'architecture. C'est la seule étape où on parle de « comment » construire le site.

**Étapes — Plan technique :**

1. Dans la même conversation, envoyez ce prompt (collez `spec.md` à la place de `[SPEC]`) :

   > Sur la base de cette spécification :
   > [SPEC]
   >
   > Génère un plan technique (`plan.md`) en Markdown en utilisant la pile technologique suivante :
   > — Gabarit HTML5 avec Bootstrap 5 pour la mise en page responsive
   > — Un fichier `style.css` personnalisé pour les couleurs et la typographie
   > — JavaScript vanilla pour le menu mobile
   > — Pages statiques (pas de backend ni de base de données)
   > — Le formulaire de contact utilise Formspree (sans serveur)
   >
   > Détaille : la structure des fichiers, les composants Bootstrap utilisés par page, et l'architecture CSS.

2. Copiez la réponse dans `.specify/plan.md`.

**Étapes — Liste de tâches :**

3. Dans la même conversation, envoyez :

   > Sur la base du plan et de la spécification, génère une liste de tâches ordonnées (`tasks.md`) en Markdown.
   > Chaque tâche doit être numérotée, indépendante et assez précise pour être exécutée individuellement (par exemple : «Créer le fichier index.html avec la structure Bootstrap de base»).
   > Indique les dépendances entre tâches si nécessaire.

4. Copiez la réponse dans `.specify/tasks.md`.

5. Relisez `tasks.md` : chaque tâche est-elle claire et réalisable? Modifiez manuellement si une tâche vous semble vague.

{{< notice style="tip" title="Conseil" >}}
Si vous avez beaucoup modifié les fichiers manuellement, demandez à l'IA de vérifier la cohérence avant d'implémenter : collez `spec.md`, `plan.md` et `tasks.md` et demandez *«Y a-t-il des contradictions ou des manques entre ces trois documents?»*
{{< /notice >}}

**À livrer :** Capturez l'écran du fichier `tasks.md` avec la liste des tâches générées.

---

## Exercice 4 — Implémenter le site

Vous exécutez maintenant les tâches une par une : pour chacune, vous demandez au chatbot de générer le code, puis vous créez ou mettez à jour le fichier dans VS Code.

**Étapes — Implémentation tâche par tâche :**

1. Pour chaque tâche dans `tasks.md`, envoyez ce prompt (adaptez `[TÂCHE]` et collez le contexte pertinent) :

   > Contexte du projet (à garder en mémoire) :
   > [SPEC — coller spec.md]
   > [PLAN — coller les sections pertinentes de plan.md]
   >
   > Exécute uniquement la tâche suivante et génère le code complet :
   > [TÂCHE — coller la tâche depuis tasks.md]
   >
   > Génère uniquement le code de cette tâche, sans explications superflues.

2. Copiez le code généré et créez ou modifiez le fichier correspondant dans VS Code (`index.html`, `style.css`, etc.).

3. Répétez pour chaque tâche dans l'ordre de `tasks.md`.

4. Une fois toutes les tâches complétées, ouvrez `index.html` dans votre navigateur pour voir le résultat.

**Étapes — Vérification (converge) :**

5. Demandez au chatbot de vérifier la cohérence entre le code et les spécifications :

   > Voici ma spécification :
   > [SPEC]
   >
   > Voici le code que j'ai produit :
   > [Collez le contenu de index.html et style.css]
   >
   > Identifie les éléments de la spécification qui ne sont pas encore implémentés dans le code. Liste-les sous forme de nouvelles tâches.

6. Si l'IA identifie des manques, ajoutez les nouvelles tâches à `tasks.md` et implémentez-les (retour à l'étape 1).

7. Recommencez jusqu'à ce que l'IA confirme que tout est implémenté.

{{< notice style="info" title="Itération normale" >}}
Il est tout à fait normal de faire plusieurs cycles implémentation → vérification. Le SDD est une méthode **itérative** : chaque passage affine et complète le résultat. C'est bien plus fiable qu'un prompt unique qui essaie de tout faire d'un coup.
{{< /notice >}}

**À livrer :** Capturez l'écran du site ouvert dans le navigateur montrant au moins deux pages différentes, et le message de confirmation du chatbot indiquant que tout est implémenté.

---

## Récapitulatif du processus SDD (version manuelle)

```
Idée
  │
  ▼
Prompt constitution   → copier dans .specify/constitution.md
  │
  ▼
Prompt specify        → copier dans .specify/spec.md
  │
  ▼
Prompt clarify        → répondre aux questions → mettre à jour spec.md
  │
  ▼
Prompt plan           → copier dans .specify/plan.md
  │
  ▼
Prompt tasks          → copier dans .specify/tasks.md
  │
  ▼
Prompt implement      → tâche par tâche → créer les fichiers HTML/CSS
  │
  ▼
Prompt converge       → vérifier les manques → nouvelles tâches si besoin
```

La différence avec l'atelier SpecKit : les commandes `/speckit.*` sont remplacées par des **prompts structurés** que vous envoyez manuellement, et les fichiers sont créés par copier-coller plutôt qu'automatiquement. Le raisonnement et la rigueur sont exactement les mêmes.

