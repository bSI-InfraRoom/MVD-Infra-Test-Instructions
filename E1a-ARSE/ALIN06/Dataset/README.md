## Model Dataset

This test case utilizes the following dataset.

- One alignment layout including geometric representation
- The alignment is composed of one horizontal alignment layout and one vertical alignment layout
- The horizontal layout contains lines and circular arcs
- The vertical layout contains lines and circular arcs

The Following occurrence variations need to be checked and certified in relation to the targeted entities and concept templates:

- IfcAlignmentHorizontalSegment - *The test shall include linear and circular arc segments*
- IfcAlignmentVerticalSegment - *The test shall include linear and circular arc segments*
- Alignment Decomposition:
  - The horizontal alignment shall be decomposed with element sequences containing lines and both clockwise and counter-clockwise turns
  - The vertical alignment shall be decomposed with element sequences containing linear and circular arc segments including both clockwise and counter-clockwise turns

| Filename                                                     | Description                                   |
| ------------------------------------------------------------ | --------------------------------------------- |
| [HorizontalAlignmentParameters](./HorizontalAlignmentParameters.csv) | Parameters for the horizontal segments as csv |
| [VerticalAlignmentParameters](./VerticalAlignmentParameters.csv) | Parameters for the vertical segments as csv   |
| [LandXML](./TOI-M14334-0000A.xml)                            | LandXML-file representing the alignment       |

## Dataset specification

### Entities table

| **Element**            | **Attribute** | **Value**   | **Notes** |
| ---------------------- | ------------- | ----------- | --------- |
| IfcProject             | Name          | Alin06      |           |
| IfcSite                | Name          | Alin06.Site |           |
| IfcAlignment           | Name          | A1          |           |
| IfcRoad                | Name          | Alin06.Road |           |
| IfcAlignmentHorizontal | Name          | AH1         |           |
| IfcAlignmentVertical   | Name          | AV1         |           |

### Horizontal segments table

Horizontal segments nested into AH1 in the following order:

| Entity                        | PredefinedType | Name | Start Point X | Start Point Y | Start Direction | Start Radius Of Curvature | End Radius Of Curvature | Segment Length |
| ----------------------------- | -------------- | ---- | ------------- | ------------- | --------------- | ------------------------- | ----------------------- | -------------- |
| IfcAlignmentHorizontalSegment | LINE           | H1   | 276,867419    | 935,549267    | 0,001724622     | 0                         | 0                       | 229,405681     |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H2   | 506,272759    | 935,944905    | 0,00172463      | -110                      | -110                    | 15,594208      |
| IfcAlignmentHorizontalSegment | LINE           | H3   | 521,816666    | 934,8682      | 6,143144395     | 0                         | 0                       | 91,725737      |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H4   | 612,644434    | 922,064789    | 6,143144399     | -110                      | -110                    | 120,80482      |
| IfcAlignmentHorizontalSegment | LINE           | H5   | 701,264387    | 849,049537    | 5,044918731     | 0                         | 0                       | 25,538554      |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H6   | 709,601071    | 824,909996    | 5,044918761     | 110                       | 110                     | 49,633636      |
| IfcAlignmentHorizontalSegment | LINE           | H7   | 735,66497     | 783,164849    | 5,49613363      | 0                         | 0                       | 83,739856      |

**NOTE**:

- Please note the Project Global Positioning and unit parameters specified in the main Readme file

### Vertical segments table

Vertical segments nested into AV1 in the following order:

