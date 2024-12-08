# DorfromantikGame

## Introduction

Ce projet a été conçu dans le cadre du Semestre 3 du BUT Informatique à l'IUT de Fontainebleau. L'objectif était, en JAVA, de reproduire la logique qui se cache derrière le jeu [Dorfromantik](https://store.steampowered.com/app/1455840/Dorfromantik/). Le projet a été réaliser en trio avec l'aide d'Abed Bridja et Wilfried Brigitte.

## Le sujet

Dans ce jeu inspiré librement de Dorfromantik, le joueur doit assembler des tuiles hexagonales pour former un paysage harmonieux.

Vous produirez un programme écrit en Java, sans emprunt extérieur (sauf l'API officielle), et accompagné d'un rapport. Le travail sera fait en binôme ou trinôme, et devra être terminé avant le dimanche 27 octobre 2024 à 23h59.
La partie logicielle sera développée dès le départ à l'aide du serveur Gitea du département. Le rapport prendra la forme d'un fichier au format PDF joint aux sources.

### Tuiles
Les tuiles servent à délimiter cinq terrains différents : mer, champ, pré, forêt et montagne.
Une tuile peut contenir un ou deux terrains. Lorsque deux terrains cohabitent sur une tuile, ils se partagent les côtés : 1+5, 2+4 ou 3+3.

### Parties
Une partie se déroule de la façon suivante. La première tuile est posée automatiquement. À chaque tour, une tuile est révélée au joueur, et celui-ci choisit la position et l'orientation dans laquelle poser cette tuile. La seule contrainte est que la nouvelle tuile doit être adjacente à une tuile déjà posée.
La partie se termine lorsque 50 tuiles ont été posées. On calcule alors le score du joueur en additionnant les points obtenus pour chaque poche de terrain. Si deux tuiles sont connectées par des côtés qui montrent le même terrain, ces tuiles appartiennent à la même poche. Le nombre de tuiles dans une poche, élévé au carré, donne le nombre de points accordés.
2²+2²+2²+2²+1² = 17 points
2²+2²+2²+2²+1² = 17 points
Notez qu'un paysage peut contenir plusieurs poches isolées du même terrain. Une tuile qui contient deux terrains compte obligatoirement pour deux poches différentes.

### Serveur
Un serveur de base de données sert à retenir les parties disponibles et les scores des joueurs (de façon anonyme).
Pour que deux scores puissent être comparés, il faut qu'ils correspondent à des parties qui ont utilisé la même série de tuiles.
Le serveur se souvient donc d'un certain nombre de séries sur lesquelles les joueurs peuvent baser leur partie. Il n'est pas demandé de coder la possibilité d'ajouter une série, mais pour pouvoir tester le programme, plusieurs séries devront être déjà présentes sur le serveur.
Lorsqu'un joueur débute une partie, il doit choisir parmi les séries disponibles (sans voir leur contenu). À la fin de la partie, le programme utilise les scores connus du serveur pour cette série afin de montrer au joueur la qualité de son score.

## Installation

Pour lancer le jeu, récupérez l'ensemble des fichiers.
Entrez dans le dossier du projet puis exécutez les commandes suivantes :
  ```bash
    make jar
    make run
```
Ces 2 commandes permettent de compiler le programme puis de le lancer.

## Auteurs

Abed Bridja, Wilfried Brigitte, Christopher Dubreuil

## Note

14,50/20 (Évaluée par notre professeur de développment Luc Hernandez)
