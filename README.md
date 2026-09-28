````markdown
# Image Classification from Scratch — XNDL

Projecte desenvolupat per a l'assignatura **Xarxes Neuronals i Deep Learning (XNDL)** del Grau en Intel·ligència Artificial de la UPC.

L'objectiu és dissenyar i entrenar **des de zero una xarxa neuronal convolucional (CNN)** capaç de classificar imatges en escala de grisos de `32x32` píxels en 14 categories diferents, sense utilitzar pesos preentrenats.

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

Totes les imatges tenen una resolució de `32x32` píxels i estan en escala de grisos.

L'estructura del dataset és:

```text
data/
├── train/
├── val/
└── test/
```

El conjunt de `test` segueix la mateixa distribució que el conjunt de validació, però es manté ocult durant el desenvolupament.

## Enfocament

El model inicial proporcionat era una xarxa *fully connected*, que tracta els píxels de manera independent i no aprofita l'estructura espacial de les imatges.

Per aquest motiu, es va substituir per una **arquitectura convolucional**, més adequada per a problemes de visió per computador, ja que permet detectar patrons locals com vores, textures i formes i combinar-los progressivament en representacions més complexes.

Durant el desenvolupament es van explorar diferents decisions de disseny per millorar la capacitat de generalització del model:

- Arquitectura basada en **capes convolucionals**
- Augment progressiu del nombre de canals
- **Batch Normalization**
- Funcions d'activació **ReLU**
- Reducció espacial mitjançant *pooling*
- **Dropout** per reduir l'overfitting
- **Data augmentation** durant l'entrenament
- Selecció del millor model segons el rendiment sobre el conjunt de validació

Tot el model s'entrena **des de zero**, sense utilitzar xarxes ni pesos preentrenats.

## Entrenament

El projecte està implementat amb **PyTorch** i està preparat per utilitzar GPU quan està disponible.

Una de les restriccions principals era que l'entrenament complet s'havia de poder executar en aproximadament **5 minuts sobre una GPU RTX 3080**, fet que obligava a buscar un equilibri entre:

- complexitat de l'arquitectura,
- capacitat de representació,
- velocitat d'entrenament,
- i rendiment final.

La mètrica utilitzada per avaluar el model és el **micro F1-score**, equivalent a l'accuracy en aquest problema de classificació multiclasse amb una única etiqueta per imatge.

## Tecnologies

- Python
- PyTorch
- Torchvision
- NumPy
- CUDA

## Estructura del projecte

```text
.
├── model_xndl.py
├── data/
│   ├── train/
│   ├── val/
│   └── test/
└── README.md
```

El fitxer principal conté el pipeline complet:

1. Càrrega i preprocessament de les dades
2. Data augmentation
3. Definició de la CNN
4. Entrenament
5. Validació
6. Selecció del millor model
7. Avaluació final

## Resultats

El model millora significativament el baseline inicial basat en una xarxa *fully connected* i aconsegueix una classificació robusta sobre les 14 categories.

**Validation accuracy / micro F1:** `XX.XX %`

Durant l'entrenament es conserva el millor estat del model segons el rendiment obtingut sobre el conjunt de validació.

## Principals aprenentatges

Aquest projecte va permetre treballar de manera pràctica conceptes fonamentals de Deep Learning aplicat a visió per computador:

- Disseny d'arquitectures CNN
- Efecte de la profunditat i del nombre de canals
- Regularització i overfitting
- Batch Normalization
- Data augmentation
- Selecció de models
- Compromís entre rendiment i cost computacional
````
