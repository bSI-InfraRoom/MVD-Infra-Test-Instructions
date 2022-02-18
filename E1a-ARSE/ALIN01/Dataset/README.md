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

The following tables lists the entities that shall be present in the dataset in addition to the imported entities for model setup :

Alignment:

| Name | Type                   | ObjectPlacement   | Representation |
| ---- | ---------------------- | ----------------- | -------------- |
| A1   | IfcAlignment           | IfcLocalPlacement | None           |
| AH1  | IfcAlignmentHorizontal | IfcLocalPlacement | None           |
| AV1  | IfcAlignmentVertical   | IfcLocalPlacement | None           |

Horizontal segments nested into AH1 in the following order:

| Name | Type                          | StartPointX  | StartPointY | StartDirection | StartRadius | EndRadius | Length  | Type          |
| ---- | ----------------------------- | ------------ | ----------- | -------------- | ----------- | --------- | ------- | ------------- |
| H1   | IfcAlignmentHorizontalSegment | 24474600.283 | 6654918.750 | 0.7121999      |             |           | 193.423 | .LINE.        |
| H2   | IfcAlignmentHorizontalSegment | 24474746.690 | 6655045.152 | 0.7121999      | 0.0         | 200.0     | 63.845  | .CLOTHOID.    |
| H3   | IfcAlignmentHorizontalSegment | 24474792.678 | 6655089.336 | 0.8718124      | 200.0       | 200.0     | 34.421  | .CIRCULARARC. |
| H4   | IfcAlignmentHorizontalSegment | 24474812.455 | 6655117.455 | 1.0439153      | 200.0       | 0.0       | 63.845  | .CLOTHOID.    |
| H5   | IfcAlignmentHorizontalSegment | 24474838.485 | 6655175.674 | 1.2035278      |             |           | 21.347  | .LINE.        |
| H6   | IfcAlignmentHorizontalSegment | 24474846.150 | 6655195.597 | 1.2035278      | 0.0         | -200.0    | 63.845  | .CLOTHOID.    |
| H7   | IfcAlignmentHorizontalSegment | 24474872.181 | 6655253.815 | 1.0439153      | -200.0      | -200.0    | 85.355  | .CIRCULARARC. |
| H8   | IfcAlignmentHorizontalSegment | 24474929.317 | 6655316.355 | 0.6171368      | -200.0      | 0.0       | 63.845  | .CLOTHOID.    |
| H9   | IfcAlignmentHorizontalSegment | 24474984.952 | 6655347.527 | 0.4575243      |             |           | 192.323 | .LINE.        |
| H10  | IfcAlignmentHorizontalSegment | 24475157.495 | 6655432.482 | 0.4575243      | 200.0       | 200.0     | 82.814  | .CIRCULARARC. |
| H11  | IfcAlignmentHorizontalSegment | 24475222.220 | 6655483.191 | 0.8715950      | -200.0      | -200.0    | 100.119 | .CIRCULARARC. |
| H12  | IfcAlignmentHorizontalSegment | 24475302.782 | 6655540.862 | 0.3710006      |             |           | 58.660  | .LINE.        |
| H13  | IfcAlignmentHorizontalSegment | 24475357.451 | 6655562.129 | 0.3710006      | -200.0      | -200.0    | 115.441 | .CIRCULARARC. |
| H14  | IfcAlignmentHorizontalSegment | 24475470.910 | 6655571.499 | 6.0769809      | 200.0       | 200.0     | 102.335 | .CIRCULARARC. |
| H15  | IfcAlignmentHorizontalSegment | 24475572.007 | 6655576.521 | 0.3054710      |             |           | 28.790  | .LINE.        |

Vertical segments nested into AV1 in the following order:

