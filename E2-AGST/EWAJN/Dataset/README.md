## Model Dataset

This test case utilizes the following dataset.

- A dataset including two intersecting roads in a T junction (a secondary road ending at and joining a primary road).

- The main alignments for the primary and the secondary roads
- Alignments for the pavement edges where the two roads meet. 
- An alignment is defined to separate the pavements belonging to the primary road from the pavements belonging to the secondary road.
- For each road, the pavements aggregates of a couple of courses that are represented by IfcFacetedBrep. 
  - These elements carry material and Psets
- A spatial structure representing the breakdown of the junction project

| Filename | Description |
| -------- | ----------- |
|          |             |
|          |             |
|          |             |
|          |             |

## Dataset specification

### Entities table

| **Element**            | **Attribute**  | **Value**                              | **Notes**                                                    |
| ---------------------- | -------------- | -------------------------------------- | ------------------------------------------------------------ |
| IfcProject             | Name           | TRV                                    |                                                              |
| IfcSite                | Name           | TRV                                    |                                                              |
| IfcAlignment           | Name           | CL Primärväg                           | Centerline for primary road                                  |
| IfcAlignmentHorizontal | Name           | CL Primärväg \| Horizontal alignment   | Horizontal alignment primary road                            |
| IfcAlignmentVertical   | Name           | CL Primärväg \| Vertical alignment     | Vertical alignment primary road                              |
| IfcAlignment           | Name           | CL Sekundärväg                         | Centerline for secondary road                                |
| IfcAlignmentHorizontal | Name           | CL Sekundärväg \| Horizontal alignment |                                                              |
| IfcAlignmentVertical   | Name           | CL Sekundärväg \| Vertical alignment   |                                                              |
| IfcAlignment           | Name           | HVK                                    | Pavement edge connecting right edge of primary with left edge of secondary |
| IfcAlignmentHorizontal | Name           | HVK \| Horizontal alignment            |                                                              |
| IfcAlignmentVertical   | Name           | HVK \| Vertical alignment              |                                                              |
| IfcAlignment           | Name           | VVK                                    | Pavement edge connecting right edge of secondary with right edge of primary |
| IfcAlignmentHorizontal | Name           | VVK \| Horizontal alignment            |                                                              |
| IfcAlignmentVertical   | Name           | VVK \| Vertical alignment              |                                                              |
| IfcAlignment           | Name           | Avgränsning                            | Boundary line between primary and secondary roads            |
| IfcAlignmentHorizontal | Name           | Avgränsning \| Horizontal alignment    |                                                              |
| IfcAlignmentVertical   | Name           | Avgränsning \| Vertical alignment      |                                                              |
| IfcRoad                | Name           | Primärväg                              | Primary road                                                 |
| IfcRoadPart            | Name           | Primärväg \| ROADSEGMENT               | Primary road segment                                         |
|                        | PredefinedType | ROADSEGMENT                            |                                                              |
| IfcRoad                | Name           | Sekundärväg                            | Secondary road                                               |
| IfcRoadPart            | Name           | Sekundärväg \| ROADSEGMENT             | Secondary road segment                                       |
|                        | PredefinedType | ROADSEGMENT                            |                                                              |
| IfcRoadPart            | Name           | Sekundärväg \| INTERSECTION            | The junction                                                 |
|                        | PredefinedType | INTERSECTION                           |                                                              |
| IfcPavement            | Name           | Primärväg \| PAVEMENT                  | Pavement primary road                                        |
|                        | PredefinedType | RIGID                                  |                                                              |
| IfcCourse              | Name           | Primärväg \| Slitlager                 | Wearing course primary road                                  |
|                        | PredefinedType | USERDEFINED                            |                                                              |
|                        | ObjectType     | 'Paving'                               |                                                              |
| IfcCourse              | Name           | Primärväg \| Bärlager 1                | Binder course primary road                                   |
|                        | PredefinedType | 'USERDEFINED'                          |                                                              |
|                        | ObjectType     | 'BinderCourse'                         |                                                              |
| IfcCourse              | Name           | Primärväg \| Bärlager 2                | Base course primary road                                     |
|                        | PredefinedType | 'USERDEFINED'                          |                                                              |
|                        | ObjectType     | 'BaseCourse'                           |                                                              |
| IfcCourse              | Name           | Primärväg \| Först.lager 1             | Sub base course primary road                                 |
|                        | PredefinedType | 'USERDEFINED'                          |                                                              |
|                        | ObjectType     | 'SubBaseCourse'                        |                                                              |
| IfcPavement            | Name           | Sekundärväg \| PAVEMENT                | Pavement secondary road                                      |
|                        | PredefinedType | RIGID                                  |                                                              |
| IfcCourse              | Name           | Sekundärväg \| Slitlager               | Wearing course secondary road                                |
|                        | PredefinedType | USERDEFINED                            |                                                              |
|                        | ObjectType     | 'PAVING'                               |                                                              |
| IfcCourse              | Name           | Sekundärväg \| Bärlager 1              | Binder course secondary road                                 |
|                        | PredefinedType | 'USERDEFINED'                          |                                                              |
|                        | ObjectType     | 'BINDERCOURSE'                         |                                                              |
| IfcCourse              | Name           | Sekundärväg \| Bärlager 2              | Base course secondary road                                   |
|                        | PredefinedType | 'USERDEFINED'                          |                                                              |
|                        | ObjectType     | 'BASECOURSE'                           |                                                              |
| IfcCourse              | Name           | Sekundärväg \| Först.lager 1           | Sub base course secondary road                               |
|                        | PredefinedType | 'USERDEFINED'                          |                                                              |
|                        | ObjectType     | 'SUBBASECOURSE'                        |                                                              |
| IfcPavement            | Name           | Slänt \| PAVEMENT                      | Pavement sight slope intersection                            |
|                        | PredefinedType | FLEXIBLE                               |                                                              |
| IfcCourse              | Name           | H slänt \| Först.lager 1               | Sub base course right slope intersection                     |
|                        | PredefinedType | USERDEFINED                            |                                                              |
|                        | ObjectType     | 'SUBBASECOURSE_RIGHT'                  |                                                              |
| IfcCourse              | Name           | H slänt \| Bärlager 2                  | Base course right slope intersection                         |
|                        | PredefinedType | USERDEFINED                            |                                                              |
|                        | ObjectType     | 'BASECOURSE_RIGHT'                     |                                                              |
| IfcCourse              | Name           | H slänt \| Bärlager 1                  | Binder course right slope intersection                       |
|                        | PredefinedType | USERDEFINED                            |                                                              |
|                        | ObjectType     | 'BINDERCOURSE_RIGHT'                   |                                                              |
| IfcCourse              | Name           | H-slänt \| Slitlager                   | Wearing course right slope intersection                      |
|                        | PredefinedType | USERDEFINED                            |                                                              |
|                        | ObjectType     | 'PAVING_RIGHT'                         |                                                              |
| IfcCourse              | Name           | V slänt \| Först.lager 1               | Sub base course left slope intersection                      |
|                        | PredefinedType | USERDEFINED                            |                                                              |
|                        | ObjectType     | 'SUBBASECOURSE_LEFT'                   |                                                              |
| IfcCourse              | Name           | V slänt \| Bärlager 2                  | Base course left slope intersection                          |
|                        | PredefinedType | USERDEFINED                            |                                                              |
|                        | ObjectType     | 'BASECOURSE_LEFT'                      |                                                              |
| IfcCourse              | Name           | V slänt \| Bärlager 1                  | Binder course left slope intersection                        |
|                        | PredefinedType | USERDEFINED                            |                                                              |
|                        | ObjectType     | 'BINDERCOURSE_LEFT'                    |                                                              |
| IfcCourse              | Name           | V-slänt \| Slitlager                   | Wearing course left slope intersection                       |
|                        | PredefinedType | USERDEFINED                            |                                                              |
|                        | ObjectType     | 'PAVING_LEFT'                          |                                                              |

