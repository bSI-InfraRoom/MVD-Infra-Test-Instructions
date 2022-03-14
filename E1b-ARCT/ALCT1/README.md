# Test Instruction

| Documentation Code   | Title                                          | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|------------------------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E1b_ALCT1   | Alignment Railway Cant 1                     | E1b      | ALCT1     | Chi Zhang       | SBB        | 1.0     | 10.02.2022 |


## Summary (Intent)

This test instruction is defined for IFC4.3AbRV_E1b_ALCT1 Alignment Railway Cant 1.

This test instruction covers following subjects:
- Project setup including units, context and global position
- Minimum set of spatial structure 
- One alignment for railway including horizontal, vertical and cant layouts
- Alignment segments including linear segments, circular arc segments and clothoid transition segments
- Alignment design covers the scenario that vertical alignment is measured from track center line so left and right cant are reciprocal at each point along alignment
- Alignment design covers the scenario of scissor cant
- Properties for alignment segments

The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

:zap: **This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test** :zap:

## Itemised Roots
*This section lists the primary entities and concept templates being validated by this test instruction, these are listed to understand the scope of the data entities being addressed. this is the documentation of the data placed within BIMQ*

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- *Rooted entities*
  - *IfcProject*
  - *IfcSite*
  - *IfcAlignment*
  - *IfcAlignmentSegment*
  - *IfcAlignmentHorizontal*
  - *IfcAlignmentVertical*
  - *IfcAlignmentCant*
  
- *Non-Rooted entities*
  - *IfcMapConversion*
  - *IfcProjectedCRS*
  - *IfcUnitAssignment*
  - *IfcSIUnit*
  - *IfcAlignmentHorizontalSegment*
  - *IfcAlignmentVerticalSegment*
  - *IfcAlignmentCantSegment*
  - *IfcAxis2Placement2D*
  - *IfcAxis2Placement3D*
  - *IfcCircle*
  - *IfcClothoid*
  - *IfcCompositeCurve*
  - *IfcCurveSegment*
  - *IfcLine*
  - *IfcLocalPlacement*
  - *IfcGeometricRepresentationContext*
  - *IfcGeometricRepresentationSubContext*
  - *IfcGradientCurve*
  - *IfcProductDefinitionShape*
  - *IfcShapeRepresentation*


  

</details>

<details><summary>Concept Templates</summary>

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- *Rooted Templates*
  - *Project Units*
  - *Project Representation Context*
  - *Project Global Positioning*
  - *Spatial Decomposition*
  - *Spatial Composition*
  - *Spatial Container*
  - *Alignment Layout*
  - *Alignment Geometry Cant*
  - *Property Sets for Objects*
  - *Object User Identity*
  - *Software Identity*
  
- *Partial Templates* 
  - *Arc Segment*
  - *Clothoid Transition Segment*
  - *Linear Segment*

  

</details>

## Test Case Imports
Test instructions are defined with a modular approach to reduce repetition of validation criteria and test content, and improve vendors ability to solve issues and bugs. therefore this test instruction *imports/reuses* the following Test instructions and entities with the relevant associated validation criteria.

<details><summary>Imports & Reuses</summary>

| TI Code                                  | Test Instruction Title    | Comments                     |
|------------------------------------------|---------------------------|------------------------------|
| [IFC4.3AbRV_E0_MSTP](../../E0-SCFD/MSTP) | Model Setup & Positioning | PROJ-01 imported along with RCTX-01 and associated configuration and history data |

</details>

## Usages, Constraints & Logic
The following itemised restrictions and constraints shall be placed on IFC Entities & Concept Templates:

:construction: under construction :construction:

<details><summary>Semantic Usages, Constraints & Logic</summary>

The following itemised Usages, Constraints & Logic are normative entries within the AbRV MVD and MUST be satisfied to meet the defined validation criteria

| **ID**  | **CRITERIA**                           | **Concept Template** | **COMMENT** |
|---------|----------------------------------------|----------------------|-------------|
| ALIG_00 | Alignment layout structure is verified | Alignment Layout     |             |
| ALSC_00 | Alignment shall be contained in a Site | Spatial Containment  |             |
| ALGR_00 | Alignment elements should have the correct shape representation | Product Geometric Representation |          |

