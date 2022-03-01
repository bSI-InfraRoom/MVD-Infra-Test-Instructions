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

| Name | Type                   | ObjectPlacement   | Representation                                               |
| ---- | ---------------------- | ----------------- | ------------------------------------------------------------ |
| A1   | IfcAlignment           | IfcLocalPlacement | IfcGradientCurve<br />RepresentationIdentifier="Axis"<br />RepresentationType="Curve3D" |
| AH1  | IfcAlignmentHorizontal | IfcLocalPlacement | IfcCompositeCurve<br />RepresentationIdentifier="Axis"<br />RepresentationType="Curve2D" |
| AV1  | IfcAlignmentVertical   | IfcLocalPlacement | IfcGradientCurve<br />RepresentationIdentifier="Axis"<br />RepresentationType="Curve3D" |

Horizontal segments nested into AH1 in the following order:

| Name | Type                          | StartPointX | StartPointY | StartDirection | StartRadius | EndRadius | Length     | Type_1      |
| ---- | ----------------------------- | ----------- | ----------- | -------------- | ----------- | --------- | ---------- | ----------- |
| H1   | IfcAlignmentHorizontalSegment | 0,283714    | 18,750471   | 0,712199896    | 0           | 0         | 193,4232   | LINE        |
| H2   | IfcAlignmentHorizontalSegment | 146,690778  | 145,152631  | 0,712199906    | 0           | 200       | 63,845     | CLOTHOID    |
| H3   | IfcAlignmentHorizontalSegment | 192,677965  | 189,335669  | 0,871812399    | 200         | 200       | 34,420584  | CIRCULARARC |
| H4   | IfcAlignmentHorizontalSegment | 212,454617  | 217,455754  | 1,043915278    | 200         | 0         | 63,845     | CLOTHOID    |
| H5   | IfcAlignmentHorizontalSegment | 238,485471  | 275,673937  | 1,203527843    | 0           | 0         | 21,346852  | LINE        |
| H6   | IfcAlignmentHorizontalSegment | 246,15043   | 295,597202  | 1,20352782     | 0           | -200      | 63,845     | CLOTHOID    |
| H7   | IfcAlignmentHorizontalSegment | 272,181284  | 353,815386  | 1,04391532     | -200        | -200      | 85,355704  | CIRCULARARC |
| H8   | IfcAlignmentHorizontalSegment | 329,316712  | 416,355174  | 0,617136819    | -200        | 0         | 63,845     | CLOTHOID    |
| H9   | IfcAlignmentHorizontalSegment | 384,951684  | 447,527472  | 0,457524298    | 0           | 0         | 192,323738 | LINE        |
| H10  | IfcAlignmentHorizontalSegment | 557,494701  | 532,482327  | 0,457524293    | 200         | 200       | 82,814142  | CIRCULARARC |
| H11  | IfcAlignmentHorizontalSegment | 622,220317  | 583,190771  | 0,871595018    | -200        | -200      | 100,11889  | CIRCULARARC |
| H12  | IfcAlignmentHorizontalSegment | 702,781991  | 640,862461  | 0,371000558    | 0           | 0         | 58,659577  | LINE        |
| H13  | IfcAlignmentHorizontalSegment | 757,450667  | 662,129379  | 0,371000555    | -200        | -200      | 115,440984 | CIRCULARARC |
| H14  | IfcAlignmentHorizontalSegment | 870,909519  | 671,499388  | 6,076980939    | 200         | 200       | 102,335082 | CIRCULARARC |
| H15  | IfcAlignmentHorizontalSegment | 972,00724   | 676,521331  | 0,305471033    | 0           | 0         | 28,790227  | LINE        |

Vertical segments nested into AV1 in the following order:

| Name | Type                        | StartDistAlong | HorizontalLength | StartHeight | StartGradient | EndGradient  | Radius | Type_1           |
| ---- | --------------------------- | -------------- | ---------------- | ----------- | ------------- | ------------ | ------ | ---------------- |
| V1   | IfcAlignmentVerticalSegment | 0              | 67,96662759      | 43,475329   | -0,007734105  | -0,007734105 | 0      | CONSTANTGRADIENT |
| V2   | IfcAlignmentVerticalSegment | 67,96662759    | 25,56006049      | 42,94966796 | -0,007734105  | -0,093338018 | -300   | CIRCULARARC      |
| V3   | IfcAlignmentVerticalSegment | 93,52668809    | 20,39853177      | 41,66031927 | -0,093338018  | -0,093338018 | 0      | CONSTANTGRADIENT |
| V4   | IfcAlignmentVerticalSegment | 113,9252199    | 21,6842049       | 39,75636075 | -0,093338018  | -0,020657799 | 300    | CIRCULARARC      |
| V5   | IfcAlignmentVerticalSegment | 135,6094248    | 68,62574308      | 38,52203122 | -0,020657799  | -0,020657799 | 0      | CONSTANTGRADIENT |
| V6   | IfcAlignmentVerticalSegment | 204,2351678    | 56,93193013      | 37,10437443 | -0,020657799  | 0,007812811  | 2000   | CIRCULARARC      |
| V7   | IfcAlignmentVerticalSegment | 261,167098     | 46,44967561      | 36,73880354 | 0,007812811   | 0,007812811  | 0      | CONSTANTGRADIENT |
| V8   | IfcAlignmentVerticalSegment | 307,6167736    | 101,9005629      | 37,10170608 | 0,007812811   | 0,048630199  | 2500   | CIRCULARARC      |
| V9   | IfcAlignmentVerticalSegment | 409,5173365    | 30,59165499      | 39,97629696 | 0,048630199   | 0,048630199  | 0      | CONSTANTGRADIENT |
| V10  | IfcAlignmentVerticalSegment | 440,1089914    | 64,02882141      | 41,46397522 | 0,048630199   | -0,01545787  | -1000  | CIRCULARARC      |
| V11  | IfcAlignmentVerticalSegment | 504,1378129    | 203,5716837      | 42,52487872 | -0,01545787   | -0,01545787  | 0      | CONSTANTGRADIENT |
| V12  | IfcAlignmentVerticalSegment | 707,7094965    | 55,84829226      | 39,3780941  | -0,01545787   | -0,071486276 | -1000  | CIRCULARARC      |
| V13  | IfcAlignmentVerticalSegment | 763,5577815    | 76,62507339      | 36,95215385 | -0,071486276  | 0,005320833  | 1000   | CIRCULARARC      |
| V14  | IfcAlignmentVerticalSegment | 840,1828549    | 152,3446543      | 34,42091694 | 0,005320833   | 0,005320833  | 0      | CONSTANTGRADIENT |
| V15  | IfcAlignmentVerticalSegment | 992,5275091    | 36,817362        | 35,23151739 | 0,005320833   | 0,023736122  | 2000   | CIRCULARARC      |
| V16  | IfcAlignmentVerticalSegment | 1029,344877    | 52,56256394      | 35,76637241 | 0,023736122   | -0,028845118 | -1000  | CIRCULARARC      |
| V17  | IfcAlignmentVerticalSegment | 1081,907441    | 188,5015408      | 35,6321942  | -0,028845118  | -0,028845118 | 0      | CONSTANTGRADIENT |

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