| Entity                      | PredefinedType   | Name | Type                        | StartDistAlong | HorizontalLength | StartHeight | StartGradient | EndGradient  | Radius | Type_1           |
| --------------------------- | ---------------- | ---- | --------------------------- | -------------- | ---------------- | ----------- | ------------- | ------------ | ------ | ---------------- |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V1   | IfcAlignmentVerticalSegment | 135,557        | 10,84246946      | 125,687614  | 0,03416131    | 0,03416131   | 0      | CONSTANTGRADIENT |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V2   | IfcAlignmentVerticalSegment | 146,3994695    | 18,11228261      | 126,058007  | 0,03416131    | 0,020212997  | -1300  | CIRCULARARC      |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V3   | IfcAlignmentVerticalSegment | 164,5117521    | 40,83305808      | 126,5504044 | 0,020212997   | 0,020212997  | 0      | CONSTANTGRADIENT |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V4   | IfcAlignmentVerticalSegment | 205,3448102    | 39,03368133      | 127,3757629 | 0,020212997   | -0,009817512 | -1300  | CIRCULARARC      |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V5   | IfcAlignmentVerticalSegment | 244,3784915    | 50,17607352      | 127,5786042 | -0,009817512  | -0,009817512 | 0      | CONSTANTGRADIENT |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V6   | IfcAlignmentVerticalSegment | 294,554565     | 11,522986        | 127,086     | 0             | 0            | 0      | CONSTANTGRADIENT |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V7   | IfcAlignmentVerticalSegment | 306,077551     | 192,5126892      | 127,086     | -0,003529811  | -0,003529811 | 0      | CONSTANTGRADIENT |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V8   | IfcAlignmentVerticalSegment | 498,5902402    | 15,27528964      | 126,4064666 | -0,003529811  | -0,006584989 | -5000  | CIRCULARARC      |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V9   | IfcAlignmentVerticalSegment | 513,8655298    | 78,35926585      | 126,3292136 | -0,006584989  | -0,006584989 | 0      | CONSTANTGRADIENT |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V10  | IfcAlignmentVerticalSegment | 592,2247957    | 10,41034226      | 125,8132186 | -0,006584989  | 0,00142311   | 1300   | CIRCULARARC      |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V11  | IfcAlignmentVerticalSegment | 602,6351379    | 13,80735508      | 125,7863506 | 0,00142311    | 0,00142311   | 0      | CONSTANTGRADIENT |

### Spatial (De)Composition table

| **Parent Element** | **Parent Element Type** | **Parent Element Name** | **MinSize** | **MaxSize** | **Child Element** | **Child Element Type** | **Child Element Name** |
| ------------------ | ----------------------- | ----------------------- | ----------- | ----------- | ----------------- | ---------------------- | ---------------------- |
| IfcProject         |                         | Alin06                  | 1           | 1           | IfcSite           |                        | Alin06.Site            |
| IfcSite            |                         | Alin06.Site             | 1           | 1           | IfcRoad           |                        | Allin06.Road           |

### Spatial Containment table

| **Spatial Element** | **Spatial Element Type** | **Spatial Element Name** | **MinSize** | **MaxSize** | **Element**  | **Element Type** | **Element Name** |
| ------------------- | ------------------------ | ------------------------ | ----------- | ----------- | ------------ | ---------------- | ---------------- |
| IfcSite             |                          | Alin06.Site              | 1           | 1           | IfcAlignment |                  | A1               |

### Product Geometric Representation table

| **Product**            | **Product Type** | **Product Name** | **Representation Identifier** | **Representation Type** | **Items**           |
| ---------------------- | ---------------- | ---------------- | ----------------------------- | ----------------------- | ------------------- |
| IfcAlignment           | na               | A1               | Axis                          | Curve3D                 | 1 IfcGradientCurve  |
| IfcAlignmentHorizontal | na               | AH1              | Axis                          | Curve2D                 | 1 IfcCompositeCurve |
| IfcAlignmentVertical   | na               | AV1              | Axis                          | Curve2D                 | 1 IfcGradientCurve  |

### Product Placement table

| **Product**  | **Product Type** | **Product Name** | **Object Placement** | Relative Placement Product | Relative Placement Product Type | Relative Placement Product Name |
| ------------ | ---------------- | ---------------- | -------------------- | -------------------------- | ------------------------------- | ------------------------------- |
| IfcAlignment |                  | A1               | IfcLocalPlacement    | IfcSite                    | na                              | Alin06.Site                     |

## 