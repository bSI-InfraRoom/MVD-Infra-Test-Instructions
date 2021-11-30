# Test instructions


|       Test Case title     | Code | Abbreviation | Author | Data Owner |
|:-------------------------:|:----:|:------------:|:------:| :---------:|
|  Aggregate structures + Track. Pavement and Course (ballast) + Cant | E2b1 | ASTPC | Evandro Alfieri | RFI |

## Summary (intent)

<details><summary>click to expand</summary> 

This test case uses some elements of the railway track domain to test the following capabilities:
- Object grouping
- Object classification via external reference (i.e., bSDD)
- Object typing
- Object decomposition (assemblies)
- Project Global Positioning
- Railway spatial structure
- Railway alignment (with cant)
- Linear placement along alignment
- Properties of objects

The business context for the test is provided by a 2km portion of railway line, including: 2 alignments, track substructure and superstructure, and related products.  

### Test instructions (**high-level**, <ins>**not necessarily in this order**</ins>)

1. Model project breakdown structure (spatial structure)
1. Model alignment(s)
1. Geo-reference model
1. Model track objects type and objects (ballast, rails, sleepers, etc.)
1. Group objects, assemble objects
1. Classify objects
1. Model properties of objects/object types
1. Assign objects to project breakdown

</details>

---

## Itemised Roots

<details><summary>click to expand</summary> 

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary> 

  - IfcProject
  - IfcSite
  - IfcRailway
  - IfcFacilityPart
  - IfcGroup
  - IfcElementAssembly
  - IfcActuator
  - IfcRail
  - IfcTrackElement
  - IfcFastener
  - IfcCourse

  - IfcRelAggregates
  - IfcRelAssignsToGroup
  - IfcRelContainedInSpatialStructure
  - IfcRelReferencedInSpatialStructure
  - IfcRelDefinesByType
  - IfcRelDefinesByProperty
  - IfcRelNests

  - IfcAlignemnt
  - IfcAlignmentHorizontal
  - IfcAlignmentVertical
  - IfcAlignmentCant
  - IfcAlignmentSegment
  - IfcAlignmentHorizontalSegment
  - IfcAlignmentVerticalSegment
  - IfcAlignmentCantSegment

  - IfcContext
  - IfcRelAssociatesClassification
  - IfcClassification
  - IfcClassificationReference

  - IfcTypeObject
  - IfcActuatorType
  - IfcCourseType

  - IfcPropertySet
  - IfcPropertySingleValue
  - IfcPropertyEnumeratedValue

  - ... (to be continued)

</details>

<details><summary>Concept Templates</summary> 

  - Object Assignment
     - Group Assignment
  - Object Association
     - Classification Association
  - Object Attributes
     - Object Predefined Type
  - Object Composition
     - Alignment Decomposition
     - Element Decomposition
     - Spatial Decomposition
  - Object Connectivity
     - Spatial Service Connectivity (or better *Group Spatial Connectivity*, not yet present in documentation)
     - Spatial Containment
  - Object definition
     - Object Typing
     - Property Sets for Objects
     - Property Sets for Types
  - Product Shape
     - `I need help here`
     - Product Geometric Representation
     - Alignment Geometry
     - Alignment Geometry Gradient
     - ... (to be continued)
  - Project Context
     - Project Classification Information
     - Project Declaration
     - Project Global Positioning
     - Project Representation Context
     - Project Units
</details>

</details>

---

## Variations

<details><summary>click to expand</summary>

The Following occurrence variations need to be checked and certified in relation to the targeted entities and concept templates:

- Entity_01 - *description of variation*
- Entity_02 - *description of variation*

</details>

## Usages

<details><summary>click to expand</summary> 

The following itemised restrictions and constraints shall be placed on IFC Entities & Concept Templates:

:construction: under construction :construction:

- IfcSomething
    - *Constraint*

The Test case requires the following additional checks related to Model Geometry:

- *Correspondence between the business-logic and the geometry parts for all segments*
- *Tangential continuity of alignemnt segments. Tolerance of ... millimetres*
- ... (to be continued)