### Properties table

| **Entity**  | **Entity Type** | Entity Name                  | **PropertySet Name** | **Property Name**   | **Property Value Type**     | **Enumerated Values** | **Value type**         | **Property Value** |
| ----------- | --------------- | ---------------------------- | -------------------- | ------------------- | --------------------------- | --------------------- | ---------------------- | ------------------ |
| IfcPavement | RIGID           | Primärväg \| PAVEMENT        | Pset_PavementCommon  | NominalThickness    | IfcNonNegativeLengthMeasure |                       | IfcPropertySingleValue | 0,7                |
|             |                 |                              |                      | NominalWidth        | IfcNonNegativeLengthMeasure |                       | IfcPropertySingleValue | 7,5                |
|             |                 |                              |                      | StructuralSlope     | IfcPositiveRatioMeasure     |                       | IfcPropertySingleValue |                    |
|             |                 |                              |                      | StructuralSlopeType | IfcLabel                    |                       | IfcPropertySingleValue | EVEN               |
| IfcPavement | RIGID           | Sekundärväg \| PAVEMENT      | Pset_PavementCommon  | NominalThickness    | IfcNonNegativeLengthMeasure |                       | IfcPropertySingleValue | 0,7                |
|             |                 |                              |                      | NominalWidth        | IfcNonNegativeLengthMeasure |                       | IfcPropertySingleValue | 6                  |
|             |                 |                              |                      | StructuralSlope     | IfcPositiveRatioMeasure     |                       | IfcPropertySingleValue |                    |
|             |                 |                              |                      | StructuralSlopeType | IfcLabel                    |                       | IfcPropertySingleValue | EVEN               |
| IfcPavement | FLEXIBLE        | Slänt\| PAVEMENT             | Pset_PavementCommon  | StructuralSlope     | IfcPositiveRatioMeasure     |                       | IfcPropertySingleValue | 0,3333 (-1:3)      |
|             |                 |                              |                      | StructuralSlopeType | IfcLabel                    |                       | IfcPropertySingleValue | EVEN               |
| IfcCourse   | USERDEFINED     | Primärväg \| Slitlager       | Pset_CourseCommon    | NominalThickness    | IfcNonNegativeLengthMeasure |                       | IfcPropertySingleValue | 0,04               |
| IfcCourse   | USERDEFINED     | Primärväg \| Bärlager 1      | Pset_CourseCommon    | NominalThickness    | IfcNonNegativeLengthMeasure |                       | IfcPropertySingleValue | 0,16               |
| IfcCourse   | USERDEFINED     | Primärväg \| Bärlager 2      | Pset_CourseCommon    | NominalThickness    | IfcNonNegativeLengthMeasure |                       | IfcPropertySingleValue | 0,08               |
| IfcCourse   | USERDEFINED     | Primärväg \| Först.lager 1   | Pset_CourseCommon    | NominalThickness    | IfcNonNegativeLengthMeasure |                       | IfcPropertySingleValue | 0,42               |
| IfcCourse   | USERDEFINED     | Sekundärväg \| Slitlager     | Pset_CourseCommon    | NominalThickness    | IfcNonNegativeLengthMeasure |                       | IfcPropertySingleValue | 0,04               |
| IfcCourse   | USERDEFINED     | Sekundärväg \| Bärlager 1    | Pset_CourseCommon    | NominalThickness    | IfcNonNegativeLengthMeasure |                       | IfcPropertySingleValue | 0,16               |
| IfcCourse   | USERDEFINED     | Sekundärväg \| Bärlager 2    | Pset_CourseCommon    | NominalThickness    | IfcNonNegativeLengthMeasure |                       | IfcPropertySingleValue | 0,08               |
| IfcCourse   | USERDEFINED     | Sekundärväg \| Först.lager 1 | Pset_CourseCommon    | NominalThickness    | IfcNonNegativeLengthMeasure |                       | IfcPropertySingleValue | 0,42               |


