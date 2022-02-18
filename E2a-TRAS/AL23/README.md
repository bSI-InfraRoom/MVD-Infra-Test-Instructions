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
| Horizontal layout            | Straight Line, Circular Arc, Clothoid     |
| Vertical layout              | Straight Line, Circular Arc               |
| Cant layout                  | Constant Straight Line, Linear Transition |
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
</details>

<details><summary>Concept Templates</summary> 

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Project Context
   - Project Global Positioning
- Object Composition
   - Alignment Layout
   - Spatial Decomposition
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




## Usages, Constraints & Logic
Other than the logic embedded by the IFC Entities & Concept Templates required for this test, **and** the constraints captured in the *Usages, Constraints & Logic* section of of precondition tests, **no additional constraints are applied**




## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_AL23_AmazingSoft.ifc`)




## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section**, and **the ones of pre-required tests** shall be verified, with no exception. :zap:

### General

- All the concept templates must be correctly implemented as presented in the validation criteria
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file
- All validation criteria of the pre-required tests shall apply here too


### Railway alignment (with cant)

> **Acceptance criteria**: For the **Railway alignment (with cant)** capability, the validation procedure must verify that **all** the following validation criteria are satisfied.
>
> If present, all criteria listed in [Usages, Constraints & Logic](#Usages,-Constraints-&-Logic), and in the same section of precondition tests, shall be verified too.

<details open><summary>Railway alignment (with cant)</summary> 

| **ID**  | **CRITERIA**                                                     | **VALUE**                                   | **COMMENT**                |
|---------|------------------------------------------------------------------|---------------------------------------------|----------------------------|
| ALIG_01 | Alignments contained in file                                     | 2                                           |                            |
| ALIG_02 | Component for Alignment 1_Primary route                          | 1 horizontal, 1 vertical, 1 cant            |                            |
| ALIG_03 | Component for Alignment 2_Diverted route                         | 1 horizontal, 1 vertical, 1 cant            |                            |
| ALIG_04 | The horizontal (H) layout is made only by these type of segments | straight line, circular arc, clothoid       |                            |
| ALIG_05 | The vertical (V) layout is made only by these type of segments   | straight line, circular arc                 |                            |
| ALIG_06 | The cant (C) layout is made only by these type of segments       | constant straight line, linear transition   |                            |

</details>
