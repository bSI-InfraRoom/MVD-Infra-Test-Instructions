# Test instructions

[![See GH Pages publication for this test](https://img.shields.io/badge/GitHub%20Pages-Test%20Case%20documentation-blue)](https://evandroalfieri.github.io/MVD-Infra-Test-Instructions/E2b-ASTPC/)

| Documentation Code   | Title                                                              | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|--------------------------------------------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E2b_ASTPC | Aggregate structures + Track. Pavement and Course (ballast) + Cant | E2b           | ASTPC     | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |

## Summary (intent)

This test case uses one unique dataset to progressively asses multiple IFC 4.3 capabilities. **export**

The dataset is represented by a short portion of railway line (800 m), including: 2 alignments, and the elements of the railway track domain listed in the *Itemised Roots* paragraph [below](#Itemised-Roots).

<img src="Dataset/LineLayout.svg" height="400"/>

Starting from this dataset, the following capabilities will be tested in 3 steps:

- Step 1: 
   - Railway alignment (with cant)
- Step 2:
   - Local placement & Linear placement along alignment
   - Railway spatial structure
   - Object decomposition (assemblies)
   - (?) Object typing
   - Project Global Positioning
- Step 3:
  - Object grouping
  - Object classification via external reference (i.e., bSDD)
  - Properties of objects

**High-level test instructions**

Coherently to the above steps, also the production of the IFC file subject to test can be broken down into three moments:

- Step 1:
   1. Model alignment(s)

- Step 2:
   1. Model project breakdown structure (spatial structure)
   1. Model and position track object (course, ballast, rails, sleepers, etc.) and related types
   1. Assemble objects
   1. Assign objects to project breakdown
   1. Geo-reference model

- Step 3:
   1. Group objects
   1. Classify objects
   1. Model properties of objects/object types

The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

:warning: <ins> This is a test-driven process: refer to the **Validation Criteria** to understand what is required by the test</ins> :warning: 

---

## Itemised Roots

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

**NOTE**: These entities represent a test-specific subset of the wider AbRV_E2b exchange, hence of the overall AbRV MVD. <ins>**By no means the scope of the test shall be used to define the scope of the exchange, nor of the MVD**</ins>

- Model setup:
   1. IfcProject
   1. IfcSite
   1. IfcRailway
   1. IfcFacilityPart
- Alignment:
   1. IfcAlignment
   1. IfcAlignmentHorizontal
   1. IfcAlignmentVertical
   1. IfcAlignmentCant
   1. IfcAlignmentSegment
   1. IfcAlignmentHorizontalSegment
   1. IfcAlignmentVerticalSegment
   1. IfcAlignmentCantSegment
- Track domain physical products:
   1. IfcRail
   1. IfcTrackElement
   1. IfcFastener
   1. IfcActuator / IfcActuatorType
   1. IfcCourse / IfcCourseType
   1. IfcElementAssembly
- Other test-specific entities:
   1. IfcGroup
   1. IfcClassification
   1. IfcClassificationReference


</details>

<details><summary>Concept Templates</summary> 

- Object Assignment
   - Group Assignment
- Object Association
   - Classification Association
- Object Attributes
   - Object Predefined Type
- Object Composition
   - Alignment Layout
   - Element Decomposition
   - Spatial Decomposition
- Object Connectivity
   - Group Spatial Connectivity
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

</details>

---

## Model Dataset

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. <ins> Form more details on each item see [Dataset description](Dataset/README.md).</ins>

| Filename                | Type (format)  | Description                               |
|-------------------------|----------------|-------------------------------------------|
| Line_layout             | figure (jpg)   | Schematic line layout of the test case |
| TrackCrossSection       | drawing (png)  | Track cross section to be used as example |
| SleeperPlacement        | figure (png)   | Information on how to position sleepers along the alignment |
| *under production*      | csv            | Alignment parameters for horizontal segments |
| *under production*      | csv            | Alignment parameters for vertical segments |
| *under production*      | csv            | Alignment parameters for cant segments |
| *under production*      | LandXML        | Alignment LandXML file, not including cant  |
| *under production*      | dwg            | Alignment dwg file, not including cant  |
| ObjectsOverview         | diagram (png)  | Objects overview: a diagram + table describing the main to be used for the test case |
| FS60UNI_R.250_TG.0.092  | drawing (svg)  | Turnout drawing to be used as example. **The objective of the test IS NOT to reproduced the turnout** 
| SimplifiedTurnout       | figure (png)   | Simplified turnout scheme. **The objective of the test IS NOT to reproduced the turnout** |

---

## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2b_ASTPC_AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet usefull to illustrate test results are:
- Screen-shot of ...
- CSV export of ...

---

## Validation criteria
:warning: <ins>For this test case to be considered passed **all capabilities** listed in this section shall be verified, with no exception.</ins> :warning:

:construction: under construction :construction:

<details><summary>General</summary>

:construction: under construction :construction:

- All the concept templates must be correctly used
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file

Other global settings:

| **ID**  | **CRITERIA**                                                     | **VALUE**                                   | **COMMENT**                |
|---------|------------------------------------------------------------------|---------------------------------------------|----------------------------|
| GENE_01 | Unit of measure for all distances                                | **meter** (m)                               | As provided in the dataset |
| GENE_02 | Unit of measure all angles                                       | **radian** (π)                              | As provided in the dataset |
| GENE_03 | Required precision for **distances**                             | "minimum 4 decimal places (0,0001)"         |                            |
| GENE_04 | Required precision for **angles** and **slope**                  | "minimum 6 decimal places (0,000001)"       |                            |

</details>

---

### Step 1: Alignment with cant

<details><summary>Railway alignment (with cant)</summary> 

- **Concept Template**: Alignment Layout
- **Usage** (if existing): NA
> **Acceptance criteria**: For the **Railway alignment (with cant)** capability, the test is considered passed if **all** the following validation criteria are satisfied.

| **ID**  | **CRITERIA**                                                     | **VALUE**                                   | **COMMENT**                |
|---------|------------------------------------------------------------------|---------------------------------------------|----------------------------|
| ALIG_01 | Alignments contained in file                                     | 2                                           |                            |
| ALIG_02 | Component for Alignment 1: Primary route                         | 1 horizontal, 1 vertical, 1 cant            |                            |
| ALIG_03 | Component for Alignment 2: Diverted route                        | 1 horizontal, 1 vertical, 1 cant            |                            |
| ALIG_04 | The horizontal (H) layout is made only by these type of segments | straight line, circular arc, clothoid       |                            |
| ALIG_05 | The vertical (V) layout is made only by these type of segments   | straight line, circular arc                 |                            |
| ALIG_06 | The cant (C) layout is made only by these type of segments       | constant straight line, linear transition   |                            |
| ALIG_07 | Value of the *RailHeadDistance* along the entire alignment       | 1500 mm                                     | See notes below for detail |
| ALIG_08 | Semantic description of segments corresponds to their geometry   | NA                                          | RDF tools can do this      |
| ALIG_09 | Tangential continuity of all segments is verified, tolerance = 0, 00000001 |                                   | RDF tools can do this      |


NOTE:
-	The *RailHeadDistance* (blue line in the figure below) is a normalized value used to compute the angle of cant. RFI uses 1500 mm for a track gauge of 1435 mm

   <img src="Dataset/CantFromLowerRail.png" height="300"/>

<details><summary> Alignment 1: Primary route </summary>

| ID      | CRITERIA                                                            | VALUE        |
|---------|---------------------------------------------------------------------|--------------|
| ALIG_10 | Horizontal Starting point Mileage (pk)                              | 0+000        |
| ALIG_11 | Horizontal Starting point DistAlong                                 | 0.0000       |
| ALIG_12 | Horizontal Starting point X                                         | 452413.9199  |
| ALIG_13 | Horizontal Starting point Y                                         | 4539456.4011 |
| ALIG_14 | Vertical Starting point Mileage                                     | 0+000        |
| ALIG_15 | Vertical Starting point Z                                           | 5.0000       |
| ALIG_16 | Horizontal Ending point Mileage (pk)                                | 0+876.3682   |
| ALIG_17 | Horizontal Ending point DistAlong                                   | 876.3682     |
| ALIG_18 | Horizontal Ending point X                                           | 453202.5241  |
| ALIG_19 | Horizontal Ending point Y                                           | 4539831.9287 |
| ALIG_20 | Vertical Ending point Mileage                                       | 0+876.3682   |
| ALIG_21 | Vertical Ending point Z                                             | 2.0000       |
| ALIG_22 | Total 2D length of alignment (horizontal projection)                | 876.3682     |
| ALIG_23 | Total 3D length of alignment                                        | 876.3819     |
| ALIG_24 | Height difference between start and end point of alignment 3D curve | -3.0000      |

</details>

<details><summary> Alignment 2: Diverted route </summary>

| ID      | CRITERIA                                                            | VALUE        |
|---------|---------------------------------------------------------------------|--------------|
| ALIG_10 | Horizontal Starting point Mileage (pk)                              | 0+000        |
| ALIG_11 | Horizontal Starting point DistAlong                                 | 0.0000       |
| ALIG_12 | Horizontal Starting point X                                         | 452460.8898  |
| ALIG_13 | Horizontal Starting point Y                                         | 4539473.5425 |
| ALIG_14 | Vertical Starting point Mileage                                     | 0+000        |
| ALIG_15 | Vertical Starting point Z                                           | 5.0000       |
| ALIG_16 | Horizontal Ending point Mileage (pk)                                | 0+828.0965   |
| ALIG_17 | Horizontal Ending point DistAlong                                   | 828.0965     |
| ALIG_18 | Horizontal Ending point X                                           | 453208.8311  |
| ALIG_19 | Horizontal Ending point Y                                           | 4539818.3191 |
| ALIG_20 | Vertical Ending point Mileage                                       | 0+828.0965   |
| ALIG_21 | Vertical Ending point Z                                             | 2.0000       |
| ALIG_22 | Total 2D length of alignment (horizontal projection)                | 828.0965     |
| ALIG_23 | Total 3D length of alignment                                        | 828.1099     |
| ALIG_24 | Height difference between start and end point of alignment 3D curve | -3.0000      |

</details>

</details>

---

### Step 2: Placement, spatial structure and object decomposition, (TBD) global positioning

<details><summary>Spatial decomposition</summary>

- **Concept Template**: Spatial Decomposition
- **Usage** (if existing): NA
> **Acceptance criteria**: For the **Spatial decomposition** capability, the test is considered passed if **all** the following validation criteria are satisfied.
>
> The validation procedure must verify that a Parent Element of the requested type aggregates (via `IfcRelAggregates`) exactly a given number of Child Elements of the requested type, no more and no less.

| Parent Element | Parent Element Type | Minimum | Maximum | Child Element   | Child Element Type |
|----------------|---------------------|---------|---------|-----------------|--------------------|
| IfcSite        |                     | 1       | 1       | IfcRailway      | Località           |
| IfcRailway     | Località            | 1       | 1       | IfcFacilityPart | TRACKSTRUCTURE     |

</details>

<details><summary>Spatial containment</summary>

- **Concept Template**: Spatial Containment
- **Usage** (if existing): NA
> **Acceptance criteria**: For the **Spatial containment** capability, the test is considered passed if **all** the following validation criteria are satisfied.
>
> The validation procedure must verify that a Spatial Element of the requested type contains (via `IfcRelContainedInSpatialStructure`) exactly a given number of Elements of the requested type, no more and no less.

| Spatial Element | Spatial Element Type | Minimum | Maximum | Element            | Element Type      |
|-----------------|----------------------|---------|---------|--------------------|-------------------|
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcActuator        | Manovra deviatoio |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcElementAssembly | TURNOUTPANEL      |
| IfcFacilityPart | TRACKSTRUCTURE       | 2       | 2       | IfcCourse          | BALLASTBED        |
| IfcFacilityPart | TRACKSTRUCTURE       | 6       | 6       | IfcRail            | RAIL              |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | TBD     | IfcTrackElement    | SLEEPER           |
| IfcSite         |                      | 2       | 2       | IfcAlignment       |                   |

</details>

<details><summary>Object decomposition (assemblies)</summary>

- **Concept Template**: Element Decomposition
- **Usage** (if existing): NA
> **Acceptance criteria**: For the **Object decomposition** capability, the test is considered passed if **all** the following validation criteria are satisfied.
>
> The validation procedure must verify that an assembly of the requested type aggregates (via `IfcRelAggregates`) exactly a given number of elements of the requested type, no more and no less.

| Assembly           | Assembly Type | Minimum | Maximum | Element         | Element Type |
|--------------------|---------------|---------|---------|-----------------|--------------|
| IfcElementAssembly | TURNOUTPANEL  | 1       | 1       | IfcFastener     | WELD         |
| IfcElementAssembly | TURNOUTPANEL  | 1       | 1       | IfcTrackElement | FROG         |
| IfcElementAssembly | TURNOUTPANEL  | 1       | 10      | IfcRail         | RAIL         |
| IfcElementAssembly | TURNOUTPANEL  | 1       | 2       | IfcRail         | CHECKRAIL    |
| IfcElementAssembly | TURNOUTPANEL  | 52      | 52      | IfcTrackElement | SLEEPER      |

NOTE:
- when **Minimum** and **Maximum** have the same value, it means exactly. Example: Minimum=Maximum=2, means that the assembly must aggregates exactly 2 elements of the requested type.
- when **Maximum** is empty, it means unlimited. Example: Minimum=1; Maximum=empty, means that the assembly must aggregate 1 or more elements of the requested type.

</details>

<details><summary>Local placement & Linear placement along alignment</summary>

:construction: under construction :construction:

- **Concept Template**: Product Linear Placement, Product Local Placement
- **Usage** (if existing): NA
> **Acceptance criteria**: For the **Linear placement long alignment** capability, the test is considered passed if **all** the following validation criteria are satisfied.
>
> The validation procedure must verify that ...


</details>

<details><summary>Project Global Positioning</summary>

- **Concept Template**: Project Global Positioning
- **Usage** (if existing): NA
> **Acceptance criteria**: For the **Project Global Positioning** capability, the test is considered passed if **all** the following validation criteria are satisfied.
>
> The validation procedure must verify that:
> - `IfcMapConversion` entity is used to transform the local engineering coordinate system, often called world coordinate system (WCS), into the coordinate reference system of the underlying map.
> - `IfcProjectedCRS` entity is used for representing the coordinate reference system of the map to which the map translation of the local engineering coordinate system of the engineering project relates.
> Below are the expected values for the two entities.
> 

`IfcMapConversion`

| #  | Attribute        | Value / Instructions                        |
|----|------------------|---------------------------------------------|
| 1  | SourceCRS        | Points to IfcGeometricRepresentationContext |
| 2  | TargetCRS        | Points to IfcProjectedCRS (see below)       |
| 3  | Eastings         | 0                                           |
| 4  | Northings        | 0                                           |
| 5  | OrthogonalHeight | 0                                           |
| 6  | XAxisAbscissa    | 1                                           |
| 7  | XAxisOrdinate    | 0                                           |
| 8  | Scale            | 1                                           |
| 9  | ScaleY           | 1                                           |
| 10 | ScaleZ           | 1                                           |

`IfcProjectedCRS`

| # | Attribute     | Value / Instructions                        |
|---|---------------|---------------------------------------------|
| 1 | Name          | 'EPSG:3065'                                 |
| 2 | Description   | 'Istituto Geografico Militare 1995 (IGM95)' |
| 3 | GeodeticDatum | 'EPSG:3065'                                 |
| 4 | VerticalDatum |  $                                          |
| 5 | MapProjection | 'UTM'                                       |
| 6 | MapZone       | '33N'                                       |
| 7 | MapUnit       | $                                           |

</details>

---

### Step 3: Grouping, classification, properties, typing

<details><summary>Object grouping</summary>

- **Concept Template**: Group Assignment
- **Usage** (if existing): NA
> **Acceptance criteria**: For the **Object grouping** capability, the test is considered passed if **all** the following validation criteria are satisfied.
>
> The validation procedure must verify that a group of the requested type is grouping (via `IfcRelAssignsToGroup`) exactly a given number of objects of the requested type, no more and no less.

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

- **Concept Template**: Object Typing
- **Usage** (if existing): NA
> **Acceptance criteria**: For the **Object typing** capability, the test is considered passed if **all** the following validation criteria are satisfied.
>
> The validation procedure must verify that an IFC entity type with the given Name is typing (via `IfcRelDefinesByType`) exactly a given number of objects of the requested Name, no more and no less.

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

<details><summary>Object classification via external reference (i.e., bSDD)</summary>

- **Concept Template**: Classification Association
- **Usage** (if existing): NA
> **Acceptance criteria**: For the **Object classification via external reference** capability, the test is considered passed if **all** the following validation criteria are satisfied.
>
> The validation procedure must verify that all the sleepers (IfcTrackElement.SLEEPER) are to be classified using the correspondent classification inside the bSDD (buildingSMART Data Dictionary). The example below shows how the classification is expected to be done.

Given two sleepers

> `#21 = IFCTRACKELEMENT('0$kRFU7b50rP3_$BI9iljk', #1, 'Sleeper Z20#0001', 'Sleeper', $, #368035, #368038, $, .SLEEPER.);`
>
> `#22 = IFCTRACKELEMENT('00sqkYXHv4OfDNJGKpHKi$', #1, 'Sleeper Z20#0002', 'Sleeper', $, #368052, #368055, $, .SLEEPER.);`

These are classified using `IfcClassification`, `IfcClassificationReference`, and `IfcRelAssociatesClassification`.

<ins>Below is an example of the attributes' values, plus a mapping of these attributes to the bSDD data model.</ins>

`IfcClassification`

| Example instance             | Source           | Edition       | EditionDate | Name       | Description | Location                                                      | ReferenceTokens |
|------------------------------|------------------|---------------|-------------|------------|-------------|---------------------------------------------------------------|-----------------|
| #45 = IFCCLASSIFICATION      | 'buildingSMART'    | '4.3rc4'        | $           | 'IFC'        | $           | http://identifier.buildingsmart.org/uri/buildingsmart/ifc-4.3 | $               |
|                              | IFCLABEL         | IFCLABEL      | IFCDATE     | IFCLABEL   | IFCTEXT     | IFCURIREFERENCE                                               | IFCIDENTIFIER   |
| **Mapping with bSDD data model** | *OrganizationCode* | *DomainVersion* | *ReleaseDate* | *DomainName* | NA          | *DomainNamespaceUri*                                            | NA              |

`IfcClassificationReference`

| Example instance                 | Location                                                                                   | Identification         | Name                    | ReferencedSource                 | Description                                                                                                        | Sort          |
|----------------------------------|--------------------------------------------------------------------------------------------|------------------------|-------------------------|----------------------------------|--------------------------------------------------------------------------------------------------------------------|---------------|
| #46 = IFCCLASSIFICATIONREFERENCE | http://identifier.buildingsmart.org/uri/buildingsmart/ifc-4.3/class/ifctrackelementsleeper | 'ifctrackelementsleeper' | 'IfcTrackElement.SLEEPER' | #45                              | $ | $             |
|                                  | IFCURIREFERENCE                                                                            | IFCIDENTIFIER          | IFCLABEL                | IFCCLASSIFICATIONREFERENCESELECT | IFCTEXT                                                                                                            | IFCIDENTIFIER |
| **Mapping with bSDD data model**     | *DomainNamespaceUri/class/code*                                                              | *Code*                   | *Name*                    | NA                               | *Definition*                                                                                                         | NA            |

`IfcRelAssociatesClassification`

| Example instance                     | GlobalId               | OwnerHistory    | Name                        | Description | RelatedObjects      | RelatingClassification  |
|--------------------------------------|------------------------|-----------------|-----------------------------|-------------|---------------------|-------------------------|
| #47 = IFCRELASSOCIATESCLASSIFICATION | `0OLroQf6D0tfjW0rwFRKeK` | #10             | 'Classification Relationship' | $           | (#21,#22)           | #46                     |
|                                      | IFCGLOBALLYUNIQUEID    | IFCOWNERHISTORY | IFCLABEL                    | IFCTEXT     | IFCDEFINITIONSELECT | IFCCLASSIFICATIONSELECT |


</details>

<details><summary>Spatial reference</summary>

- **Concept Template**: Group Spatial Connectivity
- **Usage** (if existing): NA
> **Acceptance criteria**: For the **Spatial reference** capability, the test is considered passed if **all** the following validation criteria are satisfied.
>
> The validation procedure must verify that a Spatial Element of the requested type references (via `IfcRelReferencedInSpatialStructure`) exactly a given number of Products or Groups of the requested type, no more and no less.

| Spatial Element | Spatial Element Type | Minimum | Maximum | Product or Group | Product Type or Group Type          |
|-----------------|----------------------|---------|---------|------------------|-------------------------------------|
| IfcRailway      | Località             | 1       | 1       | IfcGroup         | Binari di corsa (Contenitore)       |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Deviatoi/Intersezioni (Contenitore) |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Massicciata (Contenitore)           |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Rotaie (Contenitore)                |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Traverse (Contenitore)              |

</details>

<details><summary>Properties of objects and object types</summary>

:construction: under construction :construction:

- **Concept Template**: Property Sets for Objects, Property Sets for Types
- **Usage** (if existing): NA
> **Acceptance criteria**: For the **Properties of objects and object types** capability, the test is considered passed if **all** the following validation criteria are satisfied.
>
> The validation procedure must verify that ...

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

