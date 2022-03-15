## Variations
The Following occurrence variations need to be checked and certified in relation to the targeted entities and concept templates:

- IfcAlignmentHorizontalSegment - *The test shall include linear, clothoid and circular arc segments*
- IfcAlignmentVerticalSegment - *The test shall include linear and parabolic arc segments*
- Alignment Decomposition:
  - The horizontal alignment shall be decomposed with element sequences containing clothoid transition curves including both clockwise and counter-clockwise turns
  - The horizontal alignment shall also be decomposed with sequences of clothoid transition curves forming "S" curves
  - The vertical alignment shall be decomposed with element sequences containing linear and parabolic arc segments including both clockwise and counter-clockwise turns
  - The vertical alignment shall also be decomposed into parabolic arcs followed by parabolic arcs forming "S" curves
  - The vertical alignment shall also be decomposed with element sequences where linear elements follows directly after each other

## Model Dataset
This test case utilises the following dataset:

- One alignment layout (no geometric representation is required)
- The alignment is composed of one horizontal alignment layout and one vertical alignment layout
- The horizontal layout has the following sequences of elements:

  - Line => Clothoid => Circular arc (cw) => Clothoid => Clothoid  => Circular arc (ccw) => Clothoid => Clothoid => Circular arc (cw)
- The vertical layout has the following sequences of elements:

  - Line => Parabolic arc => Line
  - Line => Parabolic arc => Parabolic arc => Line
  - Line => Line => Line => ...

The following tables lists the entities that shall be present in the dataset in addition to the imported entities for model setup :

Alignment:

| Name | Type                   | ObjectPlacement | Representation |
| ---- | ---------------------- | --------------- | -------------- |
| A1   | IfcAlignment           | None            | None           |
| AH1  | IfcAlignmentHorizontal | None            | None           |
| AV1  | IfcAlignmentVertical   | None            | None           |

Horizontal segments nested into AH1 in the following order:

| Name | Type                          | StartPointX | StartPointY | StartDirection | StartRadius | EndRadius   | Length     | Type_1      |
| ---- | ----------------------------- | ----------- | ----------- | -------------- | ----------- | ----------- | ---------- | ----------- |
| H1   | IfcAlignmentHorizontalSegment | 145685,8552 | 6591370,142 | 3,817860174    | 0           | 0           | 47,36403   | LINE        |
| H2   | IfcAlignmentHorizontalSegment | 145648,9153 | 6591340,498 | 3,817860159    | 0           | 185         | 84,45946   | CLOTHOID    |
| H3   | IfcAlignmentHorizontalSegment | 145587,3939 | 6591282,917 | 4,046128984    | 185         | 185         | 137,211623 | CIRCULARARC |
| H4   | IfcAlignmentHorizontalSegment | 145548,3555 | 6591154,638 | 4,78781345     | 185         | 0           | 59,594595  | CLOTHOID    |
| H5   | IfcAlignmentHorizontalSegment | 145559,1771 | 6591096,104 | 4,948879761    | 0           | -203,799988 | 55,65383   | CLOTHOID    |
| H6   | IfcAlignmentHorizontalSegment | 145569,7329 | 6591041,507 | 4,812339587    | -203,799988 | -203,799988 | 25,757113  | CIRCULARARC |
| H7   | IfcAlignmentHorizontalSegment | 145570,6789 | 6591015,784 | 4,68595602     | -203,799988 | 0           | 125,614636 | CLOTHOID    |
| H8   | IfcAlignmentHorizontalSegment | 145541,9224 | 6590894,05  | 4,377775936    | 0           | 851,999999  | 118,881381 | CLOTHOID    |
| H9   | IfcAlignmentHorizontalSegment | 145505,5107 | 6590780,909 | 4,447541815    | 851,999999  | 851,999999  | 2,84745    | CIRCULARARC |

Vertical segments nested into AV1 in the following order:

