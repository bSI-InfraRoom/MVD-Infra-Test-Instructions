# Test instructions

| Documentation Code  | Test Title                           | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|---------------------|--------------------------------------|---------------|-----------|-----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_GL01 | (RFI) Global Positioning RFI dataset | E2a (TRAS)    | GL01      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |


## Summary (Intent)

This test case addresses the **export** of the required IFC entities for the exchange of **global positioning** information.

- Refer to [Test Case Imports](#Test-Case-Imports) to know the prerequisites for the present test.

- The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

- :zap: This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test :zap:




## Itemised Roots

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_E2a exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Model setup:
   1. IfcMapConversion
   1. IfcProjectedCRS
</details>

<details><summary>Concept Templates</summary> 

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Project Context
   - Project Global Positioning
</details>




## Model Dataset

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename                | Type (format)  | Description                            |
|-------------------------|----------------|----------------------------------------|
| GeographicData          | figure (jpg)   | Geographic data relevant for the test  |




## Test Case Imports

All validation criteria (and usages) of predecessors' tests shall be **verified for this test too** (regression test principle). Prerequisites for the present test case are listed below.

| TI Code                        | Test Instruction Title | Comments                     |
|--------------------------------|------------------------|------------------------------|
| [IFC4x3_AbRV-E2a-PJ01](./PJ01) | Project Setup          | none                         |




## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_GL01_AmazingSoft.ifc`)




## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section**, and **the ones of pre-required tests** shall be verified, with no exception. :zap:

### General

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------------------|----------------------------|
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       | na                         | na                         |
| GENE_01     | All requested entities (and attributes) exist in file             | As per Entities Table | na                         | na                         |

#### Entities Table

| **Element**      | **Attribute**    | **Value**                                   | **Notes**                                     |
|------------------|------------------|---------------------------------------------|-----------------------------------------------|
| IfcMapConversion | SourceCRS        |                                             | Points to `IfcGeometricRepresentationContext` |
|                  | TargetCRS        |                                             | Points to `IfcProjectedCRS` (see below)       |
|                  | Eastings         | 0                                           |                                               |
|                  | Northings        | 0                                           |                                               |
|                  | OrthogonalHeight | 0                                           |                                               |
|                  | XAxisAbscissa    | 1                                           |                                               |
|                  | XAxisOrdinate    | 0                                           |                                               |
|                  | Scale            | 1                                           |                                               |
|                  | ScaleY           | 1                                           |                                               |
|                  | ScaleZ           | 1                                           |                                               |
| IfcProjectedCRS  | Name             | 'EPSG:3065, EPSG:5214'                      |                                               |
|                  | Description      | 'Istituto Geografico Militare 1995 (IGM95)' |                                               |
|                  | GeodeticDatum    | 'EPSG:6670'                                 |                                               |
|                  | VerticalDatum    | 'EPSG:5214'                                 |                                               |
|                  | MapProjection    | 'UTM'                                       |                                               |
|                  | MapZone          | '33N'                                       |                                               |
|                  | MapUnit          | Meters                                      |


### Global Positioning

> **Acceptance criteria**
 For the **Global Positioning** capability, the validation procedure must verify that:
> - `IfcMapConversion` entity is used to transform the local engineering coordinate system, often called world coordinate system (WCS), into the coordinate reference system of the underlying map.
> - `IfcProjectedCRS` entity is used for representing the coordinate reference system of the map to which the map translation of the local engineering coordinate system of the engineering project relates.

See See [Entities Table](#Entities-Table)