## Variations
The Following occurrence variations need to be checked and certified in relation to the targeted entities and concept templates:

- Pset_Superelevation.Side - *The test shall include all possible values (LEFT, RIGHT and BOTH)*
- Pset_Superelevation.Superelevation - *The test shall include both positive and negative values*
- Pset_Superelevation.TransitionSuperelevation - *The test shall include only LINEAR transitions*
- Pset_Width.Side - *The test shall include all possible values (LEFT, RIGHT and BOTH)*
- Pset_Superelevation.TransitionWidth - *The test shall include LINEAR and CONST transitions*

## Model Dataset

- This test case utilises the following dataset:
  - Superelevation events according to the table below
  - Width events according to the table below

The following tables lists the entities that shall be present in the dataset in addition to the imported entities for model setup :

´Superelevation events:

| Name | Type                              | DistanceAlong | Superelevation | Side  | TransitionSuperelevation |
| ---- | --------------------------------- | ------------- | -------------- | ----- | ------------------------ |
| SE1  | IfcAnnotation/SUPERELEVATIONEVENT | 301,82        | 0,00           | BOTH  |                          |
| SE2  | IfcAnnotation/SUPERELEVATIONEVENT | 331,82        | 0,03           | LEFT  | LINEAR                   |
| SE3  | IfcAnnotation/SUPERELEVATIONEVENT | 331,82        | -0,03          | RIGHT | LINEAR                   |
| SE4  | IfcAnnotation/SUPERELEVATIONEVENT | 443,00        | 0,03           | LEFT  |                          |
| SE5  | IfcAnnotation/SUPERELEVATIONEVENT | 443,00        | -0,03          | RIGHT |                          |
| SE6  | IfcAnnotation/SUPERELEVATIONEVENT | 503,00        | -0,03          | LEFT  | LINEAR                   |
| SE7  | IfcAnnotation/SUPERELEVATIONEVENT | 503,00        | 0,03           | RIGHT | LINEAR                   |
| SE8  | IfcAnnotation/SUPERELEVATIONEVENT | 513,00        | -0,03          | LEFT  |                          |
| SE9  | IfcAnnotation/SUPERELEVATIONEVENT | 513,00        | 0,03           | RIGHT |                          |
| SE10 | IfcAnnotation/SUPERELEVATIONEVENT | 573,00        | -0,03          | LEFT  |                          |
| SE11 | IfcAnnotation/SUPERELEVATIONEVENT | 573,00        | -0,03          | RIGHT | LINEAR                   |

´Width events:

| Name | Type                     | DistanceAlong | NominalWidth | Side  | TransitionWidth |
| ---- | ------------------------ | ------------- | ------------ | ----- | --------------- |
| WE1  | IfcAnnotation/WIDTHEVENT | 301,82        | 3,4          | BOTH  |                 |
| WE2  | IfcAnnotation/WIDTHEVENT | 336,73        | 3,7          | LEFT  | LINEAR          |
| WE3  | IfcAnnotation/WIDTHEVENT | 336,73        | 3,6          | RIGHT | LINEAR          |
| WE4  | IfcAnnotation/WIDTHEVENT | 503,00        | 3,7          | LEFT  |                 |
| WE5  | IfcAnnotation/WIDTHEVENT | 503,00        | 3,6          | RIGHT |                 |
| WE6  | IfcAnnotation/WIDTHEVENT | 532,70        | 3,05         | BOTH  | CONST           |
| WE7  | IfcAnnotation/WIDTHEVENT | 583,00        | 2,75         | BOTH  | LINEAR          |

## Drawings (Visualisations)

The following Drawings and visualisations describe the test case dataset to be modelled and certified.

| Filename                 | Description                                                  |
| ------------------------ | ------------------------------------------------------------ |
| Superelevation and Width | ![image-20220221114609144](C:\Users\lars\Documents\Projekt\IFCInfra\MVD-Infra-Test-Instructions\E1a-ARSE\ALSE02\Dataset\Superelevation and Width.png) |


## Supporting files

| Filename | Description |
| -------- | ----------- |
|          |             |