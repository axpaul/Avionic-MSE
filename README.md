# Avionic-MSE
MSE experimental rocket avionic (On-board electronics) created by Paul Miailhe, Version 2023 launched at C'space

*CC BY-NC-SA 4.0*

Ce nouveau séquenceur descend de l'expérience acquise sur les précédentes avioniques de Marsaut 0&1. Le but principal ici est de réaliser un objet résistant à l'environnement mécanique qui va être rencontré lors du vol. En effet, d'après les premières études théoriques, notre fusée rencontrera une accélération de 28g et d'importants phénomènes vibratoires dans le domaine transsonique. De plus, la crise actuelle des semiconducteurs nous force à faire des choix restrictifs de composant. C'est la raison principale du remplacement de nombreux composants, comme les STM32 de chez STmicroélectronique ou le BMP280 de chez BOSH n'étant plus disponibles. 

## Microcontrôleur

Ainsi, nous avons sélectionné le microcontrôleur RP2040 pour notre projet, provenant de chez Raspberry, ayant un cœur ARM Cortex-M0+ et ces différents drivers intégrés comme le lecteur de flash (Quad-SPI) est bien adapté à notre solution.

## Capteurs

### Instrumentation Analogique

Le capteur 26PCGFA6D est un capteur de pression différentiel qui sera utilisé pour la sonde Pitot. Ce capteur, qui possède une capacité de lecture allant jusqu'à 250 PSI, est parfaitement adapté à la plage de mesures de notre vol. Cependant, étant un capteur analogique et fonctionnant sur le principe du pont de Wheatstone, le 26PCGFA6D nécessite un traitement spécifique du signal. Pour ce faire, nous utiliserons l'amplificateur opérationnel à instrumentation INA121 pour amplifier proprement le signal du capteur. Le signal analogique amplifié est ensuite converti en signal numérique grâce à l'utilisation d'un convertisseur analogique-numérique (CAN) ADS1014. Cette combinaison permet d'obtenir un signal numérique précis et exploitable à partir du signal analogique brut du capteur 26PCGFA6D.

### Instrumentation Numérique

Pour acquérir l'ensemble des paramètres de base du vol de la fusée, nous utiliserons :

- L'IMU - 6 axes, ICM20649 (capable de lire jusqu'à 30G)
- L'altimètre (pression/température) LPS22HB

## GPS

### GPS MAX-M10S

Le MAX-M10S est un module GPS compact et performant, capable de fournir des coordonnées précises, des informations de temps et de vitesse. Ce module GPS peut fonctionner efficacement jusqu'à une altitude de 80 000 mètres, une vitesse de 500 m/s et une dynamique inférieure ou égale à 4g. Ces limites opérationnelles le rendent idéal pour des applications à haute altitude et haute vitesse comme notre fusée supersonique.

## Radio

### Module radio SX1276 868mHz

Le SX1276 est un transcepteur RF qui utilise la technologie LoRa (Long Range), permettant une communication sans fil longue portée. Cette technologie de communication est idéale pour notre fusée, car elle permet une transmission de données fiable même à de grandes distances. En outre, le SX1276 dispose d'une excellente sensibilité de réception et d'une technologie de réduction de bruit intégrée. Cela signifie que même dans des conditions de signal faible, ce module est capable de maintenir une communication claire et stable. Ce sont des caractéristiques essentielles pour garantir la réussite de notre projet.

## Enregistrement

### Flash W25Q128JV SPI 128 Mbit

La W25Q128JV offre une capacité de stockage impressionnante de 128 Mbits, ce qui permet de stocker une grande quantité de données. Ce composant utilise une interface SPI (Serial Peripheral Interface) pour une communication rapide et efficace avec d'autres composants électroniques.

## Puissance

### Régulateur LM340AT

Le LM340AT est un régulateur de tension qui assure une alimentation stable pour les composants électroniques. Il peut fournir des tensions de sortie fixes de 5V, 12V et 15V. Il peut délivrer un courant jusqu'à 1A, ce qui le rend capable d'alimenter un large éventail de dispositifs. Le LM340AT est connu pour sa fiabilité et sa stabilité, offrant une performance constante même dans des conditions difficiles.

### 1210L110/16WR Littelfuse PTC

Le 1210L110/16WR est un fusible réarmable PTC (Positive Temperature Coefficient) qui offre une protection efficace contre les surintensités dans votre circuit. Contrairement

## Driver

Le contrôle des différents systèmes de la fusée nécessite des drivers efficaces et robustes pour assurer un fonctionnement optimal. Nous avons donc sélectionné les composants suivants :

### Driver pont en H DRV8871DDARQ1

Le DRV8871DDARQ1 est un contrôleur de moteur à courant continu (DC) de haute performance. Il est capable de piloter efficacement un moteur avec des commandes précises, ce qui est essentiel pour le contrôle du mouvement de la trappe de notre fusée.

Ce driver offre une performance élevée avec une tension d'alimentation de 6.5V à 45V et un courant de sortie de jusqu'à 3.6A. Ces spécifications garantissent qu'il peut gérer les demandes de nos moteurs de manière efficace et fiable.

### 74HC14D,653

Le 74HC14D,653 est une porte logique inverseuse avec des entrées de type Schmitt. Cette porte logique joue un rôle crucial dans la détection de la fin de course des moteurs de notre fusée.

En transformant des signaux d'entrée analogiques ou numériques en signaux de sortie numériques standardisés, le 74HC14D,653 permet de nettoyer les signaux bruités. C'est une caractéristique essentielle pour garantir un fonctionnement sûr et efficace du système de récupération de notre fusée.



| 3D | Routing  | Description |
|:---:|:---:|:---:|
| ![alt text](https://github.com/axpaul/Avionic-Marsaut1/blob/main/Image/MS1-3D%20V1.png) | ![alt text](https://github.com/axpaul/Avionic-Marsaut1/blob/main/Image/MS1-routage%20V1.png) | V°1 of avionics for Marsaut 1, 6 layers |
| ![alt text](https://github.com/axpaul/Avionic-Marsaut1/blob/main/Image/MS1-3D%20V2.png) | ![alt text](https://github.com/axpaul/Avionic-Marsaut1/blob/main/Image/MS1-routage%20N%C2%B03%20V2.png) | V°2 of avionics for Marsaut 1, 4 layers, fly model |
| ![alt text](https://github.com/axpaul/Avionic-Marsaut1/blob/main/Image/MSA-IHM-3D.png)  |  ![alt text](https://github.com/axpaul/Avionic-Marsaut1/blob/main/Image/MS1-IHM-routage.png) | V°1 of IHM for Marsaut 1, 4 layers, fly model |

## Licence 

![alt tag](https://github.com/axpaul/Avionic-Marsaut1/blob/main/Cc-by-nc-sa_icon.svg.png)
