# Dataset description


|       Test Case title     | Code | Abbreviation | Author | Data Owner |
|:-------------------------:|:----:|:------------:|:------:| :---------:|
|  Aggregate structures + Track. Pavement and Course (ballast) + Cant | E2b1 | ASTPC | Evandro Alfieri | RFI |

## Dataset

| Filename                                               | Description                                                                                               |
|--------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| [Line_layout](./Line_layout.jpg)                       | Schematic [line layout](#Line-layout) of the test case                                                    |
| [TrackCrossSection](./TrackCrossSection.png)           | [Track cross section](#Track-cross-section) to be used as example                                         |
| [SleeperPlacement](./SleeperPlacement.png)             | Information on how to [position sleepers](#Sleeper-placement) along the alignment                         |
| *under production*                                     | [Alignment parameters for horizontal segments](#Alignment-parameters-for-horizontal-segments)             |
| *under production*                                     | [Alignment parameters for vertical segments](#Alignment-parameters-for-vertical-segments)                 |
| *under production*                                     | [Alignment parameters for cant segments](#Alignment-parameters-for-cant-segments)                         |
| *under production*                                     | Alignment LandXML file, not including cant                                                                |
| *under production*                                     | Alignment dwg file, not including cant                                                                    |
| [ObjectsOverview](./ObjectsOverview.png)               | [Objects overview](#Objects-overview): a diagram + table describing the main to be used for the test case |
| [FS60UNI_R.250_TG.0.092](./FS60UNI_R.250_TG.0.092.svg) | [Turnout drawing](#Turnout-example) to be used as example. **The objective of the test IS NOT to reproduced it** |
| [SimplifiedTurnout](./SimplifiedTurnout.png)           | [Simplified turnout](#Simplified-trnout) scheme. **The objective of the test IS NOT to reproduced the turnout**                 |


---
## Line layout

Short description:

Snippet:
<img src="./Line_layout.jpg">

---
## Track cross section

Short description:

Snippet:
<img src="./TrackCrossSection.png">

---
## Sleeper placement

Short description:

Snippet:
<img src="./SleeperPlacement.png">

---
## Alignment parameters for horizontal segments

The horizontal layout of the alignment is described using a CSV file. The column headers match the IFC attributes for `IfcAlignmentHorizontalSegment`. Refers to the standard's documentation for their description.

![alt text](./Horizontal%20alignment%20table.png)

**NOTE**:
- All distances are in meters
- All angles are in radian (see note below)
- All the coordinates are defined using the UTM Coordinate System
- The *Radius Of Curvature* is considered positive when the curve is to the right, and negative when it is to the left

**IMPORTANT**:

When using IFC to exchange information, the file must respect IFC convention [marked as ii) in the figure below].
This implies a right-hand cartesian coordinate systems; and angles are measured from x-axis, counter clock-wise.

<p align="center">
    <img src="SurveyToIFCangleConvention.png" height="500"/>
</p>

#### Data snippet
![alt text](./Horizontal%20alignment%20image.png)

---
## Alignment parameters for vertical segments

The vertical layout of the alignment is described using a CSV file. The column headers match the IFC attributes for `IfcAlignmentVerticalSegment`. Refers to the standard's documentation for their description.

![alt text](./Vertical%20alignment%20table.png)

**NOTE**:
- All distances are in meters
- All angles are in gradian
- The radius (*RadiusOfCurvature*) is considered positive when the curve is convex, and negative when it is concave

#### Data snippet

![alt text](./Vertical%20alignment%20image.png)

---
## Alignment parameters for cant segments

The cant layout of the alignment is described using a CSV file. The column headers match the IFC attributes for `IfcAlignmentCantSegment`. Refers to the standard's documentation for their description.

![alt text](./Cant%20alignment%20table.png)

**NOTE**:
- In Italy, only straight line is used for cant segment
- All distances are in meters
- Applied cant: in a cross-section plane, orthogonal to the track axis, it is the difference in height (h<sub>t</sub> in the picture below) between two points, of the track plane, that have a conventional distance between them of 1500 mm. The cant is always applied to the external rail (the furthest rail from the center or the curve). Cant measure is positive because the external rail of a track is always higher than the internal rail.

<p align="center">
    <img src="./Cant-CantAngle.png" height="200"/>
</p>

#### Data snippet

![alt text](./Cant%20alignment%20image.jpg)

---
## Objects overview

The picture captures main objects and relationships to be present in the IFC file

![alt text](./ObjectsOverview.png)

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

---
## Turnout example

Short description:

Snippet:
<img src="./FS60UNI_R.250_TG.0.092.svg">

---
## Simplified turnout

Short description:

Snippet:
<img src="./SimplifiedTurnout.png"> 

---