</details>

---

## Model Dataset

<details open><summary>click to expand</summary> 

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. Form more details on each item see [Dataset description](Dataset/README.md).

| ID | Filename                                                        | Type (format)  | Description                               |
|----|-----------------------------------------------------------------|----------------|-------------------------------------------|
|    | *filename + link*                                               | csv            | Alignment parameters for horizontal segments |
|    | *filename + link*                                               | csv            | Alignment parameters for vertical segments) |
|    | *filename + link*                                               | csv            | Alignment parameters for cant segments |
|    | *filename + link*                                               | LandXML        | Alignment LandXML file, not including cant  |
|    | *filename + link*                                               | dwg            | Alignment dwg file, not including cant  |
|    | [Line_layout](./Line_layout.jpg)                                | figure (jpg)   | Schematic layout of the test case railway line |
|    | [Objects overview](./ObjectsOverview.png)         | diagram (png)  | Objects overview: a diagram + table describing the main to be used for the test case |
|    | *filename + link*                                               | drawing (pdf)  | Cross section example |
|    | *filename + link*                                               | drawing (dwg)  | Cross section example |
|    | *filename + link*                                               | drawing (PDF)  | Turnout drawing to be used as example |


</details>

---

## Expected Results

<details><summary>click to expand</summary> 

Considering the aim of this test, the expected results are:

:construction: under construction :construction:

1. N. 1 IFC file containing the information as requested
2. Screen-shot of ...

</details>

---

## Validation criteria
:warning: <ins>For this test case to be considered passed **all capabilities** listed in this section shall be verified, with no exception.</ins> :warning:

:construction: under construction :construction:

<details><summary>General</summary>

- All the concept templates must be correctly used
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file

</details>

<details><summary>Railway alignment (with cant)</summary> 

For the **Railway alignment (with cant)** capability, the test is considered passed if **all** the following validation criteria are satisfied.

| **ID** | **CRITERIA**                                                     | **VALUE**                                   | **COMMENT**                |
|--------|------------------------------------------------------------------|---------------------------------------------|----------------------------|
|        | Alignments contained in file                                     | 2                                           |                            |
|        | Component for Alignment 1                                        | H+V+C                                       |                            |
|        | Component for Alignment 2                                        | H+V                                         |                            |
|        | The horizontal (H) layout is made only by these type of segments | "straight line, circular arc, clothoid"     |                            |
|        | The vertical (V) layout is made only by these type of segments   | "straight line, circular arc"               |                            |
|        | The cant (C) layout is made only by these type of segments       | "constant straight line, linear transition" |                            |
|        | Value of the *RailHeadDistance* along the entire alignment       | 1500 mm                                     | See notes below for detail |
|        | Unit of measure for all distances                                | **meter** (m)                               | As provided in the dataset |
|        | Unit of measure all angles                                       | **radian** (π)                              | As provided in the dataset |
|        | Required precision for **distances**                             | "minimum 4 decimal places (0,0001)"         |                            |
|        | Required precision for **angles** and **slope**                  | "minimum 6 decimal places (0,000001)"       |                            |

NOTES:
-	The *RailHeadDistance* (blue line in the figure below) is a normalized value used to compute the angle of cant. RFI uses 1500 mm for a track gauge of 1435 mm

![alt text](Dataset/CantFromLowerRail.png)

<details><summary> Alignment 1 </summary>