### Horizontal segments table

ToDo

### Vertical segments table

ToDo

### Spatial (De)Composition table

| **Parent Element** | **Parent Element Type** | **Parent Element Name** | **MinSize** | **MaxSize** | **Child Element** | **Child Element Type** | **Child Element Name**      |
| ------------------ | ----------------------- | ----------------------- | ----------- | ----------- | ----------------- | ---------------------- | --------------------------- |
| IfcProject         |                         | TRV                     | 1           | 1           | IfcSite           |                        | TRV                         |
| IfcSite            |                         | TRV                     | 1           | 1           | IfcRoad           |                        | Primärväg                   |
| IfcRoad            |                         | Primärväg               | 1           | 1           | IfcRoadPart       | ROADSEGMENT            | Primärväg \| ROADSEGMENT    |
| IfcRoad            |                         | Sekundärväg             | 1           | 1           | IfcRoadPart       | ROADSEGMENT            | Sekundärväg \| ROADSEGMENT  |
| IfcRoad            |                         | Sekundärväg             | 1           | 1           | IfcRoadPart       | INTERSECTION           | Sekundärväg \| INTERSECTION |

### Spatial Containment table

| **Spatial Element** | **Spatial Element Type** | **Spatial Element Name**    | **MinSize** | **MaxSize** | **Element**  | **Element Type** | **Element Name**        |
| ------------------- | ------------------------ | --------------------------- | ----------- | ----------- | ------------ | ---------------- | ----------------------- |
| IfcSite             |                          | TRV                         | 1           | 1           | IfcAlignment |                  | CL Primärväg            |
| IfcSite             |                          | TRV                         | 1           | 1           | IfcAlignment |                  | CL Sekundärväg          |
| IfcSite             |                          | TRV                         | 1           | 1           | IfcAlignment |                  | HVK                     |
| IfcSite             |                          | TRV                         | 1           | 1           | IfcAlignment |                  | VVK                     |
| IfcSite             |                          | TRV                         | 1           | 1           | IfcAlignment |                  | Avgränsning             |
| IfcRoadPart         |                          | Primärväg \| ROADSEGMENT    | 1           | 1           | IfcPavement  | RIGID            | Primärväg \| PAVEMENT   |
| IfcRoadPart         |                          | Sekundärväg \| ROADSEGMENT  | 1           | 1           | IfcPavement  | RIGID            | Sekundärväg \| PAVEMENT |
| IfcRoadPart         |                          | Sekundärväg \| INTERSECTION | 1           | 1           | IfcPavement  | FLEXIBLE         | Slänt \| PAVEMENT       |