| Name | Type                        | StartDistAlong | HorizontalLength | StartHeight | StartGradient | EndGradient | Radius  | Type               |
| ---- | --------------------------- | -------------- | ---------------- | ----------- | ------------- | ----------- | ------- | ------------------ |
| V1   | IfcAlignmentVerticalSegment | 0.0            | 67.967           | 43.475      | -0.0077341    | -0.0077341  |         | .CONSTANTGRADIENT. |
| V2   | IfcAlignmentVerticalSegment | 67.967         | 25.560           | 42.950      | -0.0077341    | -0.0933380  | -300.0  | .CIRCULARARC.      |
| V3   | IfcAlignmentVerticalSegment | 93.527         | 20.399           | 41.660      | -0.0933380    | -0.0933380  |         | .CONSTANTGRADIENT. |
| V4   | IfcAlignmentVerticalSegment | 113.925        | 21.684           | 39.756      | -0.0933380    | -0.0206578  | 300.0   | .CIRCULARARC.      |
| V5   | IfcAlignmentVerticalSegment | 135.609        | 68.626           | 38.522      | -0.0206578    | -0.0206578  |         | .CONSTANTGRADIENT. |
| V6   | IfcAlignmentVerticalSegment | 204.235        | 56.932           | 37.104      | -0.0206578    | 0.0078128   | 2000.0  | .CIRCULARARC.      |
| V7   | IfcAlignmentVerticalSegment | 261.167        | 46.450           | 36.739      | 0.0078128     | 0.0078128   |         | .CONSTANTGRADIENT. |
| V8   | IfcAlignmentVerticalSegment | 307.617        | 101.901          | 37.102      | 0.0078128     | 0.0486302   | 2500.0  | .CIRCULARARC.      |
| V9   | IfcAlignmentVerticalSegment | 409.517        | 30.592           | 39.976      | 0.0486302     | 0.0486302   |         | .CONSTANTGRADIENT. |
| V10  | IfcAlignmentVerticalSegment | 440.109        | 64.029           | 41.464      | 0.0486302     | -0.0154579  | -1000.0 | .CIRCULARARC.      |
| V11  | IfcAlignmentVerticalSegment | 504.138        | 203.572          | 42.525      | -0.0154579    | -0.0154579  |         | .CONSTANTGRADIENT. |
| V12  | IfcAlignmentVerticalSegment | 707.709        | 55.848           | 39.378      | -0.0154579    | -0.0714863  | -1000.0 | .CIRCULARARC.      |
| V13  | IfcAlignmentVerticalSegment | 763.558        | 76.625           | 36.952      | -0.0714863    | 0.0053208   | 1000.0  | .CIRCULARARC.      |
| V14  | IfcAlignmentVerticalSegment | 840.183        | 152.345          | 34.421      | 0.0053208     | 0.0053208   |         | .CONSTANTGRADIENT. |
| V15  | IfcAlignmentVerticalSegment | 992.528        | 36.817           | 35.232      | 0.0053208     | 0.0237361   | 2000.0  | .CIRCULARARC.      |
| V16  | IfcAlignmentVerticalSegment | 1029.345       | 52.563           | 35.766      | 0.0237361     | -0.0288451  | -1000.0 | .CIRCULARARC.      |
| V17  | IfcAlignmentVerticalSegment | 1081.907       | 188.502          | 35.632      | -0.0288451    | -0.0288451  |         | .CONSTANTGRADIENT. |

## Drawings (Visualisations)

The following Drawings and visualisations describe the test case dataset to be modelled and certified.

| Filename                                     | Description                                  |
| -------------------------------------------- | -------------------------------------------- |
| [Testi_ml_map](./Testi_ml_map.pdf)           | Planar (map) view of the test case           |
| [Testi_ml_profiles](./Testi_ml_profiles.pdf) | Long section (profile) view of the test case |


## Supporting files

| Filename                                                     | Description                                   |
| ------------------------------------------------------------ | --------------------------------------------- |
| [HorizontalAlignmentParameters](./HorizontalAlignmentParameters.csv) | Parameters for the horizontal segments as csv |
| [VerticalAlignmentParameters](./VerticalAlignmentParameters.csv) | Parameters for the vertical segments as csv   |
| [LandXML](./Testi_101_ml.xml)                                | LandXML-file representing the alignment       |