# Test instructions


|       Test Case title     | Code | Abbreviation | Author | Data Owner |
|:-------------------------:|:----:|:------------:|:------:| :---------:|
|  Aggregate structures + Track. Pavement and Course (ballast) + Cant | E2b1 | ASTPC | Evandro Alfieri | RFI |

## Summary (intent)

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

---

## Itemised Roots
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

<details open><summary>Concept Templates</summary> 

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

---

## Variations
The Following occurrence variations need to be checked and certified in relation to the targeted entities and concept templates:

- Entity_01 - *description of variation*
- Entity_02 - *description of variation*


## Usages
The following itemised restrictions and constraints shall be placed on IFC Entities & Concept Templates:

:construction: under construction :construction:

- IfcSomething
    - *Constraint*

The Test case requires the following additional checks related to Model Geometry:

- *Correspondence between the business-logic and the geometry parts for all segments*
- *Tangential continuity of alignemnt segments. Tolerance of ... millimetres*
- ... (to be continued)

---

## Model Dataset
This test case utilises the dataset collected [here](./E2b1-ASTPC/Dataset) and summarised in the table below. Form more details on each item see [Dataset description](./E2b1-ASTPC/Dataset/Dataset_description.md).


1. [dwg]
1. Picture of ...[png]
1. ....
1.  [png]

*This is a later step that involved the detailed documentation of the certification dataset (model)*


| ID | Filename             | Type (format)  | Description                               |
|----|----------------------|----------------|-------------------------------------------|
|    | *filename + link* | csv            | Alignment parameters for horizontal segments  |
|    | *filename + link* | csv            | Alignment parameters for vertical segments  |
|    | *filename + link* | csv            | Alignment parameters for cant segments  |
|    | *filename + link* | LandXML        | Alignment LandXML file, not including cant  |
|    | *filename + link* | dwg            | Alignment dwg file, not including cant  |
|    | *filename + link* | figure (png)  | Schematic layout of the test case railway line |
|    | [Line layout](Line_layout.jpg) | diagram (jpg)  | Diagram describing the main objects and relationships to be used for the test case |
|    | *filename + link* | drawing (pdf)  | Cross section example |
|    | *filename + link* | drawing (dwg)  | Cross section example |

---

## Expected Results
Considering the aim of this test, the expected results are:

:construction: under construction :construction:

1. N. 1 IFC file containing the information as requested
2. Screen-shot of ...

---

## Validation criteria
<ins>For this test case to be considered passed **all** validation criteria listed in this section shall be satisfied, with no exception.</ins>

:construction: under construction :construction:

<details><summary>General</summary>

- All the concept templates must be correctly used
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file

</details>

<details open><summary>Alignment</summary> 

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



<details><summary> Alignment 1 </summary><blockquote>

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

<details><summary> Alignment 2 </summary><blockquote>

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

...
