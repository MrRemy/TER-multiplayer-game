# TER développement d'un jeu multijoueur

## Introduction 
### [WIP]

## Technologies utilisés

### Socket.io

[socket.io](http://socket.io) est un outil puissant permettant la communication  en temps réel entre un serveur et un ou plusieurs clients. Sa compatibilité avec des technologies récentes tel que les web sockets, mais aussi avec des basiques du networking comme JSON, ... le rende très flexible.
Sa simplicité d'utilisation et notre familiarité avec cette technologie (utilisation lors de différents projets) nous ont poussés à son utilisation pour ce TER.

### Node.js

[node.js](http://nodejs.org/) est un outil facile d'accès et polyvalent, il est en effet aisé d'héberger un projet Node.js de par son support par la plupart des fournisseurs d'hébergement, de même son déploiement sur un serveur personnel ne présente pas de difficultés.
Un grand nombre de modules sont disponibles pour Node.js et parmi ces derniers on fera surtout mention d'[Express](http://expressjs.com/) couvrant pour nous la totalité des interactions entre notre client et [socket.io](http://socket.io).

### p5.js
[p5.js](https://p5js.org/) est une librairie permettant une certaine facilité dans le développement de contenu créatif, ainsi elle est tout indiqué pour l'élaboration d'un jeu.

## Utilisation et "quick start"
Toutes les étapes de l’utilisation du projet seront disponibles [ici](https://github.com/maxime-samak/TER-multiplayer-game#quick-start).

## Jeu multijoueurs en temps réel
### [WIP]

## Le jeu à proprement parler
La création d'un jeu simple, nécessitant une connexion à un serveur en temps réel a été l'une des premières étapes abordées lors de ce TER.
[agar.io](https://agar.io) regroupant ces différentes caractéristiques, notre jeu se base sur les concepts proposés par celui-ci.

### Un peu de gameplay
#### [WIP]

### Hardware et Browser
Toutes les machines ne sont pas équivalentes en termes de puissance et donc de rapidité, il en va de même pour les browsers qui de par leurs spécificités propres n'auront pas toujours la même efficacité pour une tâche donnée.
Une étape essentielle du développement d'un jeu web est donc de pallier à ces inégalités qui toucheront les utilisateurs.

#### Frame rate
Prenons un exemple simple pour illustrer ce phénomène : un block se trouve sur un axe X, il se déplace sur cet axe de +1 pixel par frame. Ainsi le joueur A faisant tourner son jeu à 30 fps verra se déplacer ce block de 30 pixels sur l'axe X en 1 seconde, seulement le joueur B ayant un ordinateur plus performant et ayant 60 fps verra ce même block se déplacer de 60 pixels en 1 seconde.
Il y a là un véritable problème !

Solution : pour s'assurer que notre block se déplace toujours à la même vitesse nous allons introduire le concept d'un delta de temps entre deux rafraîchissements. Cette valeur exprimé en millisecondes représente le temps écoulé entre deux itérations de notre boucle de rendu graphique.
A 30 fps on a donc un delta d'environ 33.3ms, et à 60 fps on obtient environ 16.66ms pour notre delta on peut désormais multiplier notre valeur de déplacement (+1 sur l'axe x) par nos delta pour obtenir un mouvement à 1 pixel par seconde pour nos deux joueurs.

![Frame rate independeance](https://github.com/maxime-samak/TER-multiplayer-game/blob/master/doc/assets/deltatime.png)

Si cet exemple porte uniquement sur les frames rate il ne faut pas oublier que le même principe devrait être appliqué pour toutes valeurs subissant un changement au cours du temps de manière a assurer une cohérence du jeu pour ses joueurs.



## Notes et références
Cette étude est basé en partie sur les travaux de [Sven Bergström](https://underscorediscovery.com/#home)

[Références complémentaires](https://github.com/maxime-samak/TER-multiplayer-game/blob/master/doc/ref.md)
