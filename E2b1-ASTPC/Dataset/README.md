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

The line for the test is made of two alignments:
1. Alignment 1: Primary route (red in the figure below)
2. Alignment 2: Diverted route (blue dashed in the figure below)

Snippet:
<img src="./LineLayout.svg" height="600"/>

The **Alignment 1: Primary route** is made of the following **9 segments**:

<div align="center">

| # | Type of segment | From (pk) | To (pk)  | Segment length |
|---|-----------------|-----------|----------|----------------|
| 1 | LINE            | 0.0000    | 234.7194 | 234.7194       |
| 2 | CLOTHOID        | 234.7194  | 274.7194 | 40.0000        |
| 3 | CIRCULARARC     | 274.7194  | 468.1839 | 193.4645       |
| 4 | CLOTHOID        | 468.1839  | 508.1839 | 40.0000        |
| 5 | LINE            | 508.1839  | 547.1654 | 38.9815        |
| 6 | CLOTHOID        | 547.1654  | 587.1654 | 40.0000        |
| 7 | CIRCULARARC     | 587.1654  | 696.5971 | 109.4317       |
| 8 | CLOTHOID        | 696.5971  | 736.5971 | 40.0000        |
| 9 | LINE            | 736.5971  | 876.3682 | 139.7711       |
</div>

The **Alignment 2: Diverted route** is made of the following **11 segments**:

<div align="center">

| #  | Type of segment | From (pk) | To (pk)  | Segment length |
|----|-----------------|-----------|----------|----------------|
| 1  | CIRCULARARC     | 0.0000    | 22.9021  | 22.9021        |
| 2  | LINE            | 22.9021   | 30.8376  | 7.9355         |
| 3  | LINE            | 30.8376   | 99.1345  | 68.2969        |
| 4  | CLOTHOID        | 99.1345   | 139.1345 | 40.0000        |
| 5  | CIRCULARARC     | 139.1345  | 424.3769 | 285.2424       |
| 6  | CLOTHOID        | 424.3769  | 464.3769 | 40.0000        |
| 7  | LINE            | 464.3769  | 501.2857 | 36.9088        |
| 8  | CLOTHOID        | 501.2857  | 540.9846 | 39.6989        |
| 9  | CIRCULARARC     | 540.9846  | 648.4760 | 107.4914       |
| 10 | CLOTHOID        | 648.4760  | 688.1749 | 39.6989        |
| 11 | LINE            | 688.1749  | 828.0965 | 139.9216       |
</div>

All parameters of the segments, for both alignments, are detailed below in:

