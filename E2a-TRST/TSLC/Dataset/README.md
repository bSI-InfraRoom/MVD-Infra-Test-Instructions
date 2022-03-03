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

| Name | Type                          | StartPointX | StartPointY | StartDirection | StartRadius | EndRadius | Length      | Type_1      |
| ---- | ----------------------------- | ----------- | ----------- | -------------- | ----------- | --------- | ----------- | ----------- |
| H1   | IfcAlignmentHorizontalSegment | 1304,078529 | 2487,611348 | 4,207620618    | 0           | 0         | 1091,152467 | LINE        |
| H2   | IfcAlignmentHorizontalSegment | 776,392063  | 1532,540304 | 4,207620618    | 0           | 1518      | 80          | CLOTHOID    |
| H3   | IfcAlignmentHorizontalSegment | 738,321388  | 1462,182442 | 4,233696595    | 1518        | 1518      | 513,309402  | CIRCULARARC |
| H4   | IfcAlignmentHorizontalSegment | 582,796258  | 975,564171  | 4,572119564    | 1518        | 0         | 80          | CLOTHOID    |
| H5   | IfcAlignmentHorizontalSegment | 573,004982  | 896,168101  | 4,598470026    | 0           | 0         | 154,948149  | LINE        |
| H6   | IfcAlignmentHorizontalSegment | 555,391605  | 742,224288  | 4,598470026    | 0           | -1486     | 90          | CLOTHOID    |
| H7   | IfcAlignmentHorizontalSegment | 544,259467  | 652,919107  | 4,568327586    | -1486       | -1486     | 235,958273  | CIRCULARARC |
| H8   | IfcAlignmentHorizontalSegment | 491,993759  | 423,076296  | 4,409399855    | -1486       | 0         | 90          | CLOTHOID    |
| H9   | IfcAlignmentHorizontalSegment | 463,412608  | 337,73898   | 4,379117218    | 0           | 0         | 316,307118  | LINE        |

#### Vertical segments nested into AV1 in the following order:

| Name | Type                        | StartDistAlong | HorizontalLength | StartHeight | StartGradient | EndGradient  | Radius | Type_1           |
| ---- | --------------------------- | -------------- | ---------------- | ----------- | ------------- | ------------ | ------ | ---------------- |
| V1   | IfcAlignmentVerticalSegment | 0,000407982    | 246,4273892      | 108,082846  | 0,012500014   | 0,012500014  | 0      | CONSTANTGRADIENT |
| V2   | IfcAlignmentVerticalSegment | 246,4277972    | 95,01277799      | 111,1631917 | 0,012500014   | 0,002997773  | -10000 | CIRCULARARC      |
| V3   | IfcAlignmentVerticalSegment | 341,4405752    | 85,15793083      | 111,899419  | 0,002997773   | 0,002997773  | 0      | CONSTANTGRADIENT |
| V4   | IfcAlignmentVerticalSegment | 426,598506     | 183,6600283      | 112,1547031 | 0,002997773   | 0,013202245  | 18000  | CIRCULARARC      |
| V5   | IfcAlignmentVerticalSegment | 610,2585343    | 701,6062339      | 113,6423122 | 0,013202245   | 0,013202245  | 0      | CONSTANTGRADIENT |
| V6   | IfcAlignmentVerticalSegment | 1311,864768    | 34,07192867      | 122,9050894 | 0,013202245   | 0,011498258  | -20000 | CIRCULARARC      |
| V7   | IfcAlignmentVerticalSegment | 1345,936697    | 236,655805       | 123,325886  | 0,011498258   | 0,011498258  | 0      | CONSTANTGRADIENT |
| V8   | IfcAlignmentVerticalSegment | 1582,592502    | 353,6059896      | 126,0470154 | 0,011498258   | -0,015704899 | -13000 | CIRCULARARC      |
| V9   | IfcAlignmentVerticalSegment | 1936,198491    | 119,9639637      | 125,3034062 | -0,015704899  | -0,015704899 | 0      | CONSTANTGRADIENT |
| V10  | IfcAlignmentVerticalSegment | 2056,162455    | 282,6533323      | 123,4193842 | -0,015704899  | -4,51E-15    | 18000  | CIRCULARARC      |
| V11  | IfcAlignmentVerticalSegment | 2338,815787    | 312,8596206      | 121,2       | 2,38704E-12   | 2,38704E-12  | 0      | CONSTANTGRADIENT |


## Drawings (Visualisations)
The following Drawings and visualisations describe the test case dataset to be modelled and certified.


## Supporting files

| Filename                          | Description                               |
|-----------------------------------|-------------------------------------------|
| *filename*                        | *short description*                       |
