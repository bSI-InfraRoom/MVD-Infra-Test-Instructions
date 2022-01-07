# Test instructions

| Documentation Code  | Test Title                           | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|---------------------|--------------------------------------|---------------|-----------|-----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_GLOB | (RFI) Global Positioning RFI dataset | E2a (TRAS)    | GLOB      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |


## Summary (Intent)

TBC
...

The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

:zap: This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test :zap:




## Itemised Roots

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_E2a exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Model setup:
   1. IfcProject
   1. IfcSite
   1. IfcMapConversion
   1. IfcProjectedCRS
</details>

<details><summary>Concept Templates</summary> 

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Project Context
   - Project Global Positioning
   - Project Representation Context
   - Project Units
</details>




## Model Dataset
> I liked the dataset section referring to the dataset folder

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **Form more details on each item see [Dataset description](Dataset/README.md).**

| Filename                | Type (format)  | Description                            |
|-------------------------|----------------|----------------------------------------|
| GeographicData          | figure (jpg)   | Geographic data relevant for the test  |




## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_GLOB_AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet usefull to illustrate test results are:
- Screen-shot of ...
- CSV export of ...




## Usages, Constraints & Logic 
> Might be overlaps with validation criteria sometimes

The following itemised restrictions and constraints shall be placed on IFC Entities & Concept Templates:

:construction: under construction :construction:

<details><summary>Semantic Usages, Constraints & Logic</summary>

The following itemised Usages, Constraints & Logic are normative entries within the AbRV MVD and MUST be satisfied to meet the defined validation criteria

- IfcSomething
    - *Constraint*

</details>

<details><summary>Model Geometry</summary>
The Test case requires the following additional checks related to Model Geometry:

- *Constraint*

</details>




## Test Case Imports

> Shouldn't be enough to list the tests that are preconditions to this very one test? And that all validation criteria of predecessors shall be verified **again** for this test?
> Important: the optimisation is provided by the fact that validation criteria will not be re-written, but just referenced. This doesn't mean that the referenced criteria won't be validated again with the new file (the one related to this test). Quite the opposite: regression tests are essential.

Test instructions are defined with a modular approach to reduce repetition of validation criteria and test content, and improve vendors ability to solve issues and bugs. therefore this test instruction *imports/reuses* the following Test instructions and entities with the relevant associated validation criteria.

:construction: under construction :construction:

<details><summary>Imports & Reuses</summary>

| TI Code                                  | Test Instruction Title    | Comments                     |
|------------------------------------------|---------------------------|------------------------------|
| [IFC4.3AbRV_E0_MSTP](../../E0-SCFD/MSTP) | Model Setup & Positioning | PROJ-01 imported along with RCTX-01 and associated configuration and history data |

</details>




## Validation criteria
:zap: For this test case to be considered passed **all capabilities** listed in this section shall be verified, with no exception. :zap:

### General & Imports

<details><summary>Click to expand</summary>

- All the concept templates must be correctly implemented as presented in the validation criteria
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file.

#### Imports
> This can be removed if we already say in the Test Import section that all the validation criteria of the dependent tests shall apply here too.

| **TI Code**        | **Criteria Codes** | **COMMENT**                                        |
|--------------------|--------------------|----------------------------------------------------|
| IFC4.3AbRV_E0_MSTP | ALL CRITERIA       | As outlined in the dataset [Imported Entities Table](Dataset/README.md#Imported-Entities-Table) |

#### General
> These 4 rules shall be part of a Project Setup test case that is just referenced by this GLOb test.


| **ID**  | **CRITERIA**                                     | **VALUE**                             | **COMMENT**                                     |
|---------|--------------------------------------------------|---------------------------------------|-------------------------------------------------|
| DIST_01 | Unit of measure for all distances                | **meter** (m)                         | This shall be part of a Project Setup test case |
| ANGL_01 | Unit of measure all angles                       | **radian** (π)                        | This shall be part of a Project Setup test case |
| DIST_02 | Required precision for **distances**             | "minimum 4 decimal places (0,0001)"   | This shall be part of a Project Setup test case |
| ANGL_02 | Required precision for **angles** and **slope**  | "minimum 6 decimal places (0,000001)" | This shall be part of a Project Setup test case |

</details>

### Project Global Positioning

<details><summary>Click to expand</summary>

- **Concept Template**: Project Global Positioning
- **Usage** (if existing): NA
> **Acceptance criteria**: For the **Project Global Positioning** capability, the test is considered passed if **all** the following validation criteria are satisfied.
>
> The validation procedure must verify that:
> - `IfcMapConversion` entity is used to transform the local engineering coordinate system, often called world coordinate system (WCS), into the coordinate reference system of the underlying map.
> - `IfcProjectedCRS` entity is used for representing the coordinate reference system of the map to which the map translation of the local engineering coordinate system of the engineering project relates.


| **ID**  | **CRITERIA**                                      | **VALUE** | **COMMENT** |
|---------|---------------------------------------------------|-----------|-------------|
| ENAT_01 | Requested entities (and attributes) exist in file | See below |             |

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