| ID | CRITERIA                                                           | VALUE          |
|----|--------------------------------------------------------------------|----------------|
|    | Starting point Horizontal  - Mileage (pk)                          | 0+510.011      |
|    | Starting point Horizontal  - DistAlong                             | 0.000          |
|    | Starting point Horizontal  - X                                     | 451,296.6992   |
|    | Starting point Horizontal  - Y                                     | 4,538,798.8214 |
|    | Starting point Vertical  - Mileage                                 | 0+510.011      |
|    | Starting point Vertical  - Z                                       | 36.76035       |
|    | Ending point Horizontal  - Mileage (pk)                            | 47+271.7631    |
|    | Ending point Horizontal  - DistAlong                               | 46,761.7521    |
|    | Ending point Horizontal  - X                                       | 479,666.2177   |
|    | Ending point Horizontal  - Y                                       | 4,554,675.8253 |
|    | Ending point Vertical  - Mileage                                   | 47+271.7631    |
|    | Ending point Vertical  - Z                                         | 121.0179       |
|    | Total 2D length of alignment (horizontal projection)               | 46,761.7521    |
|    | Total 3D length of alignment                                       | 46,765.4520    |
|    | Hight difference between start and end point of alignment 3D curve | -84.2575       |

</details>

<details><summary> Alignment 2 </summary>

| ID | CRITERIA                                                           | VALUE          |
|----|--------------------------------------------------------------------|----------------|
|    | Starting point Horizontal  - Mileage (pk)                          | 0+510.011      |
|    | Starting point Horizontal  - DistAlong                             | 0.000          |
|    | Starting point Horizontal  - X                                     | 451,296.6992   |
|    | Starting point Horizontal  - Y                                     | 4,538,798.8214 |
|    | Starting point Vertical  - Mileage                                 | 0+510.011      |
|    | Starting point Vertical  - Z                                       | 36.76035       |
|    | Ending point Horizontal  - Mileage (pk)                            | 47+271.7631    |
|    | Ending point Horizontal  - DistAlong                               | 46,761.7521    |
|    | Ending point Horizontal  - X                                       | 479,666.2177   |
|    | Ending point Horizontal  - Y                                       | 4,554,675.8253 |
|    | Ending point Vertical  - Mileage                                   | 47+271.7631    |
|    | Ending point Vertical  - Z                                         | 121.0179       |
|    | Total 2D length of alignment (horizontal projection)               | 46,761.7521    |
|    | Total 3D length of alignment                                       | 46,765.4520    |
|    | Hight difference between start and end point of alignment 3D curve | -84.2575       |

</details>

</details>

<details><summary>Object grouping</summary>

For the **Object grouping** capability, the test is considered passed if **all** the following validation criteria are satisfied.

The validation procedure must verify that a group of the requested type is grouping (via `IfcRelAssignsToGroup`) exactly a given number of objects of the requested type, no more and no less.

- **Concept Template**: Group Assignment
- **Usage** (if existing): NA

| Group    | Group Type                          | Minimum | Maximum | Object             | Object Type          |
|----------|-------------------------------------|---------|---------|--------------------|----------------------|
| IfcGroup | Binari di corsa (Contenitore)       | 1       | 1       | IfcFacilityPart    | TRACKSTRUCTURE       |
| IfcGroup | Deviatoi/Intersezioni (Contenitore) | 1       | 1       | IfcActuator        | Manovra deviatoio    |
| IfcGroup | Deviatoi/Intersezioni (Contenitore) | 1       | 1       | IfcElementAssembly | TURNOUTPANEL         |
| IfcGroup | Massicciata (Contenitore)           | 2       | 2       | IfcCourse          | BALLASTBED           |
| IfcGroup | Rotaie (Contenitore)                | 3       | 3       | IfcGroup           | Segmento di rotaia   |
| IfcGroup | Segmento di rotaia                  | 2       | 2       | IfcRail            | RAIL                 |
| IfcGroup | Traverse (Contenitore)              | 3       | 3       | IfcGroup           | Segmento di traverse |
| IfcGroup | Segmento di traverse                | 1       |         | IfcTrackElement    | SLEEPER              |

NOTE:
- for typing of groups refer to the Validation criteria of the **Object typing** capability
- when **Minimum** and **Maximum** have the same value, it means exactly. Example: Minimum=Maximum=2, means that the group must group exactly 2 objects of the requested type.
- when **Maximum** is empty, it means unlimited. Example: Minimum=1; Maximum=empty, means that the group must group 1 or more elements of the requested type.

</details>

<details><summary>Object typing</summary>

For the **Object typing** capability, the test is considered passed if **all** the following validation criteria are satisfied.

