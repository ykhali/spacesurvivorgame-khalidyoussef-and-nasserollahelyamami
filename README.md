# Space Survivor 🚀

> **Projet Master 2 IA2 - CASA G1 (2025-2026)**
> **Développé par : Khalid Youssef & El Yamami Nasserollah**

---

## 📝 Explications et Mise en Situation

**Space Survivor** est plus qu'un simple jeu de tir ; c'est une simulation de comportements autonomes basés sur les **Steering Behaviors** (Comportements de Pilotage) de Craig Reynolds. Le but était de créer un écosystème où chaque entité (ennemi, allié, obstacle) navigue dans l'espace de manière organique et fluide, sans rails prédéfinis.

### Comportements Implémentés (Behaviors)

*   **Le Vaisseau Joueur** : Utilise une physique basée sur l'accélération et la friction (inertie spatiale), donnant une sensation de pilotage réaliste ("Drift").
*   **Ennemis "Seeker"** : Utilisent le comportement **`Seek`**. Ils calculent le vecteur vers le joueur et appliquent une force maximale pour le percuter. C'est l'ennemi le plus agressif.
*   **Ennemis "Shooter" (Tactiques)** : Utilisent une combinaison de **`Arrive`** (s'approcher mais ralentir pour viser) et **`Flee`** (fuir si le joueur est trop proche). Ils maintiennent une distance de combat idéale.
*   **Alliés (Drones de Soutien)** : Une prouesse d'IA de groupe. Ils utilisent le comportement **`Flocking`** (Séparation) pour ne pas se rentrer dedans, tout en utilisant **`Arrive`** pour suivre le joueur en formation et **`Seek`** pour chasser les ennemis proches.
*   **Serpents de l'Espace** : Une chaîne cinématique où chaque segment utilise **`Arrive`** pour suivre le segment précédent, créant un mouvement ondulatoire naturel.

---

## 🚀 Fonctionnalités Clés

*   **Système de Progression** : Niveaux infinis avec difficulté croissante (Ennemis -> Débris -> Mines).
*   **Power-ups Stratégiques** :
    *   🟩 **Soin** : Restaure la santé.
    *   🟧 **Arme Améliorée** : Augmente la cadence et les dégâts pendant 30s.
*   **Audio Procédural** : Aucun fichier MP3 ! Tous les sons (tirs, explosions, moteur) sont générés en temps réel par des oscillateurs et enveloppes (API Web Audio via p5.sound), rendant le jeu ultra-léger.

---

## ⚠️ Difficultés Rencontrées

1.  **Architecture & Héritage** : Au début du projet, beaucoup de code était dupliqué entre `Player`, `Enemy`, et `Ally`.
    *   *Solution* : Refactoring complet pour forcer toutes les entités mobiles à hériter d'une classe mère **`Vehicle`**, centralisant la physique (position, vélocité, accélération).
2.  **Gestion des Collisions** : Avec des centaines de balles et d'astéroïdes, les performances pouvaient chuter.
    *   *Solution* : Optimisation des boucles de collision et nettoyage automatique des entités hors écran.
3.  **Équilibrage du Gameplay** : Rendre le jeu difficile mais juste.
    *   *Solution* : Ajustement fin des forces maximales (`maxForce`) et vitesses (`maxSpeed`) pour que le joueur puisse toujours esquiver s'il est habile.

---

## 🏆 Ce dont je suis le plus fier

*   **L'IA des Alliés** : Voir le drone allié se détacher du joueur pour aller intercepter un ennemi, puis revenir se placer en formation à l'aile du joueur est extrêmement satisfaisant. Cela donne l'impression de ne pas être seul dans l'espace.
*   **Le Système de Son Procédural** : Avoir réussi à créer une ambiance sonore complète (y compris une voix de synthèse pour le Game Over !) sans aucun fichier externe.

---

## 🤖 Outils IA Utilisés

Ce projet a été assisté par un agent IA (Google Deepmind "Antigravity") pour l'accélération du développement.

*   **Spécifications** : L'IA a servi de "Pair Programmer". Je fournissais la logique de haut niveau (ex: "Je veux que les ennemis s'enfuient si je m'approche"), et l'IA proposait l'implémentation vectorielle correspondante.
*   **Debuging** : L'IA a été cruciale pour identifier rapidement les erreurs de syntaxe ou de logique dans les boucles de jeu complexes.

---

## 🎮 Contrôles

*   **Déplacement** : ZQSD / WASD / Flèches.
*   **Tir** : Clic Souris.
*   **Allié** : Touche **'P'**.
*   **Serpent** : Touche **'N'**.
*   **Debug** : Touche **'O'**.

---

## 🛠️ Installation et Lancement

Ce projet est une application web statique.

1.  **Prérequis** : Un navigateur web moderne (Chrome, Firefox, Edge).
2.  **Lancement** :
    *   Ouvrez simplement le fichier `index.html` dans votre navigateur.
    *   **Recommandé** : Utilisez une extension comme "Live Server" sur VS Code pour éviter les problèmes de chargement de fichiers locaux (bien que ce projet utilise principalement des scripts locaux et CDN).

---

## 📂 Structure du Projet

*   `index.html` : Point d'entrée du jeu.
*   `sketch.js` : Boucle principale du jeu (setup, draw, logique globale).
*   `player.js` : Classe du joueur (mouvement, tir, santé).
*   `enemy.js` : Classes des ennemis (Seeker, Shooter).
*   `ally.js` : Classe des alliés (IA de groupe et combat).
*   `bullet.js` : Gestion des projectiles.
*   `obstacle.js` : Mines et Débris.
*   `food.js` : Gestion des Power-ups (Energie, Arme).
*   `vehicle.js` : Classe mère physique (héritage).
*   `sound.js` : Gestionnaire audio (Oscillateurs et Synthèse vocale).
*   `particles.js` : Système de particules pour les effets visuels.
*   `style.css` : Styles de l'interface utilisateur.
*   `/assets` : Contient les images utilisées dans le jeu.
