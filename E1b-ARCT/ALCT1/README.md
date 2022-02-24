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
- Alignment design covers the scenaio that vertical alignment is measured from track center line so left and right cant are reciprocal at each point along alignment
- Alignment design covers the scenario of scissor cant
- Properties for alignment segments

The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

:zap: **This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test** :zap:

## Itemised Roots
*This section lists the primary entities and concept templates being validated by this test instruction, these are listed to understand the scope of the data entities being addressed. this is the documentation of the data placed within BIMQ*

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

:construction: under construction :construction:

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
  
- *Partial Templates* 
  - *Arc Segment*
  - *Clothoid Transition Segment*
  - *Linear Segment*

  

</details>

## Test Case Imports
Test instructions are defined with a modular approach to reduce repetition of validation criteria and test content, and improve vendors ability to solve issues and bugs. therefore this test instruction *imports/reuses* the following Test instructions and entities with the relevant associated validation criteria.

:construction: under construction :construction:

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
| ALCT_01 | Alignment layout structure is verified | Alignment Layout     |             |
| ALCT_02 | Alignment shall be contained in a Site | Spatial Containment  |             |


> 1. Each `IfcAlignment` must nest exactly 1 `IfcAlignmentHorizontal`
> 1. Each `IfcAlignment` must nest at most 1 `IfcAlignmentVertical`
> 1. Each `IfcAlignment` must nest at most 1 `IfcAlignmentCant`  
> 1. Each `IfcAlignmentHorizontal` must nest only `IfcAlignmentHorizontalSegment`
> 1. Each `IfcAlignmentVertical` must nest only `IfcAlignmentVerticalSegment`
> 1. Each `IfcAlignmentCant` must nest only `IfcAlignmentCantSegment`


</details>

<details><summary>Model Geometry</summary>
The Test case requires the following additional checks related to Model Geometry:


| **ID**  | **CRITERIA**                           | **Concept Template** | **COMMENT** |
|---------|----------------------------------------|----------------------|-------------|
| ALCT_03 | Continuity of alignment is verified    | na                   |             |
| ALCT_04 | Consistency between alignment semantics and geometry is verified | na |             |

> 1. The deviation between the end point of an IfcAlignmentHorizontalSegment and the start point of subsequent IfcAlignmentHorizontalSegment must be smaller than 0.0001m.
> 1. The deviation between the end point of an IfcAlignmentVerticalSegment and the start point of subsequent IfcAlignmentVerticalSegment must be smaller than 0.0001m.
> 1. The deviation between the end point of an IfcAlignmentCantSegment and the start point of subsequent IfcAlignmentCantSegment must be smaller than 0.0001m.
> 1. In case of transition code "CONTSAMEGRADIENT", the deviation between the end direction of an IfcAlignmentHorizontalSegment and the start direction of subsequent IfcAlignmentHorizontalSegment must be smaller than 0.000001 radian.
> 1. In case of transition code "CONTSAMEGRADIENT", the deviation between the end direction of an IfcAlignmentVerticalSegment and the start direction of subsequent IfcAlignmentVerticalSegment must be smaller than 0.000001 radian.


> 1. The geometric representation of alignment horizontal (IfcCompositeCurve segments) should be consistent with the semantic counterpart (list of IfcAlignmentHorizontalSegment).
> 1. The geometric representation of alignment horizontal (IfcGradientCurve segments) should be consistent with the semantic counterpart (list of IfcAlignmentVerticalSegment).
> 1. The geometric representation of alignment horizontal (IfcSegmentedReferenceCurve segments) should be consistent with the semantic counterpart (list of IfcAlignmentCantSegment).
- *Constraint*

</details>

## Expected Results

For certification of capabilities the only source will be:

:construction: under construction :construction:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`-`ExchangeCode`-`TestCode`-`SoftwareVendor`.`ifc` (Example: `IFC4.3_AbRV-E2b-ASTPC-AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet useful to illustrate test results are:
- Screen-shot of the alignment in 3D
- Screen-shot of the alignment layouts in 2D
- CSV export of point list of the IfcSegmentedReferenceCurve and IfcGradientCurve

---

## Validation criteria
:zap: For this test case to be considered passed **all capabilities** listed in this section shall be verified, with no exception. :zap:

:construction: under construction :construction:

### General & Imports

<details><summary>Click to expand</summary>

- All the concept templates must be correctly implemented as presented in the validation criteria
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file.
- 1 IfcAlignment instance is expected to be present in the file. The alignment layouts


#### Imports
| **TI Code**        | **Criteria Codes** | *COMMENT**                                         |
|--------------------|--------------------|----------------------------------------------------|
| IFC4.3AbRV_E0_MSTP | ALL CRITERIA       | As outlined in the dataset [Imported Entities Table](Dataset/README.md#Imported-Entities-Table) |


#### General
| **ID**  | **CRITERIA**                                        | **VALUE**                                     | **COMMENT** |
|---------|-----------------------------------------------------|-----------------------------------------------|-------------|
| GENE_01 | All requested entities are present in the IFC model | per [Entities Table](Dataset/README.md#Entities-Table) |    |
| GENE_02 | The model contains exactly 1 IfcAlignment | per [Entities Table](Dataset/README.md#Entities-Table) |    |
| GENE_02 | The IfcAlignment nests exactly 1 IfcAlignmentHorizontal, exactly 1 IfcAlignmentVertical and exactly 1 IfcAlignmentCant | per [Entities Table](Dataset/README.md#Entities-Table) |    |
| GENE_03 | The IfcAlignmentHorizontal nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentHorizontalSegment | per [Entities Table](Dataset/README.md#Entities-Table) |    |
| GENE_04 | The IfcAlignmentVertical nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentVerticalSegment | per [Entities Table](Dataset/README.md#Entities-Table) |    |
| GENE_05 | The IfcAlignmentCant nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentCantSegment | per [Entities Table](Dataset/README.md#Entities-Table) |    |
| GENE_06 | Parameters of alignment segments shall be defined according to the Dataset | per [Entities Table](Dataset/README.md#Entities-Table) |    |
| GENE_07 | Each IfcAlignment should have geometric representation IfcSegmentedReferenceCurve | per [Entities Table](Dataset/README.md#Entities-Table) |    |
| GENE_08 | The EndPoint of IfcSegmentedReferenceCurve shall be present in the model to be checked | per [Entities Table](Dataset/README.md#Entities-Table) |    |
| GENE_09 | The EndPoint of IfcGradientCurve shall be present in the model to be checked | per [Entities Table](Dataset/README.md#Entities-Table) |    |

</details>

### Some Concept Group

<details><summary>Click to expand</summary>
Criteria around the representation of 'Some Concept'

| **ID**  | **CRITERIA**                                        | **VALUE**                                | **COMMENT** |
|---------|-----------------------------------------------------|------------------------------------------|-------------|
| XXXX_01 | A Criteria to follow                                | its expected value or outcome             |             |

</details>