ALIG_00: Alignment layout structure is verified
> 1. Each `IfcAlignment` must nest exactly 1 `IfcAlignmentHorizontal`
> 1. Each `IfcAlignment` must nest at most 1 `IfcAlignmentVertical`
> 1. Each `IfcAlignment` must nest at most 1 `IfcAlignmentCant`  
> 1. Each `IfcAlignmentHorizontal` must nest only `IfcAlignmentSegment` that has design parameters defined by 'IfcAlignmentHorizontalSegment'
> 1. Each `IfcAlignmentVertical` must nest only `IfcAlignmentSegment' that has design parameters defined by 'IfcAlignmentVerticalSegment'
> 1. Each `IfcAlignmentCant` must nest only `IfcAlignmentSegment` that has design parameters defined by 'IfcAlignmentCantSegment'

ALSC_00: Alignment shall be contained in a Site
> 1. Each 'IfcAlignment' must be contained in 1 'IfcSite'
  
ALGR_00: Alignment and nested elements should have the correct shape representation
> 1. Each 'IfcAlignment' should have a shape representation, with representation identifier set to 'Axis', representation type set to 'Curve3D', and geometric item as 'IfcGradientCurve'
> 1. Each 'IfcAlignmentSegment' should have a shape representation, with representation identifier set to 'Axis', representation type set to 'Segment', and geometric item as 'IfcCurveSegment'
> 1. Each 'IfcAlignmentHorizontal' should have a shape representation, with representation identifier set to 'Axis', representation type set to 'Curve2D', and geometric item as 'IfcCompositeCurve'
> 1. Each 'IfcAlignmentVertical' should have a shape representation, with representation identifier set to 'Axis', representation type set to 'Curve3D', and geometric item as 'IfcGradientCurve'
> 1. Each 'IfcAlignmentCant' should have a shape representation, with representation identifier set to 'Axis', representation type set to 'Curve3D', and geometric item as 'IfcSegmentedReferenceCurve'

</details>

<details><summary>Model Geometry</summary>
The Test case requires the following additional checks related to Model Geometry:


| **ID**  | **CRITERIA**                           | **Concept Template** | **COMMENT** |
|---------|----------------------------------------|----------------------|-------------|
| ALGM_00 | Continuity of alignment is verified    | na                   |             |
| ALGM_01 | Consistency between alignment semantics and geometry is verified | na |             |

ALGM_00: Continuity of alignment is verified
> 1. The deviation between the end point of an 'IfcAlignmentHorizontalSegment' and the start point of subsequent 'IfcAlignmentHorizontalSegment' must be smaller than 0.00001m.
> 1. The deviation between the end point of an 'IfcAlignmentVerticalSegment' and the start point of subsequent 'IfcAlignmentVerticalSegment' must be smaller than 0.00001m.
> 1. The deviation between the end point of an 'IfcAlignmentCantSegment' and the start point of subsequent 'IfcAlignmentCantSegment' must be smaller than 0.00001m.
> 1. In case of transition code "CONTSAMEGRADIENT", the deviation between the end direction of an IfcAlignmentHorizontalSegment and the start direction of subsequent IfcAlignmentHorizontalSegment must be smaller than 0.000001 radian.
> 1. In case of transition code "CONTSAMEGRADIENT", the deviation between the end direction of an IfcAlignmentVerticalSegment and the start direction of subsequent IfcAlignmentVerticalSegment must be smaller than 0.000001 radian.

ALGM_01: Consistency between alignment semantics and geometry is verified
> 1. The geometric representation of alignment horizontal (IfcCompositeCurve segments) should be consistent with the semantic counterpart (list of IfcAlignmentHorizontalSegment).
> 1. The geometric representation of alignment horizontal (IfcGradientCurve segments) should be consistent with the semantic counterpart (list of IfcAlignmentVerticalSegment).
> 1. The geometric representation of alignment horizontal (IfcSegmentedReferenceCurve segments) should be consistent with the semantic counterpart (list of IfcAlignmentCantSegment).
- *Constraint*

</details>

## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`-`ExchangeCode`-`TestCode`-`SoftwareVendor`.`ifc` (Example: `IFC4.3_AbRV-E2b-ASTPC-AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet useful to illustrate test results are:
- Screen-shot of the alignment in 3D
- Screen-shot of the alignment layouts in 2D
- CSV export of point list of the IfcSegmentedReferenceCurve and IfcGradientCurve

---

## Validation criteria
:zap: For this test case to be considered passed **all capabilities** listed in this section shall be verified, with no exception. :zap:

### General & Imports

<details><summary>Click to expand</summary>

- All the concept templates must be correctly implemented as presented in the validation criteria
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file.
- 1 IfcAlignment instance is expected to be present in the file.


#### Imports
| **TI Code**        | **Criteria Codes** | *COMMENT**                                         |
|--------------------|--------------------|----------------------------------------------------|
| IFC4.3AbRV_E0_MSTP | ALL CRITERIA       | As outlined in the dataset [Imported Entities Table](Dataset/README.md#Imported-Entities-Table) |


#### General
| **ID**  | **CRITERIA**                                        | **VALUE**                                     | **COMMENT** |
|---------|-----------------------------------------------------|-----------------------------------------------|-------------|
| GENE_00 | All requested entities are present in the IFC model | per [Entities Table](Dataset/README.md#Entities-Table) |    |
| GENE_01 | All rules defined in [Usages, Constraints & Logic](## Usages, Constraints & Logic) are verified |  |    |


</details>


### Spatial decomposition

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Spatial decomposition** capability, the validation procedure must verify that a Spatial Element of the requested type is decomposed by (via `IfcRelAggregates`) exactly a given number of Spatial Elements of the requested type, no more and no less.


| **ID**  | **CRITERIA**                                                 | **VALUE**                                      | **COMMENT** |
| ------- | ------------------------------------------------------------ | ---------------------------------------------- | ----------- |
| SD_01 | Decomposition of IfcProject                                    | 1 IfcSite                                      |             |
| SD_02 | Decomposition of IfcSite                                       | 1 IfcRailway                                   |             |

</details>

### Alignment

<details><summary>Click to expand</summary>


| **ID**  | **CRITERIA**                                                 | **VALUE**                                      | **COMMENT** |
| ------- | ------------------------------------------------------------ | ---------------------------------------------- | ----------- |
| ALIG_01 | Alignments contained in file                                 | 1                                              |             |
| ALIG_02 | Elements nested in Alignment                                     | exactly 1 horizontal, exactly 1 vertical, and exactly 1 cant                      |             |
| ALIG_03 | The horizontal layout matches exactly the layout specified in the [Dataset description](./Dataset/README.md) | See [Dataset description](./Dataset/README.md) |             |
| ALIG_04 | The vertical layout matches exactly the layout specified in the [Dataset description](./Dataset/README.md) | See [Dataset description](./Dataset/README.md) |             |
| ALIG_05 | The cant layout matches exactly the layout specified in the [Dataset description](./Dataset/README.md) | See [Dataset description](./Dataset/README.md) |             |
| ALIG_06 | The EndPoint of IfcSegmentedReferenceCurve shall be present in the model to be checked |  |    |
| ALIG_07 | The EndPoint of IfcGradientCurve shall be present in the model to be checked |  |    |
| ALIG_08 | The IfcSegmentedReferenceCurve shall have the IfcGradientCurve as BaseCurve |         |             |
| ALIG_09 | The IfcGradientCurve shall have the IfcCompositeCurve as BaseCurve |         |             |

</details>

### Spatial containment

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Spatial containment** capability, the validation procedure must verify that a Spatial Element of the requested type contains (via `IfcRelContainedInSpatialStructure`) exactly a given number of Elements of the requested type, no more and no less.


| **ID**  | **CRITERIA**                                                 | **VALUE**                                      | **COMMENT** |
| ------- | ------------------------------------------------------------ | ---------------------------------------------- | ----------- |
| SC_01 | Spatial containment of IfcAlignment                                | 1  IfcSite                                            |             |

</details>

### Project global positioning

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Project global positioning** capability, the validation procedure must verify that there is an IfcMapConversion with the given parameters associated with the IfcGeometricRepresentationContext (via `HasCoordinateOperation`). Furthermore, the IfcMapConversion shall have an association with an IfcProjectedCRS (via `HasCoordinateOperation`) with the given parameters.




| Element          | Attribute        | Value     | Comment |
| ---------------- | ---------------- | --------- | ------- |
| IfcMapConversion | Eastings         | 24525000  |         |
| IfcMapConversion | Northings        | 6876000   |         |
| IfcMapConversion | OrthogonalHeight | 0         |         |
| IfcMapConversion | XAxisAbscissa    | 1         |         |
| IfcMapConversion | XAxisOrdinate    | 0         |         |
| IfcMapConversion | Scale            | 1         |         |
| IfcProjectedCRS  | Name             | EPSG:3878 |         |
| IfcProjectedCRS  | GeodeticDatum    | EPSG:6258 |         |
| IfcProjectedCRS  | VerticalDatum    | EPSG:6150 |         |

</details>