| Name | Type                        | StartDistAlong | HorizontalLength | StartHeight | StartGradient | EndGradient | Radius       | Type_1           |
| ---- | --------------------------- | -------------- | ---------------- | ----------- | ------------- | ----------- | ------------ | ---------------- |
| V1   | IfcAlignmentVerticalSegment | 85             | 1,41860495       | 15,82       | 0,009739982   | 0,009739982 | 0            | CONSTANTGRADIENT |
| V2   | IfcAlignmentVerticalSegment | 86,41860495    | 20,6264881       | 15,83381719 | 0,009739982   | 0,023047408 | 1549,998375  | PARABOLICARC     |
| V3   | IfcAlignmentVerticalSegment | 107,0450938    | 30,9389625       | 16,17196156 | 0,023047408   | 0,016859621 | -5000,004241 | PARABOLICARC     |
| V4   | IfcAlignmentVerticalSegment | 137,9840563    | 66,893377        | 16,78930258 | 0,016859621   | 0,016859621 | 0            | CONSTANTGRADIENT |
| V5   | IfcAlignmentVerticalSegment | 204,8774333    | 12,6667695       | 17,91709954 | 0,016859621   | 0,012637385 | -3000,015228 | PARABOLICARC     |
| V6   | IfcAlignmentVerticalSegment | 217,5442028    | 4,4678966        | 18,10391542 | 0,012637385   | 0,012637385 | 0            | CONSTANTGRADIENT |
| V7   | IfcAlignmentVerticalSegment | 222,0120994    | 13,9676113       | 18,16037796 | 0,012637385   | 0,017293222 | 3000,021522  | PARABOLICARC     |
| V8   | IfcAlignmentVerticalSegment | 235,9797107    | 29,55312205      | 18,36940751 | 0,017293222   | 0,017293222 | 0            | CONSTANTGRADIENT |
| V9   | IfcAlignmentVerticalSegment | 265,5328327    | 17,4384826       | 18,88047622 | 0,017293222   | 0,023106068 | 2999,990831  | PARABOLICARC     |
| V10  | IfcAlignmentVerticalSegment | 282,9713153    | 12,9163156       | 19,23272738 | 0,023106068   | 0,023106068 | 0            | CONSTANTGRADIENT |
| V11  | IfcAlignmentVerticalSegment | 295,8876309    | 64,5895582       | 19,53117264 | 0,023106068   | 0,045000824 | 2950,001197  | PARABOLICARC     |
| V12  | IfcAlignmentVerticalSegment | 360,4771891    | 0,0557456        | 21,73066968 | 0,045000824   | 0,045000824 | 0            | CONSTANTGRADIENT |
| V13  | IfcAlignmentVerticalSegment | 360,5329347    | 42,5278306       | 21,73317828 | 0,045000824   | 0,030824882 | -3000,000288 | PARABOLICARC     |
| V14  | IfcAlignmentVerticalSegment | 403,0607653    | 126,9386947      | 23,34552968 | 0,030824882   | 0,030824882 | 0            | CONSTANTGRADIENT |
| V15  | IfcAlignmentVerticalSegment | 529,99946      | 10               | 27,2584     | 0,028668      | 0,028668    | 0            | CONSTANTGRADIENT |
| V16  | IfcAlignmentVerticalSegment | 539,99946      | 10               | 27,54508    | 0,027292      | 0,027292    | 0            | CONSTANTGRADIENT |
| V17  | IfcAlignmentVerticalSegment | 549,99946      | 10               | 27,818      | 0,026832      | 0,026832    | 0            | CONSTANTGRADIENT |
| V18  | IfcAlignmentVerticalSegment | 559,99946      | 10               | 28,08632    | 0,026325      | 0,026325    | 0            | CONSTANTGRADIENT |
| V19  | IfcAlignmentVerticalSegment | 569,99946      | 10               | 28,34957    | 0,02537       | 0,02537     | 0            | CONSTANTGRADIENT |
| V20  | IfcAlignmentVerticalSegment | 579,99946      | 10               | 28,60327    | 0,020813      | 0,020813    | 0            | CONSTANTGRADIENT |
| V21  | IfcAlignmentVerticalSegment | 589,99946      | 10               | 28,8114     | 0,020176      | 0,020176    | 0            | CONSTANTGRADIENT |
| V22  | IfcAlignmentVerticalSegment | 599,99946      | 10               | 29,01316    | 0,019498      | 0,019498    | 0            | CONSTANTGRADIENT |
| V23  | IfcAlignmentVerticalSegment | 609,99946      | 10               | 29,20814    | 0,018781      | 0,018781    | 0            | CONSTANTGRADIENT |
| V24  | IfcAlignmentVerticalSegment | 619,99946      | 10               | 29,39595    | 0,018022      | 0,018022    | 0            | CONSTANTGRADIENT |
| V25  | IfcAlignmentVerticalSegment | 629,99946      | 10               | 29,57617    | 0,017226      | 0,017226    | 0            | CONSTANTGRADIENT |
| V26  | IfcAlignmentVerticalSegment | 639,99946      | 10               | 29,74843    | 0,01639       | 0,01639     | 0            | CONSTANTGRADIENT |
| V27  | IfcAlignmentVerticalSegment | 649,99946      | 7,384658         | 29,91233    | 0,015674389   | 0,015674389 | 0            | CONSTANTGRADIENT |

## Drawings (Visualisations)

The following Drawings and visualisations describe the test case dataset to be modelled and certified.

| Filename                           | Description                                  |
| ---------------------------------- | -------------------------------------------- |
| [Horizontal](./Horizontal.PNG)     | Planar view of the horizontal alignment      |
| [Vertical](./T616AAC0_profile.pdf) | Long section (profile) view of the alignment |


## Supporting files

| Filename                                                     | Description                                   |
| ------------------------------------------------------------ | --------------------------------------------- |
| [HorizontalAlignmentParameters](./HorizontalAlignmentParameters.csv) | Parameters for the horizontal segments as csv |
| [VerticalAlignmentParameters](./VerticalAlignmentParameters.csv) | Parameters for the vertical segments as csv   |
| [LandXML](./T616AAC0.ifc)                                    | LandXML-file representing the alignment       |