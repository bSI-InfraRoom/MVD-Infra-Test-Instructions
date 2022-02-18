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




## Usages, Constraints & Logic 

Other than the logic embedded by the IFC Entities & Concept Templates required for this test, **and** the constraints captured in the *Usages, Constraints & Logic* section of of precondition tests, **no additional constraints are applied**




## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_GL01_AmazingSoft.ifc`)




## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section**, and **the ones of pre-required tests** shall be verified, with no exception. :zap:

### General

- All the concept templates must be correctly implemented as presented in the validation criteria
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file
- All validation criteria of the pre-required tests shall apply here too


### Global Positioning

> **Acceptance criteria**
 For the **Global Positioning** capability, the validation procedure must verify that:
> - `IfcMapConversion` entity is used to transform the local engineering coordinate system, often called world coordinate system (WCS), into the coordinate reference system of the underlying map.
> - `IfcProjectedCRS` entity is used for representing the coordinate reference system of the map to which the map translation of the local engineering coordinate system of the engineering project relates.
>
> If present, all criteria listed in [Usages, Constraints & Logic](#Usages,-Constraints-&-Logic), and in the same section of precondition tests, shall be verified too.


| **ID**  | **CRITERIA**                                      | **VALUE** | **COMMENT** |
|---------|---------------------------------------------------|-----------|-------------|
| ENAT_01 | Requested entities (and attributes) exist in file | See below |             |

<details><summary>Entities and attributes</summary>

`IfcMapConversion`

| #  | Attribute        | Value / Instructions                          |
|----|------------------|-----------------------------------------------|
| 1  | SourceCRS        | Points to `IfcGeometricRepresentationContext` |
| 2  | TargetCRS        | Points to `IfcProjectedCRS` (see below)       |
| 3  | Eastings         | 0                                             |
| 4  | Northings        | 0                                             |
| 5  | OrthogonalHeight | 0                                             |
| 6  | XAxisAbscissa    | 1                                             |
| 7  | XAxisOrdinate    | 0                                             |
| 8  | Scale            | 1                                             |
| 9  | ScaleY           | 1                                             |
| 10 | ScaleZ           | 1                                             |

`IfcProjectedCRS`

| # | Attribute     | Value / Instructions                        |
|---|---------------|---------------------------------------------|
| 1 | Name          | 'EPSG:3065'                                 |
| 2 | Description   | 'Istituto Geografico Militare 1995 (IGM95)' |
| 3 | GeodeticDatum | 'EPSG:6670'                                 |
| 4 | VerticalDatum |  $                                          |
| 5 | MapProjection | 'UTM'                                       |
| 6 | MapZone       | '33N'                                       |
| 7 | MapUnit       | Meters                                      |

</details>