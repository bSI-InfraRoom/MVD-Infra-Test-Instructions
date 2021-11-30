# Dataset description


|       Test Case title     | Code | Abbreviation | Author | Data Owner |
|:-------------------------:|:----:|:------------:|:------:| :---------:|
|  Aggregate structures + Track. Pavement and Course (ballast) + Cant | E2b1 | ASTPC | Evandro Alfieri | RFI |

## Dataset

| ID | Filename                                                        | Type (format)  | Description                               |
|----|-----------------------------------------------------------------|----------------|-------------------------------------------|
|    | *filename + link*                                               | csv            | [Alignment parameters for horizontal segments](#Alignment-parameters-for-horizontal-segments) |
|    | *filename + link*                                               | csv            | [Alignment parameters for vertical segments](#Alignment-parameters-for-vertical-segments) |
|    | *filename + link*                                               | csv            | [Alignment parameters for cant segments](#Alignment-parameters-for-cant-segments) |
|    | *filename + link*                                               | LandXML        | Alignment LandXML file, not including cant  |
|    | *filename + link*                                               | dwg            | Alignment dwg file, not including cant  |
|    | [Line_layout](./Line_layout.jpg)                                | figure (jpg)   | Schematic layout of the test case railway line |
|    | [Objects overview](./ObjectsOverview.png)         | diagram (png)  | [Objects overview](#Objects-overview): a diagram + table describing the main to be used for the test case |
|    | *filename + link*                                               | drawing (pdf)  | Cross section example |
|    | *filename + link*                                               | drawing (dwg)  | Cross section example |
|    | *filename + link*                                               | drawing (PDF)  | Turnout drawing to be used as example |

---

## Alignment parameters for horizontal segments

<details><summary>expand/collapse</summary>

The meaning of the columns in the spreadsheet for the Horizontal Alignment is explained below (from left to right). **Please note** that *Spiral* is equal to *Clothoid* in the Point Type:

1. **Element type**:
    - Linear = straight line
    - Clothoid = transition curve used in Italy
    - Circular = arc curve
2. **Point Type** (start)
    - TS tangent to spiral 
    - SC spiral to curve 
    - CS curve to spiral 
    - ST spiral to tangent
    - SS spiral spiral
    - START starting point 
    - END ending point
3. **Station**: defines the point distance from the origin on the horizontal projection
4. **Start northing**: defines the start coordinate North
5. **Start easting**: defines the start coordinate East
6. **Start direction**: defines the Azimuth of the start point
7. **Point Type** (end): same as Point Type (start)
8. **End northing**: defines the end coordinate North
9. **End easting**: defines the end coordinate East
10. **End direction**: defines the Azimuth of the end point
11. **Length**: defines the length of the element (segment) on the horizontal projection
12. **Radius**: defines the Radius of the segment, only for “circular arc curve”

**NOTE**:
- All distances are in meters
- All angles are in gradian
- All the coordinates are defined using the UTM Coordinate System
- The radius is considered positive when the curve is to the right, and negative when it is to the left

#### Data snippet

![alt text](./Horizontal%20alignment%20image.png)

![alt text](./Horizontal%20alignment%20table.png)

</details>

## Alignment parameters for vertical segments

<details><summary>expand/collapse</summary>
The meaning of the columns in the spreadsheet for the Vertical Alignment is explained below (from left to right):

1. **Element type**:
    - Linear = straight line
    - Circular = arc curve
2. **Point Type** (start):
    - VPC Vertical point of curvature 
    - VPT Vertical point of tangency 
    - START point of beginning 
    - END point of ending
3. **Start Station**: defines the point distance from the origin, on the horizontal projection
4. **Start Elevation**: defines the start elevation:
5. **Start Gradient**: defines the Zenith angle of the start point
6. **Point Type** (end): same as Pont Type (start)
7. **End Station**: defines the point distance from the origin, on the horizontal projection
8. **End Elevation**: defines the end elevation:
9. **End Gradient**: defines the Zenith angle of the end point
10. **R**: defines the vertical circular radius of the segment.

**NOTE**:
- All distances are in meters
- All angles are in gradian
- The radius (**R**) is considered positive when the curve is convex, and negative when it is concave

#### Data snippet

![alt text](./Vertical%20alignment%20image.png)

![alt text](./Vertical%20alignment%20table.png)

</details>

## Alignment parameters for cant segments

<details><summary>expand/collapse</summary>
The meaning of the columns in the spreadsheet for the Cant Alignment is explained below (from left to right). **Please note** that *Spiral* is equal to *Clothoid* in the Point Type:

1. **Type**: is the type of point
    - TS tangent to spiral 
    - SC spiral to curve 
    - CS curve to spiral 
    - ST spiral to tangent
    - SS spiral spiral
    - START starting point 
    - END ending point
2. **Station**: defines the point distance from the origin, on the horizontal projection
3. **Speed**: parameter used to calculate cant (may be used used for validation)
4. **Radius**: the radius of the curve that, in the horizontal alignment, starts/ends in that station point
5. **Transition**: the type of transition curve that, in the horizontal alignment, stays between that station point and the next one
6. **Applied cant**: in a cross-section plane, orthogonal to the track axis, it is the difference in height (h<sub>t</sub> in the picture below) between two points, of the track plane, that have a conventional distance between them of 1500 mm. The cant is always applied to the external rail (the furthest rail from the center or the curve). Cant measure is positive because the external rail of a track is always higher than the internal rail.

![alt text](./Cant-CantAngle.png)

**NOTE**:
- In Italy, only straight line is used for cant segment
- All distances are in meters, except the Cant that is in millimetres
- All angles are in gradian
- Speed is in kilometres per hour (km/h)
- The radius (**R**) is considered positive when the curve is to the right, and negative when it is to the left


#### Data snippet

![alt text](./Cant%20alignment%20image.jpg)

![alt text](./Cant%20alignment%20table.png)

</details>

## Objects overview

<details><summary>expand/collapse</summary>
The picture captures main objects and relationships to be present in the IFC file

![alt text](./E2b1-ASTPC_Main%20objects%20and%20relationships.png)

The table lists the direct attributes of the above mentioned objects

| Entity                 | Name                                | Description                | ObjectType | PredefinedType        | CompositionType | NOTE                  |
|------------------------|-------------------------------------|----------------------------|------------|-----------------------|-----------------|-----------------------|
| IfcSite                | Sito                                | $                          | $          | $                     | na              |                       |
| IfcRailway             | Foligno                             | LO1336                     | Località   | USERDEFINED           | ELEMENT         |                       |
| IfcTypeObject          | Binari di corsa (Contenitore)       | $                          | $          | $                     | na              |                       |
| IfcGroup               | Binari di corsa di Foligno          | LO1336-BC                  | $          | $                     | na              | isTypedBy             |
| IfcFacilityPart        | Binario IV dispari - Orte Falconara | LO1336-BC-BC01             | $          | TRACKSTRUCTURE        | na              |                       |
| IfcTypeObject          | Deviatoi/Intersezioni (Contenitore) | $                          | $          | $                     | na              |                       |
| IfcGroup               | Deviatoi                            | LO1336-BC-BC01-DEV         | $          | $                     | na              | isTypedBy             |
| IfcTypeObject          | Rotaie (Contenitore)                | $                          | $          | $                     | na              |                       |
| IfcGroup               | Rotaie                              | LO1336-BC-BC01-ROT         | $          | $                     | na              | isTypedBy             |
| IfcTypeObject          | Massicciata (Contenitore)           | $                          | $          | $                     | na              |                       |
| IfcGroup               | Massicciata                         | LO1336-BC-BC01-MAS         | $          | $                     | na              | isTypedBy             |
| IfcTypeObject          | Traverse (Contenitore)              | $                          | $          | $                     | na              |                       |
| IfcGroup               | Traverse                            | LO1336-BC-BC01-TRA         | $          | $                     | na              | isTypedBy             |
| IfcActuatorType        | Manovra deviatoio                   | $                          | $          | $                     | na              |                       |
| IfcActuator            | Cassa di manovra CM04               | LO1336-BC-BC01-DEV-D02-MD1 | $          | $                     | na              | isTypedBy             |
| IfcElementAssembly     | DEVIAT.EL. 7A + 9                   | LO1336-BC-BC01-DEV-D02     | $          | TURNOUTPANEL          | na              |                       |
| IfcRail                | Telaio                              | $                          | $          | RAIL                  | na              |                       |
| IfcRail                | Controrotaie                        | $                          | $          | CHECKRAIL             | na              |                       |
| IfcFastener            | Giunti                              | $                          | $          | WELD                  | na              |                       |
| IfcTrackElement        | Cuore                               | $                          | $          | FROG                  | na              |                       |
| IfcTrackElement        | Traverse e attacchi                 | $                          | $          | SLEEPER               | na              |                       |
| IfcCourseType          | Segmento di massicciata             | $                          | $          | $                     | na              |                       |
| IfcCourse              | Segmento di massicciata M01         | LO1336-BC-BC01-MAS-M01     | $          | BALLASTBED            | na              | isTypedBy             |
| IfcCourse              | Segmento di massicciata M02         | LO1336-BC-BC01-MAS-M02     | $          | BALLASTBED            | na              | isTypedBy             |
| IfcTypeObject          | Segmento di rotaia                  | $                          | $          | $                     | na              |                       |
| IfcGroup               | Segmento di rotaia R01              | LO1336-BC-BC01-ROT-R01     | $          | $                     | na              | isTypedBy             |
| IfcRail                | Rotaia 01 DX                        | $                          | $          | RAIL                  | na              |                       |
| IfcRail                | Rotaia 01 SX                        | $                          | $          | RAIL                  | na              |                       |
| IfcGroup               | Segmento di rotaia R02              | LO1336-BC-BC01-ROT-R02     | $          | $                     | na              | isTypedBy             |
| IfcRail                | Rotaia 02 DX                        | $                          | $          | RAIL                  | na              |                       |
| IfcRail                | Rotaia 02 SX                        | $                          | $          | RAIL                  | na              |                       |
| IfcGroup               | Segmento di rotaia R03              | LO1336-BC-BC01-ROT-R03     | $          | $                     | na              | isTypedBy             |
| IfcRail                | Rotaia 03 DX                        | $                          | $          | RAIL                  | na              |                       |
| IfcRail                | Rotaia 03 SX                        | $                          | $          | RAIL                  | na              |                       |
| IfcTypeObject          | Segmento di traverse                | $                          | $          | $                     | na              |                       |
| IfcGroup               | Segmento di traverse T01            | LO1336-BC-BC01-TRA-T01     | $          | $                     | na              | isTypedBy             |
| IfcGroup               | Segmento di traverse T02            | LO1336-BC-BC01-TRA-T02     | $          | $                     | na              | isTypedBy             |
| IfcGroup               | Segmento di traverse T03            | LO1336-BC-BC01-TRA-T03     | $          | $                     | na              | isTypedBy             |
| IfcTrackElement        | Traversa NNNN                       | $                          | $          | SLEEPER               | na              | NNNN indicates number |
| _____________________  | _____________________               | _____________________      | _______    | _____________________ | na              | _____________________ |
| IfcAlignment           | Alignment 1                         | $                          | $          | $                     | na              |                       |
| IfcAlignment           | Alignment 2                         | $                          | $          | $                     | na              |                       |
| IfcAlignmentHorizontal | Horizontal 1                        | $                          | $          | na                    | na              |                       |
| IfcAlignmentVertical   | Vertical 1                          | $                          | $          | na                    | na              |                       |
| IfcAlignmentCant       | Cant 1                              | $                          | $          | na                    | na              |                       |
| IfcAlignmentHorizontal | Horizontal 2                        | $                          | $          | na                    | na              |                       |
| IfcAlignmentVertical   | Vertical 2                          | $                          | $          | na                    | na              |                       |

</details>