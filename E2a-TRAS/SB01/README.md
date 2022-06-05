# Test instructions

| Documentation Code   | Test Title                                 | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|--------------------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_SB01  | (RFI) Track sub-structure for single track | E2a (TRAS)    | SB01      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |




## Summary (Intent)

This test case addresses the **export** of the required IFC entities for the exchange of **track sub-structure** information.

This test case focuses only on track sub-structure (red in picture below). For the track super-structure part (green in picture below), refer to test case **IFC4.3AbRV_E2a_SP01**, of which SB01 is a pre-condition.

Snippet:
<img src="./Dataset/TrackCrossSection_snippet.png" width="500"/>

- Refer to [Test Case Imports](#Test-Case-Imports) to know the prerequisites for the present test.

- The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

- :zap: This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test :zap:





## Itemised Roots
:construction: **under construction, check CT for product shape** :construction:

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_E2a exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Products:
   1. IfcCourse / IfcCourseType
   1. IfcEarthworksFill
</details>

<details><summary>Concept Templates</summary> 

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Object Attributes
   - Object Predefined Type
- Object definition
   - Object Typing
- Product Shape
   - Product Geometric Representation
   - Body SectionedSolidHorizontal
- Object Connectivity
   - Spatial Containment
- Product Placement
   - Product Local Placement
   - Product Linear Placement
</details>




## Model Dataset

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename              | Type (format) | Description                                                        |
|-----------------------|---------------|--------------------------------------------------------------------|
| TrackCrossSection     | drawing (png) | Track cross section to be used as example                          |



## Test Case Imports

All validation criteria (and usages) of predecessors' tests shall be **verified for this test too** (regression test principle). Prerequisites for the present test case are listed below.

| TI Code                        | Test Instruction Title               | Comments |
|--------------------------------|--------------------------------------|----------|
| [IFC4x3_AbRV-E1-AL22](./AL22)  | (RFI) Two alignments without cant    | **For the test to be passed, the track sub-structure shall be modelled ONLY for the Primary Route (i.e., Alignment 1_Primary route)** |




## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_SB01_AmazingSoft.ifc`)


## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section**, and **the ones of pre-required tests** shall be verified, with no exception. :zap:

### General

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------------------|----------------------------|
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       | na                         | na                         |
| GENE_01     | All requested entities (and attributes) exist in file             | As per Entities Table | na                         | na                         |

#### Entities Table

| **Element**       | **Attribute**  | **Value**                 | **Notes**                      |
|-------------------|----------------|---------------------------|--------------------------------|
| IfcEarthworksFill | Name           | Corpo del rilevato        |                                |
|                   | PredefinedType | SUBGRADE                  |                                |
| IfcCourse         | Name           | Strato di sub-ballast     | Junction layer in the figure   |
|                   | ObjectType     | Junction                  |                                |
|                   | PredefinedType | USERDEFINED               |                                |
| IfcCourse         | Name           | Strato di supercompattato | Foundation layer in the figure |
|                   | ObjectType     | Foundation                |                                |
|                   | PredefinedType | USERDEFINED               |