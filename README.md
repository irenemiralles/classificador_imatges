# Image Classification from Scratch — XNDL

Projecte desenvolupat per a l'assignatura **Xarxes Neuronals i Deep Learning (XNDL)** del Grau en Intel·ligència Artificial de la UPC.

L'objectiu del projecte és dissenyar i entrenar **des de zero una xarxa neuronal convolucional (CNN)** capaç de classificar imatges en escala de grisos de `32x32` píxels en 14 categories diferents, sense utilitzar pesos preentrenats.

## Objectiu

El model classifica cada imatge en una de les categories següents:

- Apple
- Basketball
- Brain
- Circle
- Clock
- Compass
- Cookie
- Donut
- Face
- Moon
- Potato
- Sun
- Watermelon
- Wheel

El dataset està dividit en:

```text
data/
├── train/
├── val/
└── test/