### Element (De)Composition Table

| **Assembly Element** | **Assembly Type** | **Assembly Name**       | **MinSize** | **MaxSize** | **Element** | **Element Type** | **Element Name**             |
| -------------------- | ----------------- | ----------------------- | ----------- | ----------- | ----------- | ---------------- | ---------------------------- |
| IfcPavement          | RIGID             | Primärväg \| PAVEMENT   | 1           | 1           | IfcCourse   |                  | Primärväg \| Slitlager       |
| IfcPavement          | RIGID             | Primärväg \| PAVEMENT   | 1           | 1           | IfcCourse   |                  | Primärväg \| Bärlager 1      |
| IfcPavement          | RIGID             | Primärväg \| PAVEMENT   | 1           | 1           | IfcCourse   |                  | Primärväg \| Bärlager 2      |
| IfcPavement          | RIGID             | Primärväg \| PAVEMENT   | 1           | 1           | IfcCourse   |                  | Primärväg \| Först.lager 1   |
| IfcPavement          | RIGID             | Sekundärväg \| PAVEMENT | 1           | 1           | IfcCourse   |                  | Sekundärväg \| Slitlager     |
| IfcPavement          | RIGID             | Sekundärväg \| PAVEMENT | 1           | 1           | IfcCourse   |                  | Sekundärväg \| Bärlager 1    |
| IfcPavement          | RIGID             | Sekundärväg \| PAVEMENT | 1           | 1           | IfcCourse   |                  | Sekundärväg \| Bärlager 2    |
| IfcPavement          | RIGID             | Sekundärväg \| PAVEMENT | 1           | 1           | IfcCourse   |                  | Sekundärväg \| Först.lager 1 |
| IfcPavement          | FLEXIBLE          | Slänt \| PAVEMENT       | 1           | 1           | IfcCourse   |                  | H slänt \| Slitlager         |
| IfcPavement          | FLEXIBLE          | Slänt \| PAVEMENT       | 1           | 1           | IfcCourse   |                  | V slänt \| Slitlager         |
| IfcPavement          | FLEXIBLE          | Slänt \| PAVEMENT       | 1           | 1           | IfcCourse   |                  | H slänt \| Bärlager 1        |
| IfcPavement          | FLEXIBLE          | Slänt \| PAVEMENT       | 1           | 1           | IfcCourse   |                  | V slänt \| Bärlager 1        |
| IfcPavement          | FLEXIBLE          | Slänt \| PAVEMENT       | 1           | 1           | IfcCourse   |                  | H slänt \| Bärlager 2        |
| IfcPavement          | FLEXIBLE          | Slänt \| PAVEMENT       | 1           | 1           | IfcCourse   |                  | V slänt \| Bärlager 2        |
| IfcPavement          | FLEXIBLE          | Slänt \| PAVEMENT       | 1           | 1           | IfcCourse   |                  | H slänt \| Först.lager 1     |
| IfcPavement          | FLEXIBLE          | Slänt \| PAVEMENT       | 1           | 1           | IfcCourse   |                  | V slänt \| Först.lager 1     |

**NOTE**:

- when **MinSize** and **MaxSize** have the same value, it means exactly. Example: MinSize=MaxSize=1, means that the Assembly must aggregates exactly 1 Element with that Type (and Name).

