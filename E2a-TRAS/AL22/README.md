# Test instructions

| Documentation Code   | Test Title                        | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|-----------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E1_AL22   | (RFI) Two alignments without cant | E1 (ALRF)     | AL22      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |


## Summary (Intent)

This test case addresses the **export** of the required IFC entities for the exchange of **railway alignment without cant** information.

Snippet:
<img src="./Dataset/LineLayout.svg" width="500"/>

| Info                         |                                           |
|------------------------------|-------------------------------------------|
| Number of alignment(s)       | 2                                         |
| Vertical Measurement         | Lower Rail                                |
| Properties of segments       | no                                        |
| Horizontal layout            | Straight Line, Circular Arc, Clothoid     |
| Vertical layout              | Straight Line, Circular Arc               |
| Cant layout                  | not present                               |
| IFC reference file available | no                                        |


- Refer to [Test Case Imports](#Test-Case-Imports) to know the prerequisites for the present test.

- The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

- :zap: This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test :zap:




## Itemised Roots

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_E2a exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Model setup:
   1. IfcSite
   1. IfcRailway
- Alignment:
   1. IfcAlignment
   1. IfcAlignmentHorizontal
   1. IfcAlignmentVertical
</details>

<details><summary>Concept Templates</summary> 

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Project Context
   - Project Global Positioning
- Object Composition
   - Alignment Layout
   - Spatial Decomposition
- Object Connectivity
   - Spatial Containment
</details>




## Model Dataset

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename              | Type (format) | Description                                                        |
|-----------------------|---------------|--------------------------------------------------------------------|
| LineLayout            | figure (svg)  | Schematic line layout of the test case                             |
| Alignment1_horizontal | csv           | Alignment parameters for horizontal segments of the Primary Route  |
| Alignment2_horizontal | csv           | Alignment parameters for horizontal segments of the Diverted Route |
| Alignment1_vertical   | csv           | Alignment parameters for vertical segments of the Primary Route    |
| Alignment2_vertical   | csv           | Alignment parameters for vertical segments of the Diverted Route   |




## Test Case Imports

All validation criteria (and usages) of predecessors' tests shall be **verified for this test too** (regression test principle). Prerequisites for the present test case are listed below.

| TI Code                        | Test Instruction Title               | Comments |
|--------------------------------|--------------------------------------|----------|
| [IFC4x3_AbRV-E2a-PJ01](./PJ01) | Project Setup                        | none     |
| [IFC4x3_AbRV-E2a-GL01](./GL01) | (RFI) Global Positioning RFI dataset | none     |




## Usages, Constraints & Logic 

The following itemised restrictions and constraints shall be placed on IFC Entities & Concept Templates:

<details><summary>Semantic Usages, Constraints & Logic</summary>

The following itemised Usages, Constraints & Logic are normative entries within the AbRV MVD and MUST be satisfied to meet the defined validation criteria

| **ID**  | **CRITERIA**                                        | **VALUE**                           | **COMMENT** |
|---------|-----------------------------------------------------|-------------------------------------|-------------|
| ALIG_00 | Alignment layout structure is verified              | See below for further specification |             |
| SITE_00 | IfcAlignment shall always be contained in a IfcSite | na                                  |             |


ALIG_00: Alignment layout structure is verified

> 1. Each `IfcAlignment` must nest exactly 1 `IfcAlignmentHorizontal`
> 1. Each `IfcAlignment` must nest at most 1 `IfcAlignmentVertical`
> 1. Each `IfcAlignment` must nest at most 1 `IfcAlignmentCant`
> 1. Each `IfcAlignmentHorizontal` must be nested only by 1 `IfcAlignment`
> 1. Each `IfcAlignmentVertical` must be nested only by 1 `IfcAlignment`
> 1. Each `IfcAlignmentCant` must be nested only by 1 `IfcAlignment`
> 1. Each `IfcAlignment` must nest only the following entities: `IfcAlignmentHorizontal`, `IfcAlignmentVertical`, `IfcAlignmentCant`, `IfcReferent`, `IfcAlignment`
> 1. Each `IfcAlignmentHorizontal` must nest only `IfcAlignmentHorizontalSegment`
> 1. Each `IfcAlignmentVertical` must nest only `IfcAlignmentVerticalSegment`
> 1. Each `IfcAlignmentCant` must nest only `IfcAlignmentCantSegment`

</details>

<details><summary>Model Geometry</summary>
The Test case requires the following additional checks related to Model Geometry:

| **ID**  | **CRITERIA**                                                              | **VALUE** | **COMMENT**                |
|---------|---------------------------------------------------------------------------|-----------|----------------------------|
| ALIG_07 | Value of the *RailHeadDistance* along the entire alignment                | 1500 mm   | See notes below for detail |
| ALIG_08 | Semantic description of segments corresponds to their geometry            | NA        | RDF tools can do this      |
| ALIG_09 | Tangential continuity of all segments is verified, tolerance = 0,00000001 |           | RDF tools can do this      |


ALIG_07 - Note

> The *RailHeadDistance* (blue line in the figure below) is a normalized value used to compute the angle of cant. RFI uses 1500 mm for a track gauge of 1435 mm
>
>   <img src="Dataset/CantFromLowerRail.png" height="300"/>

</details>





## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_AL22_AmazingSoft.ifc`)




## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section**, and **the ones of pre-required tests** shall be verified, with no exception. :zap:

### General

- All the concept templates must be correctly implemented as presented in the validation criteria
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file
- All validation criteria of the pre-required tests shall apply here too

| **ID**  | **CRITERIA**                                      | **VALUE** | **COMMENT** |
|---------|---------------------------------------------------|-----------|-------------|
| ENAT_01 | Requested entities (and attributes) exist in file | See below |             |

<details><summary>Entities and attributes</summary>

`IfcAlignment` (Alignment 1_Primary route)

| Attribute      | Value                     |
|----------------|---------------------------|
| Name           | Alignment 1_Primary route |
| Description    | $                         |
| ObjectType     | Railway track alignment   |
| PredefinedType | USERDEFINED               |

`IfcAlignment` (Alignment 2_Diverted route)

| Attribute      | Value                      |
|----------------|----------------------------|
| Name           | Alignment 2_Diverted route |
| Description    | $                          |
| ObjectType     | Railway track alignment    |
| PredefinedType | USERDEFINED                |

`IfcSite`

| Attribute      | Value                                                   |
|----------------|---------------------------------------------------------|
| Name           | Sito                                                    |
| Description    | 'One of the many sites that can be present in the file' |
| ObjectType     | $                                                       |
| PredefinedType | $                                                       |

`IfcRailway`

| Attribute       | Value       |
|-----------------|-------------|
| Name            | LO1336      |
| Description     | Foligno     |
| ObjectType      | Località    |
| PredefinedType  | USERDEFINED |
| CompositionType | ELEMENT     |

</details>

### Railway alignment (without cant)

> **Acceptance criteria**: For the **Railway alignment (without cant)** capability, the validation procedure must verify that **all** the following validation criteria are satisfied.
>
> If present, all criteria listed in [Usages, Constraints & Logic](#Usages,-Constraints-&-Logic), and in the same section of precondition tests, shall be verified too.

<details open><summary>Railway alignment (without cant)</summary> 

| **ID**  | **CRITERIA**                                                     | **VALUE**                                   | **COMMENT**                |
|---------|------------------------------------------------------------------|---------------------------------------------|----------------------------|
| ALIG_01 | Alignments contained in file                                     | 2                                           |                            |
| ALIG_02 | Component for Alignment 1_Primary route                          | 1 horizontal, 1 vertical                    |                            |
| ALIG_03 | Component for Alignment 2_Diverted route                         | 1 horizontal, 1 vertical                    |                            |
| ALIG_04 | The horizontal (H) layout is made only by these type of segments | straight line, circular arc, clothoid       |                            |
| ALIG_05 | The vertical (V) layout is made only by these type of segments   | straight line, circular arc                 |                            |

</details>


<details open><summary> Alignment 1_Primary route </summary>

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


<details open><summary> Alignment 2_Diverted route </summary>

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

### Spatial decomposition

> **Acceptance criteria**: For the **Spatial decomposition** capability, the validation procedure must verify that a Parent Element of the requested type aggregates (via `IfcRelAggregates`) exactly a given number of Child Elements of the requested type, no more and no less.

| Parent Element | Parent Element Type | Minimum | Maximum | Child Element   | Child Element Type |
|----------------|---------------------|---------|---------|-----------------|--------------------|
| IfcProject     |                     | 1       | 1       | IfcSite         |                    |
| IfcSite        |                     | 1       | 1       | IfcRailway      | Località           |


### Spatial containment

> **Acceptance criteria**: For the **Spatial containment** capability, the validation procedure must verify that a Spatial Element of the requested type contains (via `IfcRelContainedInSpatialStructure`) exactly a given number of Elements of the requested type, no more and no less.

| Spatial Element | Spatial Element Type | Minimum | Maximum | Element            | Element Type            |
|-----------------|----------------------|---------|---------|--------------------|-------------------------|
| IfcSite         |                      | 2       | 2       | IfcAlignment       | Railway track alignment |
