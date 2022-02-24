# Test Instruction

| Documentation Code    | Title                            | Exchange Code   | Test Code | Author        | Data Owner | Version | Date       |
| --------------------- | -------------------------------- | --------------- | --------- | ------------- | ---------- | ------- | ---------- |
| IFC4.3AbRV_E1a_ALSE02 | Alignment Superelevation & Width | IFC4x3_AbRV-E1a | ALSE02    | Lars WIkström | FTIA       | 1.0     | 07.01.2022 |


## Summary (Intent)

With these instructions the infrastructure (e.g. Road) alignment exchange is established. This test instruction use the same alignment definition as [ALIN06](../ALIN06).

| Info                         |                                      |
| ---------------------------- | ------------------------------------ |
| Number of alignment(s)       | 1                                    |
| Properties of segments       | no                                   |
| Horizontal layout            | Straight Line, Circular Arc          |
| Vertical layout              | Straight Line, Circular Arc          |
| Geometric representation     | IfcCompositeCurve, IfcGradientCurve  |
| Superelevation               | 12 IfcAnnotation/SUPERELEVATIONEVENT |
| Width                        | 8 IfcAnnotation/WIDTHEVENT           |
| IFC reference file available | Yes                                  |

The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

The data comes from, and is a simplified version of, the IFC Infra Unit Test [MCON-2](https://github.com/bSI-InfraRoom/IFC-infra-unit-test/tree/main/MCON-2) which in turn is extracted from the IFC Rail [Level Crossing storyline](https://github.com/IFCRail/IFC-Rail-Unit-Test/tree/master/8_Storylines%20Test%20(SL)/SL08_Level%20Crossing). 

:zap: **This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test** :zap:

## Itemised Roots
*This section lists the primary entities and concept templates being validated by this test instruction, these are listed to understand the scope of the data entities being addressed. this is the documentation of the data placed within BIMQ*

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

:construction: under construction :construction:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- Inherited from imported tests:
  - Model setup
    - *IfcSite*
    - *IfcRoad*
    - *IfcRepresentationContext*
    - *IfcMapConversion*
    - *IfcProjectedCRS*
    - *IfcUnitAssignment*
  - Alignment
    - *IfcAlignment*
    - *IfcAlignmentHorizontal*
    - *IfcAlignmentVertical*
    - *IfcAlignmentSegment*
    - *IfcAlignmentHorizontalSegment*
    - *IfcAlignmentVerticalSegment*
    - *IfcCompositeCurve*
    - *IfcGradientCurve*
    - *IfcCurveSegment*
    - *IfcLine*
    - *IfcCircle*
- For this test instruction:
  - *IfcAnnotation*
  - *IfcPropertySet*
  - *IfcPropertySingleValue*
  - *IfcPropertyEnumeratedValue*
  - *IfcLinearPlacement*

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
  - Product Relative Positioning


</details>

## Test Case Imports
Test instructions are defined with a modular approach to reduce repetition of validation criteria and test content, and improve vendors ability to solve issues and bugs. therefore this test instruction *imports/reuses* the following Test instructions and entities with the relevant associated validation criteria.

:construction: under construction :construction:

<details><summary>Imports & Reuses</summary>

| TI Code                                                      | Test Instruction Title          | Comments                                                     |
| ------------------------------------------------------------ | ------------------------------- | ------------------------------------------------------------ |
| [**IFC4x3_AbRV-E1a-ALIN06**](https://github.com/bSI-InfraRoom/MVD-Infra-Test-Instructions/blob/develop/E1a-ARSE/ALIN06) | Alignment Infrastructure Curves | Including all dependencies, i.e. E0_SSRD, E0_SSSI and E0_MSTP |

</details>

## Usages, Constraints & Logic
The following itemised restrictions and constraints shall be placed on IFC Entities & Concept Templates:

:construction: under construction :construction:

<details><summary>Semantic Usages, Constraints & Logic</summary>

| **ID** | **CRITERIA**                         | **VALUE**                           | **COMMENT** |
| ------ | ------------------------------------ | ----------------------------------- | ----------- |
| SE_00  | Superelevation structure is verified | See below for further specification |             |
| SE_01  | Width structure is verified          | See below for further specification |             |

SE_00: Superelevation structure is verified

>1. The dataset shall contain 12 superelevation event instances, each represented by an `IfcAnnotation` with `PredefinedType=.SUPERELEVATIONEVENT.`
>2. Each superelevation event shall have an associated `IfcLinearPlacement` relative to the alignment curve according to CT Product Linear Placement at the specified locations
>2. Each superelevation event shall be positioned relative to the `IfcAlignment` using `IfcRelPositions` according to CT Product Relative Positioning
>3. Each superelevation event shall have an associated Property set with the name `Pset_Superelevation` according to CT Property sets For Objects
>4. Each `Pset_Superelevation` shall have properties `Side`, `Superelevation` and `TransitionSuperelevation` set to the specified values.

SE_01: Width structure is verified

>1. The dataset shall contain 8 width event instances, each represented by an `IfcAnnotation` with `PredefinedType=.WIDTHEVENT.`
>2. Each width event shall have an associated `IfcLinearPlacement` relative to the alignment curve according to CT Product Linear Placement at the specified locations
>2. Each width event shall be positioned relative to the `IfcAlignment` using `IfcRelPositions` according to CT Product Relative Positioning
>3. Each width event shall have an associated Property set with the name `Pset_Width` according to CT Property sets For Objects
>4. Each `Pset_Width` shall have properties `Side`, `NominalWidth` and `TransitionWidth` set to the specified values.

</details>

<details><summary>Model Geometry</summary>
The Test case requires the following additional checks related to Model Geometry:
Neither the superelevation events nor the Width events needs explicit geometric representation.
</details>

## Expected Results

For certification of capabilities the only source will be:

:construction: under construction :construction:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`-`ExchangeCode`-`TestCode`-`SoftwareVendor`.`ifc` (Example: `IFC4.3_AbRV-E2b-ASTPC-AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet usefull to illustrate test results are:
- Screen-shot of a planar view and a "long section" showing the superelevation and width changes or a table showing the same information

---

## Validation criteria
:zap: For this test case to be considered passed **all capabilities** listed in this section shall be verified, with no exception. :zap:

:construction: under construction :construction:

### General & Imports

<details><summary>Click to expand</summary>

- All the concept templates must be correctly implemented as presented in the validation criteria
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file.


#### Imports
| **TI Code**           | **Criteria Codes** | *COMMENT**                                 |
| --------------------- | ------------------ | ------------------------------------------ |
| IFC4.3AbRV_E1a_ALIN06 | ALL CRITERIA       | As outlined in the ALIN06 test instruction |


#### General
| **ID**  | **CRITERIA**                                        | **VALUE**                                     | **COMMENT** |
|---------|-----------------------------------------------------|-----------------------------------------------|-------------|
| GENE_01 | All requested entities are present in the IFC model | per [Entities Table](Dataset/README.md#Entities-Table) |    |

</details>

### Superelevation event

<details><summary>Click to expand</summary>

| **ID**  | **CRITERIA**                                                 | **VALUE**                                      | **COMMENT** |
| ------- | ------------------------------------------------------------ | ---------------------------------------------- | ----------- |
| ALSE_01 | Superelevation events contained in file                      | 12                                             |             |
| ALSE_02 | Each superelevation event has a linear placement at the specified location | See [Dataset description](./Dataset/README.md) |             |
| ALSE_03 | Each superelevation event has a Pset_Superelevation attached with the correct property values assigned | See [Dataset description](./Dataset/README.md) |             |
| ALSE_04 | Each superelevation event is associated to the IfcAlignment using IfcRelPositions relationship |                                                |             |
| ALSE_05 | Width events contained in file                               | 8                                              |             |
| ALSE_06 | Each width event has a linear placement at the specified location | See [Dataset description](./Dataset/README.md) |             |
| ALSE_07 | Each width event has a Pset_Width attached with the correct property values assigned | See [Dataset description](./Dataset/README.md) |             |
| ALSE_08 | Each width event is associated to the IfcAlignment using IfcRelPositions relationship |                                                |             |

</details>