The validation procedure must verify that an IFC entity type with the given Name is typing (via `IfcRelDefinesByType`) exactly a given number of objects of the requested Name, no more and no less.

- **Concept Template**: Object Typing
- **Usage** (if existing): NA

| Entity Type     | Entity Type Name                    | Minimum | Maximum | IfcObject       | IfcObject Name                      |
|-----------------|-------------------------------------|---------|---------|-----------------|-------------------------------------|
| IfcTypeObject   | Binari di corsa (Contenitore)       | 1       | 1       | IfcGroup        | Binari di corsa di Foligno          |
| IfcTypeObject   | Deviatoi/Intersezioni (Contenitore) | 1       | 1       | IfcGroup        | Deviatoi                            |
| IfcTypeObject   | Massicciata (Contenitore)           | 1       | 1       | IfcGroup        | Massicciata                         |
| IfcTypeObject   | Rotaie (Contenitore)                | 1       | 1       | IfcGroup        | Rotaie                              |
| IfcTypeObject   | Traverse (Contenitore)              | 1       | 1       | IfcGroup        | Traverse                            |
| IfcActuatorType | Manovra deviatoio                   | 1       | 1       | IfcActuator     | Cassa di manovra CM04               |
| IfcCourseType   | Segmento di massicciata             | 1       | 1       | IfcCourse       | Segmento di massicciata M01         |
| IfcCourseType   | Segmento di massicciata             | 1       | 1       | IfcCourse       | Segmento di massicciata M02         |
| IfcTypeObject   | Segmento di rotaia                  | 1       | 1       | IfcGroup        | Segmento di rotaia R01              |
| IfcTypeObject   | Segmento di rotaia                  | 1       | 1       | IfcGroup        | Segmento di rotaia R02              |
| IfcTypeObject   | Segmento di rotaia                  | 1       | 1       | IfcGroup        | Segmento di rotaia R03              |
| IfcTypeObject   | Segmento di traverse                | 1       | 1       | IfcGroup        | Segmento di traverse T01            |
| IfcTypeObject   | Segmento di traverse                | 1       | 1       | IfcGroup        | Segmento di traverse T02            |
| IfcTypeObject   | Segmento di traverse                | 1       | 1       | IfcGroup        | Segmento di traverse T03            |
| IfcTypeObject   | Binari di corsa                     | 1       | 1       | IfcFacilityPart | Binario IV dispari - Orte Falconara |

NOTE:
- when **Minimum** and **Maximum** have the same value, it means exactly. Example: Minimum=Maximum=1, means that the entity type must type exactly 1 object with that Name.

</details>

<details><summary>Object decomposition (assemblies)</summary>

:construction: under construction :construction:

- **Concept Template**: Element Decomposition
- **Usage** (if existing): NA

| Assembly           | Assembly Type | Minimum | Maximum | Element         | Element Type |
|--------------------|---------------|---------|---------|-----------------|--------------|
| IfcElementAssembly | TURNOUTPANEL  | 1       | 1       | IfcFastener     | WELD         |
| IfcElementAssembly | TURNOUTPANEL  | 1       | 1       | IfcTrackElement | FROG         |
| IfcElementAssembly | TURNOUTPANEL  | 1       | 10      | IfcRail         | RAIL         |
| IfcElementAssembly | TURNOUTPANEL  | 1       | 2       | IfcRail         | CHECKRAIL    |
| IfcElementAssembly | TURNOUTPANEL  | 52      | 52      | IfcTrackElement | SLEEPER      |

</details>

<details><summary>Object classification via external reference (i.e., bSDD)</summary>

| **ID** | **CRITERIA**                            | **VALUE** / **COMMENT**               |
|--------|-----------------------------------------|---------------------------------------|
|        | ABC                                     | 0                                     |

</details>

<details><summary>Project Global Positioning</summary>

| **ID** | **CRITERIA**                            | **VALUE** / **COMMENT**               |
|--------|-----------------------------------------|---------------------------------------|
|        | ABC                                     | 0                                     |

