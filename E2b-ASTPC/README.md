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

:warning: <ins> This is a test-driven process: refer to the [Validation Criteria](./Validation%20Criteria.md) to understand what is required by the test</ins> :warning: 

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
| Alignment1_horizontal ; Alignment2_horizontal | csv            | Alignment parameters for horizontal segments |
| Alignment1_vertical ; Alignment2_vertical     | csv            | Alignment parameters for vertical segments |
| Alignment1_cant ; Alignment2_cant     | csv            | Alignment parameters for cant segments |
| *under production*      | LandXML        | Alignment LandXML file, not including cant  |
| *under production*      | dwg            | Alignment dwg file, not including cant  |
| ObjectsOverview         | diagram (png)  | Objects overview: a diagram + table describing the main elements of the test |
| FS60UNI_R.250_TG.0.092  | drawing (svg)  | Turnout drawing to be used as example |
| SimplifiedTurnout       | figure (png)   | Simplified turnout scheme |

---

## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2b_ASTPC_AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet usefull to illustrate test results are:
- Screen-shot of ...
- CSV export of ...

---

## Validation criteria
:warning: <ins>For this test case to be considered passed **all capabilities** listed in [Validation Criteria](./Validation%20Criteria.md) shall be verified, with no exception.</ins> :warning:


