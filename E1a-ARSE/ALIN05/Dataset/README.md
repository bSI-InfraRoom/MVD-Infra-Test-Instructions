## Model Dataset

- - This test case utilises the following dataset:
    - One alignment layout (no geometric representation is required)
    - The alignment is composed of one horizontal alignment layout and one vertical alignment layout
    - The horizontal layout has the following sequences of elements:
  
      - Line => Clothoid => Circular arc (cw) => Clothoid => Clothoid  => Circular arc (ccw) => Clothoid => Clothoid => Circular arc (cw)
    - The vertical layout has the following sequences of elements:
  
      - Line => Parabolic arc => Line
      - Line => Parabolic arc => Parabolic arc => Line
      - Line => Line => Line => ...
  

| Filename                                                     | Description                                   |
| ------------------------------------------------------------ | --------------------------------------------- |
| [HorizontalAlignmentParameters](./HorizontalAlignmentParameters.csv) | Parameters for the horizontal segments as csv |
| [VerticalAlignmentParameters](./VerticalAlignmentParameters.csv) | Parameters for the vertical segments as csv   |
| [LandXML](./T616AAC0.xml)                                    | LandXML-file representing the alignment       |

## Dataset specification

### Entities table

| **Element**            | **Attribute** | **Value**   | **Notes** |
| ---------------------- | ------------- | ----------- | --------- |
| IfcProject             | Name          | Alin05      |           |
| IfcSite                | Name          | Alin05.Site |           |
| IfcAlignment           | Name          | A1          |           |
| IfcRoad                | Name          | Alin05.Road |           |
| IfcAlignmentHorizontal | Name          | AH1         |           |
| IfcAlignmentVertical   | Name          | AV1         |           |

### Horizontal segments table

Horizontal segments nested into AH1 in the following order:

| Entity                        | PredefinedType | Name | Start Point X | Start Point Y | Start Direction | Start Radius Of Curvature | End Radius Of Curvature | Segment Length |
| ----------------------------- | -------------- | ---- | ------------- | ------------- | --------------- | ------------------------- | ----------------------- | -------------- |
| IfcAlignmentHorizontalSegment | LINE           | H1   | 145685,8552   | 6591370,142   | 3,817860174     | 0                         | 0                       | 47,36403       |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H2   | 145648,9153   | 6591340,498   | 3,817860159     | 0                         | 185                     | 84,45946       |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H3   | 145587,3939   | 6591282,917   | 4,046128984     | 185                       | 185                     | 137,211623     |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H4   | 145548,3555   | 6591154,638   | 4,78781345      | 185                       | 0                       | 59,594595      |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H5   | 145559,1771   | 6591096,104   | 4,948879761     | 0                         | -203,799988             | 55,65383       |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H6   | 145569,7329   | 6591041,507   | 4,812339587     | -203,799988               | -203,799988             | 25,757113      |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H7   | 145570,6789   | 6591015,784   | 4,68595602      | -203,799988               | 0                       | 125,614636     |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H8   | 145541,9224   | 6590894,05    | 4,377775936     | 0                         | 851,999999              | 118,881381     |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H9   | 145505,5107   | 6590780,909   | 4,447541815     | 851,999999                | 851,999999              | 2,84745        |

### Vertical segments table

Vertical segments nested into AV1 in the following order:

