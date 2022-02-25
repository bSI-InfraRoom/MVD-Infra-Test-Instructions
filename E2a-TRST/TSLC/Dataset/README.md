## Variations
The following occurrence variations need to be checked and certified in relation to the targeted entities and concept templates:

- Entity_01 - *decription of variation*
- Entity_02 - *decription of variation*





## Model Dataset
This test case utilises the attached dataset documented by the following drawings and data schedule. 

*This is a later step that involved the detailed documentation of the certification dataset (model)*

### Alignment:

| Name | Type                   | ObjectPlacement   | Representation                                               |
| ---- | ---------------------- | ----------------- | ------------------------------------------------------------ |
| A1   | IfcAlignment           | IfcLocalPlacement | IfcGradientCurve<br />RepresentationIdentifier="Axis"<br />RepresentationType="Curve3D" |
| AH1  | IfcAlignmentHorizontal | IfcLocalPlacement | IfcCompositeCurve<br />RepresentationIdentifier="Axis"<br />RepresentationType="Curve2D" |
| AV1  | IfcAlignmentVertical   | IfcLocalPlacement | IfcGradientCurve<br />RepresentationIdentifier="Axis"<br />RepresentationType="Curve3D" |

#### Horizontal segments nested into AH1 in the following order:

| Name | Type                          | StartPointX | StartPointY | StartDirection | StartRadius | EndRadius | Length     | Type_1      |
| ---- | ----------------------------- | ----------- | ----------- | -------------- | ----------- | --------- | ---------- | ----------- |
| H1   | IfcAlignmentHorizontalSegment | 276,867419  | 935,549267  | 0,001724622    | 0           | 0         | 229,405681 | LINE        |
| H2   | IfcAlignmentHorizontalSegment | 506,272759  | 935,944905  | 0,00172463     | -110        | -110      | 15,594208  | CIRCULARARC |
| H3   | IfcAlignmentHorizontalSegment | 521,816666  | 934,8682    | 6,143144395    | 0           | 0         | 91,725737  | LINE        |
| H4   | IfcAlignmentHorizontalSegment | 612,644434  | 922,064789  | 6,143144399    | -110        | -110      | 120,80482  | CIRCULARARC |
| H5   | IfcAlignmentHorizontalSegment | 701,264387  | 849,049537  | 5,044918731    | 0           | 0         | 25,538554  | LINE        |
| H6   | IfcAlignmentHorizontalSegment | 709,601071  | 824,909996  | 5,044918761    | 110         | 110       | 49,633636  | CIRCULARARC |
| H7   | IfcAlignmentHorizontalSegment | 735,66497   | 783,164849  | 5,49613363     | 0           | 0         | 83,739856  | LINE        |

#### Vertical segments nested into AV1 in the following order:

| Name | Type                        | StartDistAlong | HorizontalLength | StartHeight | StartGradient | EndGradient  | Radius | Type_1           |
| ---- | --------------------------- | -------------- | ---------------- | ----------- | ------------- | ------------ | ------ | ---------------- |
| V1   | IfcAlignmentVerticalSegment | 135,557        | 10,84246946      | 125,687614  | 0,03416131    | 0,03416131   | 0      | CONSTANTGRADIENT |
| V2   | IfcAlignmentVerticalSegment | 146,3994695    | 18,11228261      | 126,058007  | 0,03416131    | 0,03416131   | -1300  | CIRCULARARC      |
| V3   | IfcAlignmentVerticalSegment | 164,5117521    | 40,83305808      | 126,5504044 | 0,020212997   | 0,020212997  | 0      | CONSTANTGRADIENT |
| V4   | IfcAlignmentVerticalSegment | 205,3448102    | 39,03368133      | 127,3757629 | 0,020212997   | 0,020212997  | -1300  | CIRCULARARC      |
| V5   | IfcAlignmentVerticalSegment | 244,3784915    | 50,17607352      | 127,5786042 | -0,009817512  | -0,009817512 | 0      | CONSTANTGRADIENT |
| V6   | IfcAlignmentVerticalSegment | 294,554565     | 11,522986        | 127,086     | 0             | 0            | 0      | CONSTANTGRADIENT |
| V7   | IfcAlignmentVerticalSegment | 306,077551     | 192,5126892      | 127,086     | -0,003529811  | -0,003529811 | 0      | CONSTANTGRADIENT |
| V8   | IfcAlignmentVerticalSegment | 498,5902402    | 15,27528964      | 126,4064666 | -0,003529811  | -0,003529811 | -5000  | CIRCULARARC      |
| V9   | IfcAlignmentVerticalSegment | 513,8655298    | 78,35926585      | 126,3292136 | -0,006584989  | -0,006584989 | 0      | CONSTANTGRADIENT |
| V10  | IfcAlignmentVerticalSegment | 592,2247957    | 10,41034226      | 125,8132186 | -0,006584989  | -0,006584989 | 1300   | CIRCULARARC      |
| V11  | IfcAlignmentVerticalSegment | 602,6351379    | 13,80735508      | 125,7863506 | 0,00142311    | 0,00142311   | 0      | CONSTANTGRADIENT |


## Drawings (Visualisations)
The following Drawings and visualisations describe the test case dataset to be modelled and certified.


## Supporting files

| Filename                          | Description                               |
|-----------------------------------|-------------------------------------------|
| *filename*                        | *short description*                       |
