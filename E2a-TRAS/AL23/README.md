# Test instructions

| Documentation Code   | Test Title                        | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|-----------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E1b_AL23  | (RFI) Two alignments with cant    | E1b (ALRC)    | AL23      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |



## Summary (Intent)

This test case addresses the **export** of the required IFC entities for the exchange of **railway alignment with cant** information.

| Info                         |                                           |
|------------------------------|-------------------------------------------|
| Number of alignment(s)       | 2                                         |
| Vertical Measurement         | Lower Rail                                |
| Properties of segments       | no                                        |
| Horizontal layout            | Line, Circular Arc, Clothoid     |
| Vertical layout              | Constant Gradient, Circular Arc               |
| Cant layout                  | Constant Cant, Linear Transition |
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
   1. IfcAlignmentCant
   1. IfcAlignmentSegment
</details>

<details><summary>Concept Templates</summary> 

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Project Context
   - Project Global Positioning
- Object Composition
   - Alignment Layout
   - Alignment Geometry Cant
   - Spatial Decomposition
- Product Shape
   - Product Geometric Representation
       - Alignment Geometry
          - Alignment Geometry Cant
</details>




## Model Dataset

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename              | Type (format) | Description                                                        |
|-----------------------|---------------|--------------------------------------------------------------------|
| Alignment1_cant       | csv           | Alignment parameters for cant segments of the Primary Route        |
| Alignment2_cant       | csv           | Alignment parameters for cant segments of the Diverted Route       |




## Test Case Imports

All validation criteria (and usages) of predecessors' tests shall be **verified for this test too** (regression test principle). Prerequisites for the present test case are listed below.

| TI Code                        | Test Instruction Title               | Comments |
|--------------------------------|--------------------------------------|----------|
| [IFC4x3_AbRV-E2a-PJ01](./PJ01) | Project Setup                        | none     |
| [IFC4x3_AbRV-E2a-GL01](./GL01) | (RFI) Global Positioning RFI dataset | none     |
| [IFC4x3_AbRV-E1-AL22](./AL22)  | (RFI) Two alignments without cant    | none     |




## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_AL23_AmazingSoft.ifc`)




## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section**, and **the ones of pre-required tests** shall be verified, with no exception. :zap:

### General

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------------------|----------------------------|
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       | na                         | na                         |
| GENE_01     | All requested entities (and attributes) exist in file             | As per Entities Table | na                         | na                         |

#### Entities Table

| **Element**            | **Attribute**   | **Value**                                               | **Notes** |
|------------------------|-----------------|---------------------------------------------------------|-----------|
| IfcAlignment           | Name            | Alignment 1_Primary route                               |           |
|                        | ObjectType      | Railway track alignment                                 |           |
|                        | PredefinedType  | USERDEFINED                                             |           |
| IfcAlignment           | Name            | Alignment 2_Diverted route                              |           |
|                        | ObjectType      | Railway track alignment                                 |           |
|                        | PredefinedType  | USERDEFINED                                             |           |
| IfcAlignmentCant       | Name            | AC1                                                     |           |
| IfcAlignmentCant       | Name            | AC2                                                     |           |
| IfcSite                | Name            | Sito                                                    |           |
|                        | Description     | 'One of the many sites that can be present in the file' |           |
| IfcRailway             | Name            | LO1336                                                  |           |
|                        | Description     | Foligno                                                 |           |
|                        | ObjectType      | Località                                                |           |
|                        | PredefinedType  | USERDEFINED                                             |           |
|                        | CompositionType | ELEMENT                                                 |           |


### Railway alignment (with cant)

> **Acceptance criteria**: For the **Railway alignment (with cant)** capability, the validation procedure must verify that **all** the following validation criteria are satisfied.

| **RULE ID** | **CRITERIA**                                             | **VALUE [examples]**                           | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|----------------------------------------------------------|------------------------------------------------|----------------------------|------------------------|
| SITE_00     | All IfcAlignment shall always be contained in an IfcSite |                                                |                            | Spatial Containment    |
| ALIG_00     | Alignment layout structure is verified                   | See steps                                      |                            | Alignment Layout       |
| ALIG_01     | Number of alignments contained in file                   | [2]                                            |                            |                        |
| ALIG_02     | Parameters of alignment segments are verified            | As per Alignment Table                         |                            |                        |
| ALIG_03     | Alignment geometric compliance is verified               | As per Alignment geometric compliance document |                            |                        |
| ALIG_04     | Value of the RailHeadDistance along the entire alignment | [1500 mm]                                      | IfcAlignmentCant           |                        |

<details><summary>ALIG_00 steps</summary>

| **STEP ID** | **STEP**                                                                                                                                           |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| ALIG_00.1   | Each IfcAlignment must nest exactly 1 IfcAlignmentHorizontal                                                                                       |
| ALIG_00.2   | Each IfcAlignment must nest at most 1 IfcAlignmentVertical                                                                                         |
| ALIG_00.3   | Each IfcAlignment must nest exactly 1 IfcAlignmentVertical                                                                                         |
| ALIG_00.4   | Each IfcAlignment must nest at most 1 IfcAlignmentCant                                                                                             |
| ALIG_00.5   | Each IfcAlignment must nest exactly 1 IfcAlignmentCant                                                                                             |
| ALIG_00.6   | Each IfcAlignmentHorizontal must be nested only by 1 IfcAlignment                                                                                  |
| ALIG_00.7   | Each IfcAlignmentVertical must be nested only by 1 IfcAlignment                                                                                    |
| ALIG_00.8   | Each IfcAlignmentCant must be nested only by 1 IfcAlignment                                                                                        |
| ALIG_00.9   | Each IfcAlignment must nest only the following entities: IfcAlignmentHorizontal, IfcAlignmentVertical, IfcAlignmentCant, IfcReferent, IfcAlignment |
| ALIG_00.10  | Each IfcAlignmentHorizontal nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentHorizontalSegment         |
| ALIG_00.11  | Each IfcAlignmentVertical nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentVerticalSegment             |
| ALIG_00.12  | Each IfcAlignmentCant nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentCantSegment                     |

</details>

<details><summary>ALIG_04 details</summary>

> The *RailHeadDistance* (blue line in the figure below) is a normalized value used to compute the angle of cant. RFI uses 1500 mm for a track gauge of 1435 mm
>
>   <img src="Dataset/CantFromLowerRail.png" height="300"/>

</details>