- [Alignment parameters for horizontal segments](#Alignment-parameters-for-horizontal-segments)
- [Alignment parameters for vertical segments](#Alignment-parameters-for-vertical-segments)
- [Alignment parameters for cant segments](#Alignment-parameters-for-cant-segments)

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

The horizontal layout of the alignment (both for Alignment 1 and Alignment 2) is described using a CSV file. The column headers match the IFC attributes for `IfcAlignmentHorizontalSegment`. Refers to the standard's documentation for their description.

#### Alignment 1: Primary route

| ID | PredefinedType | Start Point X | Start Point Y | Start Direction | Start Radius Of Curvature | End Radius Of Curvature | Segment Length |
|----|----------------|---------------|---------------|-----------------|---------------------------|-------------------------|----------------|
| 1  | LINE           | 452413.9199   | 4539456.4010  | 0.214271681     | 0                         | 0                       | 234.719412     |
| 2  | CLOTHOID       | 452634.4150   | 4539536.8690  | 0.214271681     | 0                         | -1000                   | 40.000000      |
| 3  | CIRCULARARC    | 452671.8980   | 4539550.8320  | 0.236493911     | -1000                     | -1000                   | 193.464471     |
| 4  | CLOTHOID       | 452844.4075   | 4539637.7370  | 0.451454422     | -1000                     | 0                       | 40.000000      |
| 5  | LINE           | 452877.9371   | 4539659.5480  | 0.473676652     | 0                         | 0                       | 38.981516      |
| 6  | CLOTHOID       | 452910.4711   | 4539681.0210  | 0.473676652     | 0                         | 1000                    | 40.000000      |
| 7  | CIRCULARARC    | 452944.0007   | 4539702.8310  | 0.451454422     | 1000                      | 1000                    | 109.431750     |
| 8  | CLOTHOID       | 453039.5298   | 4539756.1000  | 0.329863598     | 1000                      | 0                       | 40.000000      |
| 9  | LINE           | 453075.7086   | 4539773.1600  | 0.307641368     | 0                         | 0                       | 139.771059     |

#### Alignment 2: Diverted route

| ID | PredefinedType | Start Point X | Start Point Y | Start Direction | Start Radius Of Curvature | End Radius Of Curvature | Segment Length |
|----|----------------|---------------|---------------|-----------------|---------------------------|-------------------------|----------------|
| 1  | CIRCULARARC    | 452460.8898   | 4539473.5430  | 0.214271681     | 0                         | 249.538                 | 22.902068      |
| 2  | LINE           | 452482.7338   | 4539480.3960  | 0.112296264     | 0                         | 0                       | 7.935500       |
| 3  | LINE           | 452490.4064   | 4539482.4220  | 0.112296264     | 0                         | 0                       | 68.296941      |
| 4  | CLOTHOID       | 452556.4403   | 4539499.8580  | 0.112296264     | 0                         | -1000                   | 40.000000      |
| 5  | CIRCULARARC    | 452595.0453   | 4539510.3270  | 0.134518477     | -1000                     | -1000                   | 285.242348     |
| 6  | CLOTHOID       | 452854.5258   | 4539626.4420  | 0.451454422     | -1000                     | 0                       | 40.000000      |
| 7  | LINE           | 452888.0554   | 4539648.2530  | 0.473676652     | 0                         | 0                       | 36.908858      |
| 8  | CLOTHOID       | 452918.8596   | 4539668.5850  | 0.473676652     | 0                         | 985                     | 39.698871      |
| 9  | CIRCULARARC    | 452952.1378   | 4539690.2300  | 0.451285858     | 985                       | 985                     | 107.491403     |
| 10 | CLOTHOID       | 453045.9733   | 4539742.5540  | 0.330032162     | 985                       | 0                       | 39.698871      |
| 11 | LINE           | 453081.8789   | 4539759.4870  | 0.307641368     | 0                         | 0                       | 139.921625     |

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

---
## Alignment parameters for vertical segments

The vertical layout of the alignment (both for Alignment 1 and Alignment 2) is described using a CSV file. The column headers match the IFC attributes for `IfcAlignmentVerticalSegment`. Refers to the standard's documentation for their description.

#### Alignment 1: Primary route

| ID | PredefinedType   | Start Dist Along | Horizontal Length | Start Height | Start Gradient | End Gradient | RadiusOfCurvature |
|----|------------------|------------------|-------------------|--------------|----------------|--------------|-------------------|
| 1  | CONSTANTGRADIENT |                  |                   | 5            |                |              |                   |
| 2  | CIRCULARARC      | 325.0006         | 49.9975           | 5            | 0              | -0.01        | 5000              |
| 3  | CONSTANTGRADIENT | 374.9981         | 250.0038          | 4.75         | -0.01          | -0.01        |                   |
| 4  | CIRCULARARC      | 625.0019         | 49.9975           | 2.25         | -0.01          | 0            | -5000             |
| 5  | CONSTANTGRADIENT | 674.9994         | 201.3688          | 2            | 0              | 0            |                   |

#### Alignment 2: Diverted route

| ID | PredefinedType   | Start Dist Along | Horizontal Length | Start Height | Start Gradient | End Gradient | RadiusOfCurvature |
|----|------------------|------------------|-------------------|--------------|----------------|--------------|-------------------|
| 1  | CONSTANTGRADIENT |                  |                   | 5            |                |              |                   |
| 2  | CIRCULARARC      | 277.0671         | 49.8646           | 5            | 0              | -0.009973    | 5000              |
| 3  | CONSTANTGRADIENT | 326.9317         | 250.9366          | 4.7513       | -0.009973      | -0.009973    |                   |
| 4  | CIRCULARARC      | 577.8683         | 49.8646           | 2.2487       | -0.009973      | 0            | -5000             |
| 5  | CONSTANTGRADIENT | 627.7329         | 200.3636          | 2            | 0              | 0            |                   |

**NOTE**:
- All distances are in meters
- All angles are in gradian
- The radius (*RadiusOfCurvature*) is considered positive when the curve is convex, and negative when it is concave

---
## Alignment parameters for cant segments

The cant layout of the alignment (both for Alignment 1 and Alignment 2) is described using a CSV file. The column headers match the IFC attributes for `IfcAlignmentCantSegment`. Refers to the standard's documentation for their description.

#### Alignment 1: Primary route

| ID | PredefinedType   | Start Dist Along | Horizontal Length | Start Cant left | End Cant left | Start Cant right | End Cant right |
|----|------------------|------------------|-------------------|-----------------|---------------|------------------|----------------|
| 1  | CONSTANTCANT     | 0.0000           | 234.7194          | 0               | 0             | 0                | 0              |
| 2  | LINEARTRANSITION | 234.7194         | 40.0000           | 0               | 0             | 0                | 0.06           |
| 3  | CONSTANTCANT     | 274.7194         | 193.4645          | 0               | 0             | 0.06             | 0.06           |
| 4  | LINEARTRANSITION | 468.1839         | 40.0000           | 0               | 0             | 0.06             | 0              |
| 5  | CONSTANTCANT     | 508.1839         | 38.9815           | 0               | 0             | 0                | 0              |
| 6  | LINEARTRANSITION | 547.1654         | 40.0000           | 0               | 0.06          | 0                | 0              |
| 7  | CONSTANTCANT     | 587.1654         | 109.4317          | 0.06            | 0.06          | 0                | 0              |
| 8  | LINEARTRANSITION | 696.5971         | 40.0000           | 0.06            | 0             | 0                | 0              |
| 9  | CONSTANTCANT     | 736.5971         | 139.7711          | 0               | 0             | 0                | 0              |
| 10 | CONSTANTCANT     | 876.3682         | -876.3682         | 0               | 0             | 0                | 0              |

#### Alignment 2: Diverted route

| ID | PredefinedType   | Start Dist Along | Horizontal Length | Start Cant left | End Cant left | Start Cant right | End Cant right |
|----|------------------|------------------|-------------------|-----------------|---------------|------------------|----------------|
| 1  | CONSTANTCANT     | 0.0000           | 22.9021           | 0               | 0             | 0                | 0              |
| 2  | CONSTANTCANT     | 22.9021          | 7.9355            | 0               | 0             | 0                | 0              |
| 3  | CONSTANTCANT     | 30.8376          | 68.2969           | 0               | 0             | 0                | 0              |
| 4  | LINEARTRANSITION | 99.1345          | 40.0000           | 0               | 0             | 0                | 0.01           |
| 5  | CONSTANTCANT     | 139.1345         | 285.2424          | 0               | 0             | 0.01             | 0.01           |
| 6  | LINEARTRANSITION | 424.3769         | 40.0000           | 0               | 0             | 0.01             | 0              |
| 7  | CONSTANTCANT     | 464.3769         | 36.9088           | 0               | 0             | 0                | 0              |
| 8  | LINEARTRANSITION | 501.2857         | 39.6989           | 0               | 0.01          | 0                | 0              |
| 9  | CONSTANTCANT     | 540.9846         | 107.4914          | 0.01            | 0.01          | 0                | 0              |
| 10 | LINEARTRANSITION | 648.4760         | 39.6989           | 0.01            | 0             | 0                | 0              |
| 11 | CONSTANTCANT     | 688.1749         | 139.9216          | 0               | 0             | 0                | 0              |
| 12 | CONSTANTCANT     | 828.0965         | -828.0965         | 0               | 0             | 0                | 0              |

**NOTE**:
- In Italy, only straight line is used for cant segment
- All distances are in meters
- Applied cant: in a cross-section plane, orthogonal to the track axis, it is the difference in height (h<sub>t</sub> in the picture below) between two points, of the track plane, that have a conventional distance between them of 1500 mm. The cant is always applied to the external rail (the furthest rail from the center or the curve). Cant measure is positive because the external rail of a track is always higher than the internal rail.

<p align="center">
    <img src="./Cant-CantAngle.png" height="200"/>
</p>

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