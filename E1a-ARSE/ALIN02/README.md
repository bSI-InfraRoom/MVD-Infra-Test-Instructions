# Test Instruction

| Documentation Code    | Title                           | Exchange Code | Test Code | Author        | Data Owner | Version | Date       |
| --------------------- | ------------------------------- | ------------- | --------- | ------------- | ---------- | ------- | ---------- |
| IFC4.3AbRV_E1a_ALIN02 | Alignment Infrastructure Curves | E1a           | ALIN02    | Lars Wikström | TRV        | 1.0     | 07.01.2022 |


## Summary (Intent)

With these instructions the infrastructure (e.g. Road) alignment exchange is established.

| Info                         |                                       |
| ---------------------------- | ------------------------------------- |
| Number of alignment(s)       | 1                                     |
| Properties of segments       | no                                    |
| Horizontal layout            | Straight Line, Circular Arc, Clothoid |
| Vertical layout              | Straight Line, Parabolic Arc          |
| Geometric representation     | No                                    |
| IFC reference file available | Yes                                   |

- Refer to [Test Case Imports](#Test-Case-Imports) to know the prerequisites for the present test.

- The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

- :zap: This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test :zap:

## Itemised Roots
The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>
These entities represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**



- Model setup
  - *IfcProject*
  - *IfcRepresentationContext*
  - *IfcMapConversion*
  - *IfcProjectedCRS*
  - *IfcUnitAssignment*
- Spatial structure
  - *IfcSite*
  - *IfcRoad*
- Alignment

  - *IfcAlignment*
  - *IfcAlignmentHorizontal*
  - *IfcAlignmentVertical*
  - *IfcAlignmentSegment*
  - *IfcAlignmentHorizontalSegment*
  - *IfcAlignmentVerticalSegment*

</details>

<details><summary>Concept Templates</summary>


These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- Project Context
  - *Project Units*
  - *Project Representation Context*
  - *Project Global Positioning*
- Object Composition
  - *Alignment Decomposition*
  - *Spatial Decomposition*
- Object Connectivity 
  - *Spatial Containment*

</details>

## Model Dataset

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename                                                     | Description                                   |
| ------------------------------------------------------------ | --------------------------------------------- |
| [HorizontalAlignmentParameters](Dataset/HorizontalAlignmentParameters.csv) | Parameters for the horizontal segments as csv |
| [VerticalAlignmentParameters](Dataset/VerticalAlignmentParameters.csv) | Parameters for the vertical segments as csv   |
| [LandXML](Dataset/T616AAC0.ifc)                              | LandXML-file representing the alignment       |

## Test Case Imports

Test instructions are defined with a modular approach to reduce repetition of validation criteria and test content, and improve vendors ability to solve issues and bugs. therefore this test instruction *imports/reuses* the following Test instructions and entities with the relevant associated validation criteria.

No test cases are imported for this test case. All necessary data and criteria are included.

## Expected Results

For certification of capabilities the only source will be:

:construction: under construction :construction:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`-`ExchangeCode`-`TestCode`-`SoftwareVendor`.`ifc` (Example: `IFC4.3_AbRV-E2b-ASTPC-AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet usefull to illustrate test results are:
- Screen-shot of a planar view and a "long section" similar to the provided examples
- CSV export of the horizontal and vertical alignment segment parameters

---

## Validation criteria
## Validation criteria

:zap: For this test case to be considered passed **all capabilities listed in this section**, and **the ones of pre-required tests** shall be verified, with no exception. :zap:

### General

| **RULE ID** | **CRITERIA**                                                 | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | ------------------------------------------------------------ | ------------------------------------------------------------ | -------------------------- | ---------------------- |
| GENE_00     | All validation criteria of precondition's tests shall be verified |                                                              | na                         | na                     |
| GENE_01     | All requested entities (and attributes) exist in file        | As per Entities Table. See [Dataset description](Dataset/README.md) | na                         | na                     |

### Road alignment

**Acceptance criteria**: For the **Railway alignment (without cant)** capability, the validation procedure must verify that **all** the following validation criteria are satisfied.

| **RULE ID** | **CRITERIA**                                             | **VALUE [examples]**   | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | -------------------------------------------------------- | ---------------------- | -------------------------- | ---------------------- |
| SITE_00     | All IfcAlignment shall always be contained in an IfcSite |                        |                            | Spatial Containment    |
| ALIG_00     | Alignment layout structure is verified                   | See steps              |                            | Alignment Layout       |
| ALIG_01     | Number of alignments contained in file                   | [1]                    |                            |                        |
| ALIG_02     | Parameters of alignment segments are verified            | As per Alignment Table |                            |                        |

<details><summary>ALIG_00 steps</summary>




| **STEP ID** | **STEP**                                                     |
| ----------- | ------------------------------------------------------------ |
| ALIG_00.1   | Each IfcAlignment must nest exactly 1 IfcAlignmentHorizontal |
| ALIG_00.2   | Each IfcAlignment must nest at most 1 IfcAlignmentVertical   |
| ALIG_00.3   | Each IfcAlignment must nest exactly 1 IfcAlignmentVertical   |
| ALIG_00.6   | Each IfcAlignmentHorizontal must be nested only by 1 IfcAlignment |
| ALIG_00.7   | Each IfcAlignmentVertical must be nested only by 1 IfcAlignment |
| ALIG_00.9   | Each IfcAlignment must nest only the following entities: IfcAlignmentHorizontal, IfcAlignmentVertical |
| ALIG_00.10  | Each IfcAlignmentHorizontal nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentHorizontalSegment |
| ALIG_00.11  | Each IfcAlignmentVertical nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentVerticalSegment |

</details>

### Spatial (De)Composition


| **RULE ID** | **CRITERIA**                      | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | --------------------------------- | ------------------------------------------------------------ | -------------------------- | ---------------------- |
| SDEC_01     | Spatial decomposition is verified | As per Spatial (De)Composition Table. See [Dataset description](Dataset/README.md) | na                         | Spatial Decomposition  |

> **Acceptance criteria**: For the **Spatial decomposition** capability, the validation procedure must verify that a Parent Element of the requested type aggregates (via `IfcRelAggregates`) exactly a given number of Child Elements of the requested type, no more and no less.

<details><summary>SDEC_01 details: Spatial decomposition is verified</summary>




> - Given a set of elements taken from the [Spatial (De)Composition Table](Dataset/README.md#Dataset/README.md#spatial-decomposition-table)
> - Then the Parent Element, and optionally the Parent Element Type, exists
> - And the Parent Element must aggregate at least a number within [MinSize..MaxSize] of the requested Child Element

</details>

### Spatial Containment

| **RULE ID** | **CRITERIA**                    | **VALUE [examples]**             | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | ------------------------------- | -------------------------------- | -------------------------- | ---------------------- |
| SCON_01     | Spatial containment is verified | As per Spatial Containment Table | na                         | Spatial Containment    |

> **Acceptance criteria**: For the **Spatial containment** capability, the validation procedure must verify that a Spatial Element of the requested type contains (via `IfcRelContainedInSpatialStructure`) exactly a given number of Elements of the requested type, no more and no less.

<details><summary>SCON_01 details: Spatial containment is verified</summary>




> - Given a set of elements taken from the [Spatial Containment Table](Dataset/README.md#Spatial-Containment-Table)
> - Then the Spatial Element, and optionally the Spatial Element Type, exists
> - And the Spatial Element must contain at least a number within [MinSize..MaxSize] of the requested Element

</details>

### Project Setup

| **RULE ID** | **CRITERIA**                                    | **VALUE [examples]** | **ENTITY (if applicable)** | **CT (if applicable)**     |
| ----------- | ----------------------------------------------- | -------------------- | -------------------------- | -------------------------- |
| ORIG_01     | Origin of Coordinate System is set as requested | [(0., 0., 0.)]       |                            | Project Global Positioning |
| ORIG_02     | True north is set as requested                  | [(0., 1., 0.)]       |                            | Project Global Positioning |
| DIST_01     | Unit of measure for all distances               | [meter]              |                            | Project Units              |
| ANGL_01     | Unit of measure all angles                      | [radian]             |                            | Project Units              |
| DIST_02     | Required precision for distances                | [0,0001]             | all alignment segments     | na                         |
| ANGL_02     | Required precision for angles and slope         | [0,000001]           |                            | na                         |

### Project global positioning

| Element          | Attribute        | Value     | Comment |
| ---------------- | ---------------- | --------- | ------- |
| IfcMapConversion | Eastings         | 0         |         |
| IfcMapConversion | Northings        | 0         |         |
| IfcMapConversion | OrthogonalHeight | 0         |         |
| IfcMapConversion | XAxisAbscissa    | 1         |         |
| IfcMapConversion | XAxisOrdinate    | 0         |         |
| IfcMapConversion | Scale            | 1         |         |
| IfcProjectedCRS  | Name             | EPSG:3011 |         |
| IfcProjectedCRS  | GeodeticDatum    | EPSG:6619 |         |
| IfcProjectedCRS  | VerticalDatum    | EPSG:5615 |         |

