# 🌌 TP 1 : Maîtrise des GPIO - Systèmes Embarqués

Bienvenue dans le dépôt du **Travail Pratique N°1** consacré à la programmation matérielle (Bare Metal) des GPIO sur microcontrôleur **STM32 Nucleo-C031C6** à l'aide de la bibliothèque HAL.

Ce projet se distingue par son approche innovante : il inclut non seulement les codes sources en C, mais également un **rapport de laboratoire interactif (HTML/CSS/JS)** intégrant un véritable **Jumeau Numérique (Digital Twin)** du montage matériel.

## 🚀 Fonctionnalités du Compte-Rendu Interactif

Le fichier `compte_rendu_tp1.html` est une application web autonome au design "Deep Space" comprenant :
* **Une Page de Garde immersive** avec effet de défilement.
* **Un Simulateur Dynamique Intelligent :** Le comportement du montage virtuel (bouton et LED) change automatiquement en fonction de l'onglet de manipulation sélectionné (Simulation d'un clignotement autonome, d'un contrôle direct, ou d'une machine à états complexe).
* **Un système d'onglets** pour naviguer proprement entre les différents codes sources (C) développés.
* **Une section Post-Lab détaillée** avec des fiches d'analyse technique expliquant les concepts sous-jacents (Pull-up, anti-rebond, polling vs interruptions, etc.).

## 📋 Manipulations Réalisées (Code C)

1. **Clignotement Simple (500ms) :** Utilisation de `HAL_GPIO_TogglePin()` combiné à `HAL_Delay()` pour créer un cycle régulier et autonome.
2. **Contrôle Direct par Bouton :** Lecture de l'état logique d'un bouton poussoir (configuration Pull-up interne sur PC13). La LED externe (PA5) s'allume de manière synchrone avec le maintien physique du bouton.
3. **Le Défi (Variateur de Vitesse à 3 Modes) :** Création d'une machine à états non-bloquante de niveau professionnel. Remplacement des délais bloquants par `HAL_GetTick()` pour garantir une détection instantanée du bouton. Chaque clic permet de cycler entre trois modes : Clignotement lent (1000ms), Clignotement rapide (200ms), et Allumage fixe. Filtre logiciel anti-rebond inclus.

## 🛠️ Matériel & Outils Requis

* **Carte :** STM32 Nucleo-C031C6 (Matériel physique ou simulation via [Wokwi](https://wokwi.com/stm32))
* **Composants :** 1x LED, 1x Résistance (220Ω - 330Ω), fils de connexion.
* **Environnement C :** STM32CubeIDE (Génération de code via CubeMX).
* **Environnement Web :** N'importe quel navigateur web moderne (Chrome, Firefox, Edge) pour ouvrir le rapport HTML.

## ⚙️ Instructions d'Exécution

### 1. Visualiser le Rapport Interactif
Double-cliquez simplement sur le fichier `compte_rendu_tp1.html` pour l'ouvrir dans votre navigateur. Interagissez avec les boutons virtuels et les onglets pour tester les différentes logiques implémentées.

### 2. Simuler le Code C (Wokwi)
1. Créez un projet "STM32 Nucleo64 C031C6" sur Wokwi.
2. Câblez l'anode d'une LED externe sur la broche **PA5** et la cathode à une résistance reliée à la masse (GND). Le bouton utilisateur bleu intégré est sur **PC13**.
3. Remplacez le contenu par défaut par les fichiers `main.c` et `main.h` (actuellement configurés pour le Défi 3 Modes).
4. Lancez la simulation (Play) pour tester la réactivité de la machine à états.

## 👥 Équipe du Projet

**Année Universitaire :** 2025/2026
* **Binôme :** Dahane Ahmed Lamine & Tabbi Meriem
* **Enseignante Responsable :** Mme. Afaf Saoud
