## Requisitos

```bash
pip install pynrrd SimpleITK torch torchvision scikit-image scipy trimesh numpy matplotlib
```

## Descripción

Desarrollo de un sistema de segmentación multiclase de TAC de tórax mediante *deep learning* para la generación automática de torsos virtuales destinados a simulación electrofisiológica. Se segmentan 15 estructuras anatómicas utilizando arquitecturas U-Net 2.5D y ResUNet 2.5D, y se generan mallas 3D a partir de las predicciones mediante el algoritmo *Marching Cubes*.

## Dataset

60 volúmenes TAC de tórax de 4 fuentes públicas y privadas:

- **Hospital La Fe** (Pacientes 1-3 y 21-32)
- **VAREPOP-APOLLO** (Pacientes 4-20) — [enlace](https://doi.org/10.7937/ghkn-md15)
- **Wasserthal et al.** (Pacientes 33-48) — [enlace](https://doi.org/10.5281/zenodo.10047292)
- **NSCLC-Radiogenomics** (Pacientes 49-60) — [enlace](https://doi.org/10.7937/K9/TCIA.2017.7hs46erv)

Split: 40 entrenamiento / 20 test.

## Estructura del repositorio
```
├── PREPROCESADO/       # Remuestreo, normalización y exportación del dataset 2.5D
├── CLASE PIEL/         # Generación de la máscara de piel
├── redes/
│   ├── ResU-Net 2.5D con data augmentation/        # U-Net 2.5D sin data augmentation
│   ├── ResU-Net 2.5D sin data augmentation/        # U-Net 2.5D con data augmentation
│   ├── U-Net 2.5D con data augmentation/     # ResUNet 2.5D sin data augmentation
│   └── U-Net 2.5D sin data augmentation/     # ResUNet 2.5D con data augmentation
├── MALLADO/            # Generación de mallas 3D con Marching Cubes
└── DATASET_2p5D_bases_FINAL/   # Dataset preprocesado (disponible en Kaggle)
```
El dataset preprocesado está disponible en Kaggle: [DATASET_2p5D_bases_FINAL](https://www.kaggle.com/datasets/ignacioredondo/dataset-2p5d-bases-final)
