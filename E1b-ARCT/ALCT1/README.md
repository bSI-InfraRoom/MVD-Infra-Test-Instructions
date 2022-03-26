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

<details><summary>Semantic Usages, Constraints & Logic</summary>

The following itemised Usages, Constraints & Logic are normative entries within the AbRV MVD and MUST be satisfied to meet the defined validation criteria
</details>

<details><summary>Model Geometry</summary>
The Test case requires the following additional checks related to Model Geometry:


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
| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------------------|----------------------------|
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       | na                         | na                         |
| GENE_01     | All requested entities (and attributes) exist in file             | As per Entities Table | na                         | na                         |


</details>

### Project Setup

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------------------|----------------------------|
| ORIG_01     | Origin of Coordinate System is set as requested                   | [(0., 0., 0.)]        |                            | Project Global Positioning |
| ORIG_02     | True north is set as requested                                    | [(0., 1., 0.)]        |                            | Project Global Positioning |
| DIST_01     | Unit of measure for all distances                                 | [meter]               |                            | Project Units              |
| ANGL_01     | Unit of measure all angles                                        | [radian]              |                            | Project Units              |
| DIST_02     | Required precision for distances                                  | [0,0001]              | all alignment segments     | na                         |
| ANGL_02     | Required precision for angles and slope                           | [0,000001]            |                            | na                         |

### Spatial decomposition

| **RULE ID** | **CRITERIA**                      | **VALUE [examples]**               | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|-----------------------------------|------------------------------------|----------------------------|------------------------|
| SDEC_01     | Spatial decomposition is verified | As per Spatial Decomposition Table | na                         | Spatial Decomposition  |

> **Acceptance criteria**: For the **Spatial decomposition** capability, the validation procedure must verify that a Parent Element of the requested type aggregates (via `IfcRelAggregates`) exactly a given number of Child Elements of the requested type, no more and no less.

**Bullet point example**:
- IfcProject *(Name: Project_1)*
  - IfcSite *(Name: Site_1)*
    - IfcRailway *(Name: Railway_1)*

</details>

### Alignment

<details><summary>Click to expand</summary>

| **RULE ID** | **CRITERIA**                                             | **VALUE [examples]**                           | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|----------------------------------------------------------|------------------------------------------------|----------------------------|------------------------|
| SITE_00     | All IfcAlignment shall always be contained in an IfcSite |                                                |                            | Spatial Containment    |
| ALIG_00     | Alignment layout structure is verified                   | See steps                                      |                            | Alignment Layout       |
| ALIG_01     | Number of alignments contained in file                   | [1]                                            |                            |                        |
| ALIG_02     | Parameters of alignment segments are verified            | As per Alignment Table                         |                            |                        |
| ALIG_03     | Alignment geometric compliance is verified               | As per Alignment geometric compliance document |                            |                        |
| ALIG_04     | Value of the RailHeadDistance along the entire alignment | [1500 mm]                                      | IfcAlignmentCant           |                        |
| ALIG_05     | Shape representation of alignment is verified | Items has exactly 1 [IfcGradientCurve]                                   |   IfcAlignment        |   Axis 3D Geometry                  |
| ALIG_06     | Shape representation of alignment horizontal is verified | Items has exactly 1 [IfcCompositeCurve]                                   |  IfcAlignmentHorizontal        |   Axis 2D Geometry                  |
  | ALIG_07     | Shape representation of alignment vertical is verified | Items has exactly 1 [IfcGradientCurve]                                   |   IfcAlignmentVertical        |   Axis 3D Geometry                  |
  | ALIG_08     | Shape representation of alignment cant is verified | Items has exactly 1 [IfcSegmentedReferenceCurve]                                   |   IfcAlignmentCant        |   Axis 3D Geometry                  |
  | ALIG_09     | Shape representation of alignment segment is verified | Items has exactly 1 [IfcCurveSegment]                                   |   IfcAlignmentSegment        |   Segment Geometry                  |



| **STEP ID** | **STEP**                                                                                                                                           |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| ALIG_00.1   | Each IfcAlignment must nest exactly 1 IfcAlignmentHorizontal                                                                                       |
| ALIG_00.3   | Each IfcAlignment must nest exactly 1 IfcAlignmentVertical                                                                                         |
| ALIG_00.5   | Each IfcAlignment must nest exactly 1 IfcAlignmentCant                                                                                             |
| ALIG_00.6   | Each IfcAlignmentHorizontal must be nested only by 1 IfcAlignment                                                                                  |
| ALIG_00.7   | Each IfcAlignmentVertical must be nested only by 1 IfcAlignment                                                                                    |
| ALIG_00.8   | Each IfcAlignmentCant must be nested only by 1 IfcAlignment                                                                                        |
| ALIG_00.10  | Each IfcAlignmentHorizontal nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentHorizontalSegment         |
| ALIG_00.11  | Each IfcAlignmentVertical nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentVerticalSegment             |
| ALIG_00.12  | Each IfcAlignmentCant nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentCantSegment                     |

