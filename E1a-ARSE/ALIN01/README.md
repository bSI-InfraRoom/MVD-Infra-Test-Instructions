# Test Instruction

| Documentation Code    | Title                           | Exchange Code | Test Code | Author        | Data Owner | Version | Date       |
| --------------------- | ------------------------------- | ------------- | --------- | ------------- | ---------- | ------- | ---------- |
| IFC4.3AbRV_E1a_ALIN01 | Alignment Infrastructure Curves | E1a           | ALIN01    | Lars Wikström | FTIA       | 1.0     | 07.01.2022 |


## Summary (Intent)

With these instructions the infrastructure (e.g. Road) alignment exchange is established.

| Info                         |                                       |
| ---------------------------- | ------------------------------------- |
| Number of alignment(s)       | 1                                     |
| Properties of segments       | no                                    |
| Horizontal layout            | Straight Line, Circular Arc, Clothoid |
| Vertical layout              | Straight Line, Circular Arc           |
| Geometric representation     | No                                    |
| IFC reference file available | Yes                                   |

The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

:zap: **This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test** :zap:

## Itemised Roots
*This section lists the primary entities and concept templates being validated by this test instruction, these are listed to understand the scope of the data entities being addressed. this is the documentation of the data placed within BIMQ*

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

:construction: under construction :construction:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- Inherited from imported tests
  - Model setup
    - *IfcProject*
    - *IfcRepresentationContext*
    - *IfcMapConversion*
    - *IfcProjectedCRS*
    - *IfcUnitAssignment*
  - Spatial structure
    - *IfcSite*
    - *IfcRoad*
- For this test instruction
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

- Inherited from imported tests:
  - *Project Units*
  - *Project Representation Context*
  - *Project Global Positioning*
  - *Spatial Decomposition*
  - *Spatial Composition*
  - *Spatial Container*
  - *Project Global Positioning*
- For this test instruction
  - *Alignment Decomposition*
  - *Spatial Containment*

</details>

## Test Case Imports
Test instructions are defined with a modular approach to reduce repetition of validation criteria and test content, and improve vendors ability to solve issues and bugs. therefore this test instruction *imports/reuses* the following Test instructions and entities with the relevant associated validation criteria.

:construction: under construction :construction:

<details><summary>Imports & Reuses</summary>

| TI Code                                  | Test Instruction Title  | Comments                                                     |
| ---------------------------------------- | ----------------------- | ------------------------------------------------------------ |
| [IFC4.3AbRV_E0_SSRD](../../E0-SSRD/SSRD) | Spatial Structures Road | Spatial structure for road incuding the dependencies (E0_SSSI, E0_MSTP) |

</details>

## Usages, Constraints & Logic
The following itemised restrictions and constraints shall be placed on IFC Entities & Concept Templates:

:construction: under construction :construction:

<details><summary>Semantic Usages, Constraints & Logic</summary>
The following itemised Usages, Constraints & Logic are normative entries within the AbRV MVD and MUST be satisfied to meet the defined validation criteria

| **ID**  | **CRITERIA**                                  | **VALUE**                           | **COMMENT** |
| ------- | --------------------------------------------- | ----------------------------------- | ----------- |
| ALIG_00 | Alignment layout structure is verified        | See below for further specification |             |
| SITE_00 | Alignment shall always be contained in a Site | na                                  |             |

ALIG_00: Alignment layout structure is verified

> 1. Each `IfcAlignment` must nest exactly 1 `IfcAlignmentHorizontal`
> 2. Each `IfcAlignment` must nest at most 1 `IfcAlignmentVertical`
> 3. Each `IfcAlignmentHorizontal` must be nested only by 1 `IfcAlignment`
> 4. Each `IfcAlignmentVertical` must be nested only by 1 `IfcAlignment`
> 5. Each `IfcAlignment` must nest only `IfcAlignmentHorizontal`, or `IfcAlignmentVertical`
> 6. Each `IfcAlignmentHorizontal` must nest only `IfcAlignmentHorizontalSegment`
> 7. Each `IfcAlignmentVertical` must nest only `IfcAlignmentVerticalSegment`
> 8. Each `IfcAlignmentHorizontalSegment` must be nested only by 1 `IfcAlignmentHorizontal`
> 9. Each `IfcAlignmentVerticalSegment` must be nested only by 1 `IfcAlignmentVertical`

- </details>

<details><summary>Model Geometry</summary>
The Test case requires no additional checks related to Model Geometry

</details>

## Expected Results

For certification of capabilities the only source will be:

:construction: under construction :construction:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`-`ExchangeCode`-`TestCode`-`SoftwareVendor`.`ifc` (Example: `IFC4.3_AbRV-E2b-ASTPC-AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet usefull to illustrate test results are:
- Screen-shot of a planar view and a "long section" similar to the provided examples
- CSV export of the horizontal and vertical alignment segment parameters

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

### Road alignment

<details><summary>Click to expand</summary>

| **ID**  | **CRITERIA**                                                 | **VALUE**                                      | **COMMENT** |
| ------- | ------------------------------------------------------------ | ---------------------------------------------- | ----------- |
| ALIG_01 | Alignments contained in file                                 | 1                                              |             |
| ALIG_02 | Components for Alignment                                     | 1 horizontal, 1 vertical                       |             |
| ALIG_03 | The horizontal (H) layout matches exactly the layout specified in the [Dataset description](./Dataset/README.md) | See [Dataset description](./Dataset/README.md) |             |
| ALIG_04 | The vertical (V) layout matches exactly the layout specified in the [Dataset description](./Dataset/README.md) | See [Dataset description](./Dataset/README.md) |             |

</details>
### Spatial containment

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Spatial containment** capability, the validation procedure must verify that a Spatial Element of the requested type contains (via `IfcRelContainedInSpatialStructure`) exactly a given number of Elements of the requested type, no more and no less.

| Spatial Element | Spatial Element Type | Minimum | Maximum | Element      | Element Type   |
| --------------- | -------------------- | ------- | ------- | ------------ | -------------- |
| IfcSite         |                      | 1       | 1       | IfcAlignment | Road alignment |

</details>

### Project global positioning

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Project global positioning** capability, the validation procedure must verify that there is an IfcMapConversion with the given parameters associated with the IfcGeometricRepresentationContext (via `HasCoordinateOperation`). Furthermore, the IfcMapConversion shall have an association with an IfcProjectedCRS (via `HasCoordinateOperation`) with the given parameters.


| Element          | Attribute        | Value     | Comment |
| ---------------- | ---------------- | --------- | ------- |
| IfcMapConversion | Eastings         | 24474600  |         |
| IfcMapConversion | Northings        | 6655000   |         |
| IfcMapConversion | OrthogonalHeight | 0         |         |
| IfcMapConversion | XAxisAbscissa    | 1         |         |
| IfcMapConversion | XAxisOrdinate    | 0         |         |
| IfcMapConversion | Scale            | 1         |         |
| IfcProjectedCRS  | Name             | EPSG:3878 |         |
| IfcProjectedCRS  | GeodeticDatum    | EPSG:6258 |         |
| IfcProjectedCRS  | VerticalDatum    | EPSG:3900 |         |

</details>