</details>

<details><summary>Railway spatial structure</summary>

:construction: under construction :construction:

- **Concept Template**: Spatial Decomposition
- **Usage** (if existing): NA

| Parent Element | Parent Element Type | Minimum | Maximum | Child Element   | Child Element Type |
|----------------|---------------------|---------|---------|-----------------|--------------------|
| IfcSite        |                     | 1       | 1       | IfcRailway      | Località           |
| IfcRailway     | Località            | 1       | 1       | IfcFacilityPart | TRACKSTRUCTURE     |

</details>

<details><summary>Spatial containment</summary>

:construction: under construction :construction:

- **Concept Template**: Spatial Containment
- **Usage** (if existing): NA

| Spatial Element | Spatial Element Type | Minimum | Maximum | Element            | Element Type      |
|-----------------|----------------------|---------|---------|--------------------|-------------------|
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcActuator        | Manovra deviatoio |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcElementAssembly | TURNOUTPANEL      |
| IfcFacilityPart | TRACKSTRUCTURE       | 2       | 2       | IfcCourse          | BALLASTBED        |
| IfcFacilityPart | TRACKSTRUCTURE       | 6       | 6       | IfcRail            | RAIL              |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | TBD     | IfcTrackElement    | SLEEPER           |
| IfcSite         |                      | 2       | 2       | IfcAlignment       |                   |

</details>

<details><summary>Spatial reference</summary>

:construction: under construction :construction:

- **Concept Template**: :warning: Spatial Service Connectivity (or better *Group Spatial Connectivity*, not yet present in documentation) :warning:
- **Usage** (if existing): NA

| Spatial Element | Spatial Element Type | Minimum | Maximum | Product or Group | Product Type or Group Type          |
|-----------------|----------------------|---------|---------|------------------|-------------------------------------|
| IfcRailway      | Località             | 1       | 1       | IfcGroup         | Binari di corsa (Contenitore)       |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Deviatoi/Intersezioni (Contenitore) |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Massicciata (Contenitore)           |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Rotaie (Contenitore)                |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Traverse (Contenitore)              |

</details>

<details><summary>Linear placement along alignment</summary>

| **ID** | **CRITERIA**                            | **VALUE** / **COMMENT**               |
|--------|-----------------------------------------|---------------------------------------|
|        | ABC                                     | 0                                     |

</details>

<details><summary>Properties of objects and object types</summary>

:construction: under construction :construction:

- **Concept Template**: Property Sets for Objects, Property Sets for Types
- **Usage** (if existing): NA

| Entity          | Entity Type          | PropertySet Name | Property Name           | Property Value Type | List Of Values                                       | IfcSimpleProperty subtype  |
|-----------------|----------------------|------------------|-------------------------|---------------------|------------------------------------------------------|----------------------------|
| IfcFacilityPart | TRACKSTRUCTURE       | RFI_S16000       | Binario                 | IFCLABEL            | Pari, Dispari, Unico                                 | IfcPropertyEnumeratedValue |
| IfcFacilityPart | TRACKSTRUCTURE       | RFI_S16000       | Codice binario SAS      | IFCLABEL            |                                                      | IfcPropertySingleValue     |
| IfcFacilityPart | TRACKSTRUCTURE       | RFI_S16000       | n. deviatoi elettrici   | IFCINTEGER          |                                                      | IfcPropertySingleValue     |
| IfcFacilityPart | TRACKSTRUCTURE       | RFI_S16000       | Profilo manutentivo L94 | IFCLABEL            | <=40 t/g, >100 t/g, 40< t/g <=100 | IfcPropertyEnumeratedValue |
| IfcFacilityPart | TRACKSTRUCTURE       | RFI_S16000       | Binario elettrificato   | IFCLOGICAL          |                                                      | IfcPropertySingleValue     |
| IfcTrackElement | SLEEPER              | ???              |                         |                     |                                                      |                            |
| IfcGroup        | Segmento di traverse | ???              |                         |                     |                                                      |                            |




</details>

