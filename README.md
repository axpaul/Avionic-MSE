# Avionic-MSE
*MSE experimental rocket avionic (On-board electronics), Version 2023 launched at C'space*

*CC BY-NC-SA 4.0, Copyright 2023 Miailhe Paul, all rights reserved*

![alt tag](https://github.com/axpaul/Avionic-MSE/blob/main/Image/Publication%20MSE.png)

Grabcad :
- https://grabcad.com/library/avionics-system-for-mse-rocket-1

---

# Projet MarSoniquE (MSE)

Le projet **MarSoniquE (MSE)**, également connu sous le nom de **Marsaut E**, vise à concevoir une fusée expérimentale robuste et adaptée aux vols supersoniques pour mener des études spécifiques dans ce domaine. À ce jour, aucune fusée expérimentale n’a réalisé de vol nominal avec des caractéristiques similaires lors des événements du **C’Space** sur le site d’essai du 1er RHP. En s’appuyant sur une démarche Open Source, le projet cherche à fournir un cadre technique permettant de relever ce défi.

Le développement s’appuie sur l’expérience acquise avec les avioniques des projets précédents **Marsaut 0** et **Marsaut 1**. L’objectif principal est de créer une structure résistante aux contraintes mécaniques d’un vol supersonique, avec des accélérations atteignant **28g** et des vibrations significatives dans le domaine transsonique. Par ailleurs, la crise actuelle des semi-conducteurs impose des choix restrictifs en termes de composants.

---

## Composants techniques

### Microcontrôleur
- **RP2040** : Microcontrôleur de Raspberry basé sur un cœur **ARM Cortex-M0+**.  
  Il intègre des fonctionnalités telles que la gestion de mémoire flash (Quad-SPI) et répond aux besoins du projet.

---

### Instrumentation

#### Capteurs analogiques
- **26PCGFA6D** : Capteur de pression différentiel pour la sonde Pitot, mesurant jusqu’à **250 PSI**.
  - **Amplificateur** : Utilisation de l’**INA121** pour amplifier proprement le signal.
  - **Convertisseur analogique-numérique** : **ADS1014** pour transformer le signal amplifié en données numériques exploitables.

#### Capteurs numériques
- **IMU MPU9250** : Capteur inertiel 6 axes, capable de mesurer des accélérations jusqu’à **16g**.  
- **LPS22HB** : Altimètre combinant mesures de pression et de température.  
- **GPS MAX-M10S** : Module GPS compact, opérationnel jusqu’à **80 000 m d’altitude**, **500 m/s** de vitesse et avec une dynamique maximale de **4g**.

---

### Transmission radio
- **SX1276** : Transcepteur LoRa fonctionnant sur **868 MHz**, permettant une communication longue portée et fiable.  
  Il est conçu pour fonctionner efficacement dans des conditions de faible signal grâce à sa sensibilité élevée et sa réduction de bruit intégrée.

---

### Stockage
- **W25Q128JV** : Mémoire flash **SPI de 128 Mbits** utilisée pour l’enregistrement des données en vol.

---

### Alimentation
- **LM340AT** : Régulateur de tension fournissant des tensions fixes de **5V**, **12V** et **15V**, avec une capacité de courant de **1A**.  
- **1210L110/16WR** : Fusible réarmable **PTC** protégeant le circuit contre les surintensités.

---

### Drivers et circuits
- **DRV8871DDARQ1** : Contrôleur de moteur à courant continu.  
  - Tension d’alimentation : **6,5V à 45V**.  
  - Courant de sortie : jusqu’à **3,6A**.  
  Ce composant est utilisé pour piloter les systèmes mécaniques, tels que la trappe de récupération.

- **74HC14D,653** : Porte logique inverseuse Schmitt.  
  Elle stabilise les signaux bruités des fins de course des moteurs et garantit un fonctionnement sûr du système de récupération.

---

### Synoptic

Le schéma synotique du projet avionique :
![alt text](https://github.com/axpaul/Avionic-MSE/blob/main/Image/Sypnotique%20MSE.png)

---

### Pinout séquenceur & sensor :

![alt text](https://github.com/axpaul/Avionic-MSE/blob/main/Image/MSE%20SEQ%20PINOUT.png)
![alt text](https://github.com/axpaul/Avionic-MSE/blob/main/Image/MSE%20SENSOR%20PINOUT.png)

---

### Tableau des cartes :

| 3D | Routing  | Description |
|:---:|:---:|:---:|
| ![alt text](https://github.com/axpaul/Avionic-MSE/blob/main/Image/3D-Avionique.png) | ![alt text](https://github.com/axpaul/Avionic-MSE/blob/main/Image/Routage-Avionic-MSE.png) | Carte avionique V°1|
| ![alt text](https://github.com/axpaul/Avionic-MSE/blob/main/Image/3D-Interface.png) | ![alt text](https://github.com/axpaul/Avionic-MSE/blob/main/Image/Routage-Interface-MSE.png) | Carte interface V°1 |
| ![alt text](https://github.com/axpaul/Avionic-MSE/blob/main/Image/3D-Sensor.png)  |  ![alt text](https://github.com/axpaul/Avionic-MSE/blob/main/Image/Routage-Sensor-MSE.png) | Carte capteur analogique V°1 |
| ![alt text](https://github.com/axpaul/Avionic-MSE/blob/main/Image/3D-IHM.png)  |  ![alt text](https://github.com/axpaul/Avionic-MSE/blob/main/Image/Routage-IHM-MSE.png) | Carte IHM V°1 |

## Licence 

![alt tag](https://github.com/axpaul/Avionic-Marsaut1/blob/main/Cc-by-nc-sa_icon.svg.png)
