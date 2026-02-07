# Space Survivor

**Space Survivor** est un jeu de tir spatial intense et rapide développé en JavaScript avec la bibliothèque **p5.js**. Survivez aux vagues d'ennemis, évitez les astéroïdes, recrutez des alliés et améliorez votre vaisseau pour dominer la galaxie !

Projet réalisé dans le cadre du Master 2 IA2 CASA G1 2025-2026.

## 🚀 Fonctionnalités

*   **Combat Spatial Dynamique** : Affrontez des ennemis "Seeker" (qui vous foncent dessus) et "Shooter" (qui vous tirent dessus).
*   **Système de Niveaux** : La difficulté augmente tous les 300 points.
    *   **Niveau 1** : Ennemis de base.
    *   **Niveau 2+** : Apparition de **Débris Spatiaux** rapides.
    *   **Niveau 3+** : Apparition de **Mines Spatiales** explosives. Vos balles deviennent plus puissantes (violettes).
*   **Alliés (Nouveau !)** : Appuyez sur **'P'** pour faire apparaître des drones alliés qui vous suivent et attaquent automatiquement les ennemis.
    *   Comportement de groupe (Flocking) : Ils volent en formation et évitent les collisions.
    *   "Seek & Destroy" : Ils chassent activement les menaces.
*   **Power-ups** :
    *   🟩 **Énergie (Vert)** : Boost de vitesse.
    *   🟧 **Arme (Orange)** : Augmente la puissance de feu (+2 niveaux) pendant 30 secondes.
*   **Environnement** : Astéroïdes destructibles, Serpents de l'espace (entités neutres qui mangent de la biomasse), et système de particules pour les explosions.
*   **Audio Immersif** :
    *   Effets sonores procéduraux pour les tirs et les explosions.
    *   Voix "Game Over" amusante et grave (Synthèse vocale).

## 🎮 Contrôles

*   **Déplacement** : Touches Fléchées ou ZQSD (ZQSD recommandé).
*   **Viser** : La souris (le vaisseau regarde vers le curseur).
*   **Tirer** : Clic Gauche de la souris.
*   **Appeler un Allié** : Touche **'P'**.
*   **Faire apparaître un Serpent** : Touche **'N'** (Fun/Debug).
*   **Activer debug mode** : Touche **'O'**
*   **Quiter le jeu** : Clicker sur le bouton **Exit**
*   **Recommencer** : Cliquez sur le bouton "Restart" à l'écran de fin.

## 🛠️ Installation et Lancement

Ce projet est une application web statique.

1.  **Prérequis** : Un navigateur web moderne (Chrome, Firefox, Edge).
2.  **Lancement** :
    *   Ouvrez simplement le fichier `index.html` dans votre navigateur.
    *   **Recommandé** : Utilisez une extension comme "Live Server" sur VS Code pour éviter les problèmes de chargement de fichiers locaux (bien que ce projet utilise principalement des scripts locaux et CDN).

## 📂 Structure du Projet

*   `index.html` : Point d'entrée du jeu.
*   `sketch.js` : Boucle principale du jeu (setup, draw, logique globale).
*   `player.js` : Classe du joueur (mouvement, tir, santé).
*   `enemy.js` : Classes des ennemis (Seeker, Shooter).
*   `ally.js` : Classe des alliés (IA de groupe et combat).
*   `bullet.js` : Gestion des projectiles.
*   `obstacle.js` : Mines et Débris.
*   `sound.js` : Gestionnaire audio (Oscillateurs et Synthèse vocale).
*   `particles.js` : Système de particules pour les effets visuels.
*   `style.css` : Styles de l'interface utilisateur.
*   `/assets` : Contient les images utilisées dans le jeu.

## 👥 Crédits

- Développé par **Khalid Youssef** et **Nasserollah el yamami**
- Matiere IA réctive
- Master 2 IA2 - Université côte d'azur
- Année Universitaire : 2025-2026.
