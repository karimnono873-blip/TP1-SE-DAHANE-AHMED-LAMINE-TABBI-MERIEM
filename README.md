# 🌌 TP 1 : Maîtrise des GPIO - Systèmes Embarqués

Bienvenue dans le dépôt du **Travail Pratique N°1** consacré à la programmation matérielle (Bare Metal) des GPIO sur le microcontrôleur **STM32 Nucleo-C031C6** à l'aide de la bibliothèque HAL.

Ce projet se distingue par la création d'un **rapport de laboratoire interactif (HTML/CSS/JS)** au design "Deep Space", intégrant des **Jumeaux Numériques (Digital Twins)** pour simuler le comportement du matériel directement dans le navigateur.

## 🚀 Fonctionnalités du Compte-Rendu Interactif

Le fichier `compte_rendu_tp1.html` est une application web autonome comprenant :
* **Une Page de Garde immersive** avec effet de défilement pour une présentation académique soignée.
* **Architecture à 3 Simulateurs Isolés :** Pour garantir une fiabilité totale à 100%, chaque manipulation possède son propre circuit interactif indépendant. Aucun conflit JavaScript possible entre les différents modes !
* **Un système d'onglets fluide** pour naviguer proprement entre les circuits et les codes sources (C) associés.
* **Une section Post-Lab détaillée** avec des fiches d'analyse technique expliquant les concepts sous-jacents (Pull-up, anti-rebond, polling vs machine à états, etc.).

## 📋 Manipulations Réalisées (Code C & Simulation)

1. **Clignotement Simple (500ms) :** * *Code :* Utilisation de `HAL_GPIO_TogglePin()` combiné à `HAL_Delay()`.
   * *Simulation :* La LED virtuelle clignote de manière autonome toutes les demi-secondes. Le bouton est désactivé.
2. **Contrôle Direct par Bouton :** * *Code :* Lecture de l'état logique d'un bouton poussoir (Pull-up interne sur PC13).
   * *Simulation :* La LED externe (PA5) s'allume de manière synchrone avec le maintien physique du bouton virtuel.
3. **Le Défi (Variateur de Vitesse à 3 Modes) :** * *Code :* Création d'une machine à états non-bloquante de niveau professionnel. Remplacement des délais bloquants par `HAL_GetTick()` pour garantir une détection instantanée du bouton. 
   * *Simulation :* Chaque clic permet de cycler le circuit entre trois modes : Clignotement lent (1000ms), Clignotement rapide (200ms), et Allumage fixe.

## 🛠️ Matériel & Outils Requis

* **Carte :** STM32 Nucleo-C031C6 (Matériel physique ou simulation via [Wokwi](https://wokwi.com/stm32))
* **Composants :** 1x LED, 1x Résistance (220Ω - 330Ω), fils de connexion.
* **Environnement C :** STM32CubeIDE (Génération de code via CubeMX).
* **Environnement Web :** N'importe quel navigateur web moderne pour ouvrir le rapport HTML.

## ⚙️ Instructions d'Exécution

### 1. Visualiser le Rapport Interactif
Double-cliquez simplement sur le fichier `compte_rendu_tp1.html` pour l'ouvrir. Interagissez avec les boutons virtuels de chaque onglet pour tester les logiques implémentées.

### 2. Simuler le Code C (Wokwi)
1. Créez un projet "STM32 Nucleo64 C031C6" sur Wokwi.
2. Câblez l'anode d'une LED externe sur la broche **PA5** et la cathode à une résistance reliée à la masse (GND). Le bouton utilisateur bleu intégré est sur **PC13**.
3. Remplacez le contenu par défaut par les fichiers `main.c` et `main.h` de ce dépôt.
4. Lancez la simulation (Play) pour tester le code sur le matériel virtuel.

## 👥 Équipe du Projet

**Année Universitaire :** 2025/2026
* **Binôme :** Dahane Ahmed Lamine & Tabbi Meriem
* **Enseignante Responsable :** Mme. Afaf Saoud