### Material Association Table


| **Object** | **Object Name**              | **Material Definition** | **Material Name** |
| ---------- | ---------------------------- | ----------------------- | ----------------- |
| IfcCourse  | Primärväg \| Slitlager       | IfcMaterial             | Asphalt           |
| IfcCourse  | Primärväg \| Bärlager 1      | IfcMaterial             | Asphalt           |
| IfcCourse  | Primärväg \| Bärlager 2      | IfcMaterial             | Asphalt           |
| IfcCourse  | Primärväg \| Först.lager 1   | IfcMaterial             | Crushed stone     |
| IfcCourse  | Sekundärväg \| Slitlager     | IfcMaterial             | Asphalt           |
| IfcCourse  | Sekundärväg \| Bärlager 1    | IfcMaterial             | Asphalt           |
| IfcCourse  | Sekundärväg \| Bärlager 2    | IfcMaterial             | Asphalt           |
| IfcCourse  | Sekundärväg \| Först.lager 1 | IfcMaterial             | Crushed stone     |

### Product Geometric Representation table

| **Product**            | **Product Type** | **Product Name** | **Representation Identifier** | **Representation Type** | **Items**         |
| ---------------------- | ---------------- | ---------------- | ----------------------------- | ----------------------- | ----------------- |
| IfcAlignment           | na               | All              | Axis                          | Curve3D                 | IfcGradientCurve  |
| IfcAlignmentHorizontal | na               | All              | Axis                          | Curve2D                 | IfcCompositeCurve |
| IfcAlignmentVertical   | na               | All              | Axis                          | Curve2D                 | IfcGradientCurve  |
| IfcCourse              |                  | All              | Body                          | Brep                    | IfcFacetedBrep    |

### Product Placement table (ToDo)

| **Product**  | **Product Type** | **Product Name** | **Object Placement**         | Relative Placement Product | Relative Placement Product Type | Relative Placement Product Name |
| ------------ | ---------------- | ---------------- | ---------------------------- | -------------------------- | ------------------------------- | ------------------------------- |
| IfcAlignment |                  | A1               | IfcLocalPlacement            | IfcSite                    | na                              | ASPC.Site                       |
| IfcPavement  | FLEXIBLE         | P1               | IfcLinearPlacement at 315    | IfcAlignment               | na                              | A1                              |
| IfcPavement  | FLEXIBLE         | P2               | IfcLinearPlacement at 331,82 | IfcAlignment               | na                              | A1                              |
| IfcCourse    | USERDEFINED      | C1               | IfcLocalPlacement            | IfcPavement                | na                              | P1                              |
| IfcCourse    | USERDEFINED      | C2               | IfcLocalPlacement            | IfcPavement                | na                              | P1                              |
| IfcCourse    | USERDEFINED      | C3               | IfcLocalPlacement            | IfcPavement                | na                              | P1                              |
| IfcCourse    | USERDEFINED      | C4               | IfcLocalPlacement            | IfcPavement                | na                              | P1                              |
| IfcCourse    | USERDEFINED      | C5               | IfcLocalPlacement            | IfcPavement                | na                              | P1                              |
| IfcCourse    | USERDEFINED      | C6               | IfcLocalPlacement            | IfcPavement                | na                              | P1                              |
| IfcCourse    | USERDEFINED      | C7               | IfcLocalPlacement            | IfcPavement                | na                              | P2                              |
| IfcCourse    | USERDEFINED      | C8               | IfcLocalPlacement            | IfcPavement                | na                              | P2                              |
| IfcCourse    | USERDEFINED      | C9               | IfcLocalPlacement            | IfcPavement                | na                              | P2                              |
| IfcCourse    | USERDEFINED      | C10              | IfcLocalPlacement            | IfcPavement                | na                              | P2                              |
| IfcCourse    | USERDEFINED      | C11              | IfcLocalPlacement            | IfcPavement                | na                              | P2                              |
| IfcCourse    | USERDEFINED      | C12              | IfcLocalPlacement            | IfcPavement                | na                              | P2                              |

## Drawings (Visualisations) (ToDo)

The following Drawings and visualisations describe the test case dataset to be modelled and certified.

| Filename | Description |
| -------- | ----------- |
|          |             |


## Supporting files

| Filename              | Description      |
| --------------------- | ---------------- |
| [IFC file](./trv.ifc) | Example IFC file |
|                       |                  |
|                       |                  |
|                       |                  |
|                       |                  |
