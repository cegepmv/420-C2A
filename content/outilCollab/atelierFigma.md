+++
date = '2026-08-09T13:50:00-04:00'
draft = false
title = 'Atelier Figma'
+++


## Inscription à Figma

Création d'un compte étudiant (pro gratuit).

Voir l'article suivant: https://www.figma.com/fr-fr/education/higher-education/

## Sélection

Utilisation de la flèche et du clavier CTRL et SHIFT. Double clique pour sélectionner un élément enfant dans un élément parent. On peut également utiliser la touche ALT pour copier la sélection (ou CTRL-D pour dupliquer).

## Frames

En créant un frame, il vous est possible de choisir un prérèglage pour un téléphone par exemple. Vous pouvez utiliser plusieurs frames dans Figma. Vous pouvez également utiliser les layout grid pour avoir une référence pour placer les éléments dans votre frame.

## Formes géométriques

Dans Figma, il est possible de combiner plusieurs formes géométriques pour faire un bouton, un ensemble complexe de composantes, etc.

## Composante

Créer des instances, détacher des instances de composante, etc. Il est possible d'exporter vos composantes en format image (png, jpg) pour l'utiliser dans votre application ou votre site web.

### UI Kits

Pour nous faciliter la vie, Figma nous propose des kits qui sont utilisés dans le développement tel que 
Material Design Kit. Ce kit fournit jusqu'à 245 composants prêt à être utilisés. Pour ajouter ce kit, 
il vous faut aller dans le menu en haut à gauche (logo Figma) et choisir **Libraries**. 

![](/images/uikits.png)

### Propriétés pour réutiliser les composantes

En ajoutant des propriétés à une composante, on augmente sa réusabilité. Il est donc possible de créer des instances et de changer en un clique son aparence. De plus, il est possible de détacher une instance d'une composante pour en créer une nouvelle.

![](/images/composantepro.png)

### Exportation des composantes en CSS, Android, etc.

Comme vous pouvez voir sur l'image ci-bas, vous aurez la possibilité d'exporter le style en CSS quand votre maquette sera terminée.

![](/images/exportcss.png)

### Publiez vos composantes

Si vous publiez vos composantes, il est possible de les réutiliser en récupérant vos librairies via l'onglet asset. Si vous avez créé des variants, vous pourrez choisir le variant de votre choix pour l'instance choisie.

## Grilles et repères

Il est possible d'afficher une grille et d'y mettre plusieurs repères. Pour se faire, aller dans le menu principal et choisir dans View l'option Rulers. Il est plus facile de créer ces formes avec des repères. Cela applique un magnétisme sur les lignes repères.

![](/images/layoutgrid.png)

# Auto-Layout

Change la disposition de vos composantes et change l'espace entre les éléments. On peut ajuster de façon regrouper l'espacement entre chaque composante et permettre d'harmoniser le contenu. On peut séparer l'espacement en faisant des groupes (CRTL-G). Il est alors possible de séparer les éléments du auto-layout en groupe.

On peut disposer des éléments à la verticale, horizontale ou avec des sauts de ligne quand l'espace n'est plus suffisant dans le frame qui est configuré en auto-layout.

# Contraintes

![](/images/constraints.png)

Les contraintes permettent de définir comment un élément réagit aux changements de dimension de son parent, en garantissant une mise en page adaptable et cohérente. En utilisant les contraintes, un élément peut être fixé à un bord, centré ou redimensionné dynamiquement, facilitant ainsi la conception de designs responsifs.

![](/images/constraints2.png)

On peut forcer la contraintes à gauche, gauche et droite, droite, etc. 



# Démo avec un plugin **Content Reel**

1. Création d'un frame de type iPhone 16 Pro. (Frame)
2. Créer un rectancle avec un cercle et du texte pour le nom et le numéro de téléphone. (Forme)
3. Utilisez la fonction **Auto-Layout** (Sélection complète et clique droit de la souris - Add Auto-Layout). 
4. Créez un **component** avec votre rectangle. Utilisez le clique droit de la souris pour créer le composant.
5. Copiez ensuite plusieurs composantes de votre rectangle. (Soit avec **ALT** ou **CRTL-D**)
6. Installez le plugin **Content reel**. Il sert à remplir certain champ texte ou image avec des valeurs déjà fournies.

7. Sélectionnez tous vos cercles (SHIFT+CTRL + clique de la souris) et cliquez sur le bouton droit de votre souris, plugin, Content Reel.
8. Choisissez dans le plugin -> image, avatar (male ou female). 
![](/images/imgavatar.png)
9. Choisissez le texte du nom de votre personnage.
![](/images/selectionFigma.png)
10. Après avoir sélectionné *Text* - *Full Name*
![](/images/selectionName.png)

# Prototypage dans Figma avec dev mode

Pour tester votre application dans Figma, vous devez cliquer sur Prototype en haut à droite. Ensuite, Sélectionnez
un **device** pour le voir dans le format de votre appareil.

![](/images/prototype.png)

## Créer des interactions

Créez plusieurs **frames** et lier les frames avec le **bouton** d'action pour déclencher un changement d'écran.

### Points d'entrés et de retours
Vous pouvez configurer un point d'entré de votre simulation et le déplacer d'un écran à l'autre. Il est également
possible de faire un retour en arrière en sélectionnant un bouton (vers back).

![](/images/proto_flow.png)

### Animation entre les entrées et sorties

Pour faire une transition plus en douceur, il est possible de choisir des animations entre les écrans.

### Ready for dev

Il est possible de mettre une section de votre travail en mode **ready for dev**. 

Après cette opération, vous pourrez récupérer les styles (avec les unités px ou rem), le code et les assets (les images) pour démarrer votre développement.




# Référence

Gladys Diandoki, *UX Writing Quand le contenu tranforme l'expérience*, Éditions Eyrolles (2022)

Cours complet pour Designer UI / UX 2025 avec [Rudy Palfray](https://www.udemy.com/user/palfray-rudy/)

https://www.udemy.com/course/figma-cours-complet

Lien pour l'exercice:
https://www.figma.com/file/sSt7nzwaK3qb3typM4y5q7/Exercices-Udemy