</details>

### Spatial containment

| **RULE ID** | **CRITERIA**                    | **VALUE [examples]**             | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|---------------------------------|----------------------------------|----------------------------|------------------------|
| SCON_01     | Spatial containment is verified | As per Spatial Containment Table | na                         | Spatial Containment    |

> **Acceptance criteria**: For the **Spatial containment** capability, the validation procedure must verify that a Spatial Element of the requested type contains (via `IfcRelContainedInSpatialStructure`) exactly a given number of Elements of the requested type, no more and no less.

<details><summary>SCON_01 details: Spatial containment is verified</summary>

> - Given a set of elements taken from the [Spatial Containment Table](#Spatial-Containment-Table)
> - Then the Spatial Element, and optionally the Spatial Element Type, exists
> - And the Spatial Element must contain at least a number within [MinSize..MaxSize] of the requested Element

</details>
___

**Bullet point example**:
- IfcSite *(Name: Site_1)*
  - IfcAlignment *(Name: Alignment_1)*

### Product geometric representation

| **RULE ID** | **CRITERIA**                            | **VALUE [examples]**                     | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-----------------------------------------|------------------------------------------|----------------------------|----------------------------|
| PREP_01     | Geometric representation of products is verified | As per Product Geometric Representation Table |                   | Product Geometric Representation and its subtemplates |

> **Acceptance criteria**: For the **Group Geometric Representation** capability, the validation procedure must verify that a Product of the requested type (and optionally a requested name) has an IfcShapeRepresentation with the requested Representation Identifier, Representation Type and Items.

<details><summary>PREP_01 details:  Geometric representation of products is verified</summary>

> - Given a set of products taken from the [Product Geometric Representation Table](#Product-Geometric-Representation-Table)
> - Then the Product, and optionally the Product Type, exists
> - And the Product must have an IfcShapeRepresentation (via IfcProductDefinitionShape) with the requested Representation Identifier, Representation Type and Items.

</details>

### Product placement

| **RULE ID** | **CRITERIA**                            | **VALUE [examples]**                     | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-----------------------------------------|------------------------------------------|----------------------------|----------------------------|
| PPLA_01     | Placement of products is verified | As per Product Placement Table |                   | Product Placement subtemplates |

> **Acceptance criteria**: For the **Product Placement** capability, the validation procedure must verify that a Product of the requested type (and optionally a requested name) has the requested Object Placement, and optionally the Object Placement has PlacementRelTo reference to the Object Placement of Relative Placement Product with requested Relative Placement Product Type and Relative Placement Product Name.

<details><summary>PPLA_01 details:  Placement of products is verified</summary>

> - Given a set of products taken from the [Product Geometric Representation Table](#Product-Geometric-Representation-Table)
> - Then the Product with Product Type and Product Name, exists
> - And the Product must have Object Placement, and the Object Placement has PlacementRelTo reference to the ObjectPlacement of Relative Placement Product with requested Relative Placement Product Type and Relative Placement Product Name.

</details>



### Project global positioning

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Project global positioning** capability, the validation procedure must verify that there is an IfcMapConversion with the given parameters associated with the IfcGeometricRepresentationContext (via `HasCoordinateOperation`). Furthermore, the IfcMapConversion shall have an association with an IfcProjectedCRS (via `HasCoordinateOperation`) with the given parameters.

| Element          | Attribute        | Value     | Comment |
| ---------------- | ---------------- | --------- | ------- |
| IfcMapConversion | Eastings         | 24525000  |         |
|                  | Northings        | 6876000   |         |
|                  | OrthogonalHeight | 0         |         |
|                  | XAxisAbscissa    | 1         |         |
|                  | XAxisOrdinate    | 0         |         |
|                  | Scale            | 1         |         |
| IfcProjectedCRS  | Name             | EPSG:3878 |         |
|                  | GeodeticDatum    | EPSG:6258 |         |
|                  | VerticalDatum    | EPSG:6150 |         |

</details>