| Entity                      | PredefinedType   | Name | Start Dist Along | Horizontal Length | Start Height | Start Gradient | End Gradient | RadiusOfCurvature |
| --------------------------- | ---------------- | ---- | ---------------- | ----------------- | ------------ | -------------- | ------------ | ----------------- |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V1   | 85               | 1,41860495        | 15,82        | 0,009739982    | 0,009739982  | 0                 |
| IfcAlignmentVerticalSegment | PARABOLICARC     | V2   | 86,41860495      | 20,6264881        | 15,83381719  | 0,009739982    | 0,023047408  | 1549,998375       |
| IfcAlignmentVerticalSegment | PARABOLICARC     | V3   | 107,0450938      | 30,9389625        | 16,17196156  | 0,023047408    | 0,016859621  | -5000,004241      |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V4   | 137,9840563      | 66,893377         | 16,78930258  | 0,016859621    | 0,016859621  | 0                 |
| IfcAlignmentVerticalSegment | PARABOLICARC     | V5   | 204,8774333      | 12,6667695        | 17,91709954  | 0,016859621    | 0,012637385  | -3000,015228      |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V6   | 217,5442028      | 4,4678966         | 18,10391542  | 0,012637385    | 0,012637385  | 0                 |
| IfcAlignmentVerticalSegment | PARABOLICARC     | V7   | 222,0120994      | 13,9676113        | 18,16037796  | 0,012637385    | 0,017293222  | 3000,021522       |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V8   | 235,9797107      | 29,55312205       | 18,36940751  | 0,017293222    | 0,017293222  | 0                 |
| IfcAlignmentVerticalSegment | PARABOLICARC     | V9   | 265,5328327      | 17,4384826        | 18,88047622  | 0,017293222    | 0,023106068  | 2999,990831       |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V10  | 282,9713153      | 12,9163156        | 19,23272738  | 0,023106068    | 0,023106068  | 0                 |
| IfcAlignmentVerticalSegment | PARABOLICARC     | V11  | 295,8876309      | 64,5895582        | 19,53117264  | 0,023106068    | 0,045000824  | 2950,001197       |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V12  | 360,4771891      | 0,0557456         | 21,73066968  | 0,045000824    | 0,045000824  | 0                 |
| IfcAlignmentVerticalSegment | PARABOLICARC     | V13  | 360,5329347      | 42,5278306        | 21,73317828  | 0,045000824    | 0,030824882  | -3000,000288      |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V14  | 403,0607653      | 126,9386947       | 23,34552968  | 0,030824882    | 0,030824882  | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V15  | 529,99946        | 10                | 27,2584      | 0,028668       | 0,028668     | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V16  | 539,99946        | 10                | 27,54508     | 0,027292       | 0,027292     | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V17  | 549,99946        | 10                | 27,818       | 0,026832       | 0,026832     | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V18  | 559,99946        | 10                | 28,08632     | 0,026325       | 0,026325     | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V19  | 569,99946        | 10                | 28,34957     | 0,02537        | 0,02537      | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V20  | 579,99946        | 10                | 28,60327     | 0,020813       | 0,020813     | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V21  | 589,99946        | 10                | 28,8114      | 0,020176       | 0,020176     | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V22  | 599,99946        | 10                | 29,01316     | 0,019498       | 0,019498     | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V23  | 609,99946        | 10                | 29,20814     | 0,018781       | 0,018781     | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V24  | 619,99946        | 10                | 29,39595     | 0,018022       | 0,018022     | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V25  | 629,99946        | 10                | 29,57617     | 0,017226       | 0,017226     | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V26  | 639,99946        | 10                | 29,74843     | 0,01639        | 0,01639      | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V27  | 649,99946        | 7,384658          | 29,91233     | 0,015674389    | 0,015674389  | 0                 |

### Spatial (De)Composition table

| **Parent Element** | **Parent Element Type** | **Parent Element Name** | **MinSize** | **MaxSize** | **Child Element** | **Child Element Type** | **Child Element Name** |
| ------------------ | ----------------------- | ----------------------- | ----------- | ----------- | ----------------- | ---------------------- | ---------------------- |
| IfcProject         |                         | Alin05                  | 1           | 1           | IfcSite           |                        | Alin05.Site            |
| IfcSite            |                         | Alin05.Site             | 1           | 1           | IfcRoad           |                        | Allin05.Road           |

### Spatial Containment table

| **Spatial Element** | **Spatial Element Type** | **Spatial Element Name** | **MinSize** | **MaxSize** | **Element**  | **Element Type** | **Element Name** |
| ------------------- | ------------------------ | ------------------------ | ----------- | ----------- | ------------ | ---------------- | ---------------- |
| IfcSite             |                          | Alin05.Site              | 1           | 1           | IfcAlignment |                  | A1               |

### Product Geometric Representation table

| **Product**            | **Product Type** | **Product Name** | **Representation Identifier** | **Representation Type** | **Items**           |
| ---------------------- | ---------------- | ---------------- | ----------------------------- | ----------------------- | ------------------- |
| IfcAlignment           | na               | A1               | Axis                          | Curve3D                 | 1 IfcGradientCurve  |
| IfcAlignmentHorizontal | na               | AH1              | Axis                          | Curve2D                 | 1 IfcCompositeCurve |
| IfcAlignmentVertical   | na               | AV1              | Axis                          | Curve2D                 | 1 IfcGradientCurve  |

### Product Placement table

| **Product**  | **Product Type** | **Product Name** | **Object Placement** | Relative Placement Product | Relative Placement Product Type | Relative Placement Product Name |
| ------------ | ---------------- | ---------------- | -------------------- | -------------------------- | ------------------------------- | ------------------------------- |
| IfcAlignment |                  | A1               | IfcLocalPlacement    | IfcSite                    | na                              | Alin05.Site                     |

## Drawings (Visualisations)

The following Drawings and visualisations describe the test case dataset to be modelled and certified.

| Filename                           | Description                                  |
| ---------------------------------- | -------------------------------------------- |
| [Horizontal](./Horizontal.PNG)     | Planar view of the horizontal alignment      |
| [Vertical](./T616AAC0_profile.pdf) | Long section (profile) view of the alignment |


## 
