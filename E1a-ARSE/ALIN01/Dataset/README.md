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
  - Line => Circular arc (crest) => Circular arc (sag) => Line
  - Line => Circular arc (sag) => Circular arc (crest) => Line



| Filename                                                     | Description                                   |
| ------------------------------------------------------------ | --------------------------------------------- |
| [HorizontalAlignmentParameters](./HorizontalAlignmentParameters.csv) | Parameters for the horizontal segments as csv |
| [VerticalAlignmentParameters](./VerticalAlignmentParameters.csv) | Parameters for the vertical segments as csv   |
| [LandXML](./Testi_101_ml.xml)                                | LandXML-file representing the alignment       |

## Dataset specification

### Entities table

| **Element**            | **Attribute** | **Value**   | **Notes** |
| ---------------------- | ------------- | ----------- | --------- |
| IfcProject             | Name          | Alin01      |           |
| IfcSite                | Name          | Alin01.Site |           |
| IfcAlignment           | Name          | A1          |           |
| IfcRoad                | Name          | Alin01.Road |           |
| IfcAlignmentHorizontal | Name          | AH1         |           |
| IfcAlignmentVertical   | Name          | AV1         |           |

### Horizontal segments table

Horizontal segments nested into AH1 in the following order:

| Entity                        | PredefinedType | Name | Start Point X | Start Point Y | Start Direction | Start Radius Of Curvature | End Radius Of Curvature | Segment Length |
| ----------------------------- | -------------- | ---- | ------------- | ------------- | --------------- | ------------------------- | ----------------------- | -------------- |
| IfcAlignmentHorizontalSegment | LINE           | H1   | 0,283714      | 18,750471     | 0,712199896     | 0                         | 0                       | 193,4232       |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H2   | 146,690778    | 145,152631    | 0,712199906     | 0                         | 200                     | 63,845         |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H3   | 192,677965    | 189,335669    | 0,871812399     | 200                       | 200                     | 34,420584      |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H4   | 212,454617    | 217,455754    | 1,043915278     | 200                       | 0                       | 63,845         |
| IfcAlignmentHorizontalSegment | LINE           | H5   | 238,485471    | 275,673937    | 1,203527843     | 0                         | 0                       | 21,346852      |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H6   | 246,15043     | 295,597202    | 1,20352782      | 0                         | -200                    | 63,845         |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H7   | 272,181284    | 353,815386    | 1,04391532      | -200                      | -200                    | 85,355704      |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H8   | 329,316712    | 416,355174    | 0,617136819     | -200                      | 0                       | 63,845         |
| IfcAlignmentHorizontalSegment | LINE           | H9   | 384,951684    | 447,527472    | 0,457524298     | 0                         | 0                       | 192,323738     |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H10  | 557,494701    | 532,482327    | 0,457524293     | 200                       | 200                     | 82,814142      |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H11  | 622,220317    | 583,190771    | 0,871595018     | -200                      | -200                    | 100,11889      |
| IfcAlignmentHorizontalSegment | LINE           | H12  | 702,781991    | 640,862461    | 0,371000558     | 0                         | 0                       | 58,659577      |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H13  | 757,450667    | 662,129379    | 0,371000555     | -200                      | -200                    | 115,440984     |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H14  | 870,909519    | 671,499388    | 6,076980939     | 200                       | 200                     | 102,335082     |
| IfcAlignmentHorizontalSegment | LINE           | H15  | 972,00724     | 676,521331    | 0,305471033     | 0                         | 0                       | 28,790227      |

**NOTE**:

- Please note the Project Global Positioning and unit parameters specified in the main Readme file

### Vertical segments table

Vertical segments nested into AV1 in the following order:

| Entity                      | PredefinedType   | Name | Start Dist Along | Horizontal Length | Start Height | Start Gradient | End Gradient | RadiusOfCurvature |
| --------------------------- | ---------------- | ---- | ---------------- | ----------------- | ------------ | -------------- | ------------ | ----------------- |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V1   | 0                | 67,96662759       | 43,475329    | -0,007734105   | -0,007734105 | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V2   | 67,96662759      | 25,56006049       | 42,94966796  | -0,007734105   | -0,093338018 | -300              |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V3   | 93,52668809      | 20,39853177       | 41,66031927  | -0,093338018   | -0,093338018 | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V4   | 113,9252199      | 21,6842049        | 39,75636075  | -0,093338018   | -0,020657799 | 300               |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V5   | 135,6094248      | 68,62574308       | 38,52203122  | -0,020657799   | -0,020657799 | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V6   | 204,2351678      | 56,93193013       | 37,10437443  | -0,020657799   | 0,007812811  | 2000              |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V7   | 261,167098       | 46,44967561       | 36,73880354  | 0,007812811    | 0,007812811  | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V8   | 307,6167736      | 101,9005629       | 37,10170608  | 0,007812811    | 0,048630199  | 2500              |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V9   | 409,5173365      | 30,59165499       | 39,97629696  | 0,048630199    | 0,048630199  | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V10  | 440,1089914      | 64,02882141       | 41,46397522  | 0,048630199    | -0,01545787  | -1000             |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V11  | 504,1378129      | 203,5716837       | 42,52487872  | -0,01545787    | -0,01545787  | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V12  | 707,7094965      | 55,84829226       | 39,3780941   | -0,01545787    | -0,071486276 | -1000             |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V13  | 763,5577815      | 76,62507339       | 36,95215385  | -0,071486276   | 0,005320833  | 1000              |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V14  | 840,1828549      | 152,3446543       | 34,42091694  | 0,005320833    | 0,005320833  | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V15  | 992,5275091      | 36,817362         | 35,23151739  | 0,005320833    | 0,023736122  | 2000              |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V16  | 1029,344877      | 52,56256394       | 35,76637241  | 0,023736122    | -0,028845118 | -1000             |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V17  | 1081,907441      | 188,5015408       | 35,6321942   | -0,028845118   | -0,028845118 | 0                 |

### Spatial (De)Composition table

| **Parent Element** | **Parent Element Type** | **Parent Element Name** | **MinSize** | **MaxSize** | **Child Element** | **Child Element Type** | **Child Element Name** |
| ------------------ | ----------------------- | ----------------------- | ----------- | ----------- | ----------------- | ---------------------- | ---------------------- |
| IfcProject         |                         | Alin01                  | 1           | 1           | IfcSite           |                        | Alin01.Site            |
| IfcSite            |                         | Alin01.Site             | 1           | 1           | IfcRoad           |                        | Allin01.Road           |

### Spatial Containment table

| **Spatial Element** | **Spatial Element Type** | **Spatial Element Name** | **MinSize** | **MaxSize** | **Element**  | **Element Type** | **Element Name** |
| ------------------- | ------------------------ | ------------------------ | ----------- | ----------- | ------------ | ---------------- | ---------------- |
| IfcSite             |                          | Alin01.Site              | 1           | 1           | IfcAlignment |                  | A1               |

## Drawings (Visualisations)

The following Drawings and visualisations describe the test case dataset to be modelled and certified.

| Filename                                     | Description                                  |
| -------------------------------------------- | -------------------------------------------- |
| [Testi_ml_map](./Testi_ml_map.pdf)           | Planar (map) view of the test case           |
| [Testi_ml_profiles](./Testi_ml_profiles.pdf) | Long section (profile) view of the test case |


## 
