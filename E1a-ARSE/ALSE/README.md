# Test Instruction

| Documentation Code  | Title                            | Exchange Code   | Test Code | Author        | Data Owner | Version | Date       |
| ------------------- | -------------------------------- | --------------- | --------- | ------------- | ---------- | ------- | ---------- |
| IFC4.3AbRV_E1a_ALSE | Alignment Superelevation & Width | IFC4x3_AbRV-E1a | ALSE      | Lars WIkström | FTIA?      | 1.0     | 07.01.2022 |


## Summary (Intent)

This is the test instruction for IFC4x3_AbRV-E1a-ALSE - Alignment Superelevation & Width.

The test instruction includes:

- A basic project structure setup including units and global positioning
- An alignment structure for a road including the horizontal and vertical layouts
- Assignment of superelevation- and width events along the alignment geometry using linear placement marking the locations where these design parameters change and the values of these design parameters

The data comes from, and is a simplified version of, the IFC Infra Unit Test [MCON-2](https://github.com/bSI-InfraRoom/IFC-infra-unit-test/tree/main/MCON-2) which in turn is extracted from the IFC Rail [Level Crossing storyline](https://github.com/IFCRail/IFC-Rail-Unit-Test/tree/master/8_Storylines%20Test%20(SL)/SL08_Level%20Crossing). 

...

The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

:zap: **This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test** :zap:

## Itemised Roots
*This section lists the primary entities and concept templates being validated by this test instruction, these are listed to understand the scope of the data entities being addressed. this is the documentation of the data placed within BIMQ*

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

:construction: under construction :construction:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- Inherited from impported tests:
  - *IfcProject*
  - *IfcSite*
  - *IfcRoad*
  - *IfcAlignment*
  - *IfcAlignmentHorizontal*
  - *IfcAlignmentVertical*
  - *IfcAlignmentSegment*
  - *IfcAlignmentHorizontalSegment*
  - *IfcAlignmentVerticalSegment*
  - *IfcContext*

- For this test instruction:
  - *IfcFacilityPart*
  - *IfcAnnotation*
  - *IfcPropertySet*
  - *IfcPropertySingleValue*
  - *IfcPropertyEnumeratedValue*


</details>

<details><summary>Concept Templates</summary>

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- Inherited from imported tests:
  - *Project Units*
  - *Project Representation Context*
  - *Project Global Positioning*
  - *Spatial Decomposition*
  - *Spatial Composition*
  - *Spatial Container*
  - *Alignment Decomposition*
  - *Alignment Geometry Gradient*
  - *Product Local Placement*

- For this test instruction:
  - *Product Linear Placement*
  - *Property Sets for Objects*


</details>

## Test Case Imports
Test instructions are defined with a modular approach to reduce repetition of validation criteria and test content, and improve vendors ability to solve issues and bugs. therefore this test instruction *imports/reuses* the following Test instructions and entities with the relevant associated validation criteria.

:construction: under construction :construction:

<details><summary>Imports & Reuses</summary>

| TI Code                                                      | Test Instruction Title          | Comments                                                     |
| ------------------------------------------------------------ | ------------------------------- | ------------------------------------------------------------ |
| [**IFC4x3_AbRV-E1a-ALIN**](https://github.com/bSI-InfraRoom/MVD-Infra-Test-Instructions/blob/develop/E1a-ARSE/ALIN) | Alignment Infrastructure Curves | Including all dependencies, i.e. E0_SSRD, E0_SSSI and E0_MSTP |

</details>

## Usages, Constraints & Logic
The following itemised restrictions and constraints shall be placed on IFC Entities & Concept Templates:

:construction: under construction :construction:

<details><summary>Semantic Usages, Constraints & Logic</summary>

The following itemised Usages, Constraints & Logic are normative entries within the AbRV MVD and MUST be satisfied to meet the defined validation criteria

- IfcAnnotation/SUPERELEVATIONEVENT
    - *Each superelevation event shall have a linear placement relative to the alignment curve according to CT Product Linear Placement*
    - *Each superelevation event shall have one instance of Pset_Superelevation attached according to CT Property Sets for Objects*
    - *Each instance of Pset_Superelevation shall have values for properties Side, Superelevation and TransitionSuperelevation*

- IfcAnnotation/WIDTHEVENT
    - *Each width event shall have a linear placement relative to the alignment curve according to CT Product Linear Placement**
    - *Each width event shall have one instance of Pset_Width attached according to CT Property Sets for Objects**
    - *Each instance of Pset_Superelevation shall have values for properties Side, NominalWidth and TransitionWidth*

</details>

<details><summary>Model Geometry</summary>
The Test case requires the following additional checks related to Model Geometry:

- *Constraint*

</details>

## Expected Results

For certification of capabilities the only source will be:

:construction: under construction :construction:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`-`ExchangeCode`-`TestCode`-`SoftwareVendor`.`ifc` (Example: `IFC4.3_AbRV-E2b-ASTPC-AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet usefull to illustrate test results are:
- Screen-shot of ...
- CSV export of ...

---

## Validation criteria
:zap: For this test case to be considered passed **all capabilities** listed in this section shall be verified, with no exception. :zap:

:construction: under construction :construction:

### General & Imports

<details><summary>Click to expand</summary>

- All the concept templates must be correctly implemented as presented in the validation criteria
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file.


#### Imports
| **TI Code**        | **Criteria Codes** | *COMMENT**                                         |
|--------------------|--------------------|----------------------------------------------------|
| IFC4.3AbRV_E0_MSTP | ALL CRITERIA       | As outlined in the dataset [Imported Entities Table](Dataset/README.md#Imported-Entities-Table) |


#### General
| **ID**  | **CRITERIA**                                        | **VALUE**                                     | **COMMENT** |
|---------|-----------------------------------------------------|-----------------------------------------------|-------------|
| GENE_01 | All requested entities are present in the IFC model | per [Entities Table](Dataset/README.md#Entities-Table) |    |

</details>

### Some Concept Group

<details><summary>Click to expand</summary>
Criteria around the representation of 'Some Concept'

| **ID**  | **CRITERIA**                                        | **VALUE**                                | **COMMENT** |
|---------|-----------------------------------------------------|------------------------------------------|-------------|
| XXXX_01 | A Criteria to follow                               | its expected value or outcome            |             |

</details>
