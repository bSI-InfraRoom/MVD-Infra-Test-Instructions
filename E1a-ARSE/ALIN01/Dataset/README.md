## Variations
The Following occurrence variations need to be checked and certified in relation to the targeted entities and concept templates:

- IfcAlignmentHorizontalSegment - *The test shall include linear, clothoid and circular arc segments*
- IfcAlignmentVerticalSegment - *The test shall include linear and circular arc segments*
- Alignment Decomposition:
  - The horizontal alignment shall be decomposed with element sequences containing clothoid transition curves including both clockwise and counter-clockwise turns
  - The horizontal alignment shall also be decomposed with element sequences lacking clothoid transition curves including both clockwise and counter-clockwise turns where a clockwise and counter-clockwise turn are joined together (forming an "S" curve)
  - The vertical alignment shall be decomposed with element sequences containing linear and circular arc segments including both clockwise and counter-clockwise turns
  - The vertical alignment shall also be decomposed with element sequences where circular arcs follows directly after each other (forming an "S" curve)

## Model Dataset
This test case utilises the following dataset:

- One alignment layout (no geometric representation is required)

- The alignment is composed of one horizontal alignment layout and one vertical alignment layout

- The horizontal layout has the following sequences of elements:

  - Line => Clothoid => Circular arc (cw) => Clothoid => Line => Clothoid => Circular arc (ccw) => Clothoid => Line

  - Line => Circular arc (cw) => Circular arc (ccw) => Line

  - Line => Circular arc (ccw) => Circular arc (cw) => Line

- The vertical layout has the following sequences of elements:

  - Line => Circular arc => Line

  - Line => Circular arc (cw) => Circular arc (ccw) => Line

  - Line => Circular arc (ccw) => Circular arc (cw) => Line


## Drawings (Visualisations)
The following Drawings and visualisations describe the test case dataset to be modelled and certified.

| Filename                                     | Description                                  |
| -------------------------------------------- | -------------------------------------------- |
| [Testi_ml_map](./Testi_ml_map.pdf)           | Planar (map) view of the test case           |
| [Testi_ml_profiles](./Testi_ml_profiles.pdf) | Long section (profile) view of the test case |


## Supporting files

| Filename                                                     | Description                                              |
| ------------------------------------------------------------ | -------------------------------------------------------- |
| [HorizontalAlignmentParameters](./HorizontalAlignmentParameters.csv) | Parameters for the horizontal segments as csv            |
| [VerticalAlignmentParameters](./VerticalAlignmentParameters.csv) | Parameters for the vertical segments as csv              |
| [AlignmentParameters](./AlignmentParameters.xlsx)            | Parameters for horizontal and vertical segments as excel |