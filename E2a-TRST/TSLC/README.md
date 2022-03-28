# Test Instructions

| Documentation Code   | Title                                          | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|------------------------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_TSLC   | Track Structures Level Crossing               | E2a-TRST      | TSLC      |                 | FTIA      | 1.0     | 07.03.2022 |


## Summary (Intent)

This test case is defined for IFC4.3 AbRV_E2a_TSLC Track Structures Level Crossing. The basis for the test instruction is taken from the [Level Crossing Storyline](https://github.com/IFCRail/IFC-Rail-Unit-Test/tree/master/8_Storylines%20Test%20(SL)/SL08_Level%20Crossing).  

The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

:zap: **This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test** :zap:

## Itemised Roots
The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_E2a exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Model setup
  - *IfcProject*
  - *IfcSite*
  - *IfcRailway*
  - *IfcRoad*
  - *IfcFacilityPart/IfcRailwayPart/IfcRoadPart*
  - *IfcUnitAssignment*
  - *IfcGeometricRepresentationContext*
  - *IfcMapConversion*
  - *IfcProjectedCRS*
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
  - *IfcClothoid*
- Boom barrier
  - Signal assembly
    - *IfcMember*
    - *IfcSignal*
    - *IfcSign*
  - *IfcDoor*
  - *IfcFooting*
  - *IfcRailing*
  
- Signaling equipment
  - *IfcSensor* (axle counters)
  - *IfcDiscreteAccessory* (snow plough protection)
  - *IfcJunctionBox*

</details>

<details><summary>Concept Templates</summary>

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- *Model setup*
  - *Project Units*
  - *Project Representation Context*
  - *Project Global Positioning*
- *Spatial structure, spatial interference and spatial containment*
  - *Spatial Decomposition*
  - *Spatial Interference*
  - *Spatial Container*
- *Alignment*
  - *Alignment Decomposition*
  - *Alignment Geometry Gradient*
- *Element composition*
  - *Element Composition*
  - *Element Decomposition*

- *Product placement and relative positioning*
  - *Product Linear Placement*
  - *Product Local Placement*
  - *Product Relative Positioning*
- *Other (missing in this spec at the moment)*
  - *(Material Constituent Set)*
  - *(Object Typing)*

</details>

## Model Dataset

This test case utilises the datasets collected in the Dataset folder. **For more details on each item and a specification and model structure see [Dataset description](Dataset/README.md).**

## Test Case Imports

Test instructions are defined with a modular approach to reduce repetition of validation criteria and test content, and improve vendors ability to solve issues and bugs. therefore this test instruction *imports/reuses* the following Test instructions and entities with the relevant associated validation criteria.

<details><summary>Imports & Reuses</summary>

| TI Code                                  | Test Instruction Title    | Comments                     |
|------------------------------------------|---------------------------|------------------------------|
| [IFC4.3AbRV_E0_MSTP](../../E0-SCFD/MSTP) | Model Setup & Positioning | PROJ-01 imported along with RCTX-01 and associated configuration and history data |

</details>

## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`-`ExchangeCode`-`TestCode`-`SoftwareVendor`.`ifc` (Example: `IFC4.3_AbRV-E2b-ASTPC-AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet useful to illustrate test results are:
- Screen-shot of the model with all elements clearly visible
- CSV export of the linear, local and global (map) coordinates for each element

---

## Validation criteria
:zap: For this test case to be considered passed **all capabilities** listed in this section shall be verified, with no exception. :zap:

### General

| **RULE ID** | **CRITERIA**                                                 | **VALUE [examples]**                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | ------------------------------------------------------------ | -------------------------------------------- | -------------------------- | ---------------------- |
| GENE_00     | All validation criteria of precondition's tests shall be verified |                                              | na                         | na                     |
| GENE_01     | All requested entities (and attributes) exist in file        | see [Dataset description](Dataset/README.md) | na                         | na                     |

### Project Setup

| **RULE ID** | **CRITERIA**                                    | **VALUE [examples]** | **ENTITY (if applicable)** | **CT (if applicable)**     |
| ----------- | ----------------------------------------------- | -------------------- | -------------------------- | -------------------------- |
| ORIG_01     | Origin of Coordinate System is set as requested | [(0., 0., 0.)]       |                            | Project Global Positioning |
| ORIG_02     | True north is set as requested                  | [(0., 1., 0.)]       |                            | Project Global Positioning |
| DIST_01     | Unit of measure for all distances               | [meter]              |                            | Project Units              |
| ANGL_01     | Unit of measure all angles                      | [radian]             |                            | Project Units              |
| DIST_02     | Required precision for distances                | [0,0001]             | all alignment segments     | na                         |
| ANGL_02     | Required precision for angles and slope         | [0,000001]           |                            | na                         |

### Spatial (De)Composition

| **RULE ID** | **CRITERIA**                      | **VALUE [examples]**                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | --------------------------------- | -------------------------------------------- | -------------------------- | ---------------------- |
| SDEC_01     | Spatial decomposition is verified | See [Dataset description](Dataset/README.md) | na                         | Spatial Decomposition  |

> **Acceptance criteria**: For the **Spatial decomposition** capability, the validation procedure must verify that a Parent Element of the requested type aggregates (via `IfcRelAggregates`) exactly a given number of Child Elements of the requested type, no more and no less.

<details><summary>SDEC_01 details: Spatial decomposition is verified</summary>


> - Given a set of elements taken from the [Spatial (De)Composition Table](#Spatial-(De)Composition-Table)
> - Then the Parent Element, and optionally the Parent Element Type, exists
> - And the Parent Element must aggregate at least a number within [MinSize..MaxSize] of the requested Child Element

</details>

### Spatial Interference

<details><summary>Click to expand</summary>

> **Acceptance criteria**: For the **Spatial interference** capability, the validation procedure must verify that a Spatial Element of the requested type interferes with (via `IfcRelInterferesElements`) a Spatial Element of the requested type.

| ID      | CRITERIA                                                     | VALUE                                                  | COMMENT |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------ | ------- |
| SPIF_00 | There shall be one IfcRelInterferesElements relationship relating the two IfcFacilityPart instances typed as LEVELCROSSING. The IfcRelInterferesElements.InterferenceType shall have the value 'Crosses'. | per [Entities Table](Dataset/README.md#Entities-Table) |         |

</details>

### Alignment

| **RULE ID** | **CRITERIA**                                             | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | -------------------------------------------------------- | ------------------------------------------------------------ | -------------------------- | ---------------------- |
| SITE_00     | All IfcAlignment shall always be contained in an IfcSite |                                                              |                            | Spatial Containment    |
| ALIG_00     | Alignment layout structure is verified                   | See steps                                                    |                            | Alignment Layout       |
| ALIG_01     | Number of alignments contained in file                   | [2]                                                          |                            |                        |
| ALIG_02     | Parameters of alignment segments are verified            | As per Alignment Table. See [Dataset description](Dataset/README.md) |                            |                        |
| ALIG_03     | Alignment geometric compliance is verified               | As per Alignment geometric compliance document               |                            |                        |

<details><summary>ALIG_00 steps</summary>


| **STEP ID** | **STEP**                                                     |
| ----------- | ------------------------------------------------------------ |
| ALIG_00.1   | Each IfcAlignment must nest exactly 1 IfcAlignmentHorizontal |
| ALIG_00.2   | Each IfcAlignment must nest at most 1 IfcAlignmentVertical   |
| ALIG_00.3   | Each IfcAlignment must nest exactly 1 IfcAlignmentVertical   |
| ALIG_00.6   | Each IfcAlignmentHorizontal must be nested only by 1 IfcAlignment |
| ALIG_00.7   | Each IfcAlignmentVertical must be nested only by 1 IfcAlignment |
| ALIG_00.8   | Each IfcAlignmentCant must be nested only by 1 IfcAlignment  |
| ALIG_00.9   | Each IfcAlignment must nest only the following entities: IfcAlignmentHorizontal, IfcAlignmentVertical |
| ALIG_00.10  | Each IfcAlignmentHorizontal nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentHorizontalSegment |
| ALIG_00.11  | Each IfcAlignmentVertical nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentVerticalSegment |

</details>

### Product geometric representation

| **RULE ID** | **CRITERIA**                                     | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)**                                |
| ----------- | ------------------------------------------------ | ------------------------------------------------------------ | -------------------------- | ----------------------------------------------------- |
| PREP_01     | Geometric representation of products is verified | As per Product Geometric Representation Table. See [Dataset description](Dataset/README.md) |                            | Product Geometric Representation and its subtemplates |

> **Acceptance criteria**: For the **Group Geometric Representation** capability, the validation procedure must verify that a Product of the requested type (and optionally a requested name) has an IfcShapeRepresentation with the requested Representation Identifier, Representation Type and Items.

<details><summary>PREP_01 details:  Geometric representation of products is verified</summary>


> - Given a set of products taken from the [Product Geometric Representation Table](#Product-Geometric-Representation-Table)
> - Then the Product, and optionally the Product Type, exists
> - And the Product must have an IfcShapeRepresentation (via IfcProductDefinitionShape) with the requested Representation Identifier, Representation Type and Items.

</details>

### Spatial containment

| **RULE ID** | **CRITERIA**                    | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | ------------------------------- | ------------------------------------------------------------ | -------------------------- | ---------------------- |
| SCON_01     | Spatial containment is verified | As per Spatial Containment Table. See [Dataset description](Dataset/README.md) | na                         | Spatial Containment    |

> **Acceptance criteria**: For the **Spatial containment** capability, the validation procedure must verify that a Spatial Element of the requested type contains (via `IfcRelContainedInSpatialStructure`) exactly a given number of Elements of the requested type, no more and no less.

<details><summary>SCON_01 details: Spatial containment is verified</summary>


> - Given a set of elements taken from the [Spatial Containment Table](#Spatial-Containment-Table)
> - Then the Spatial Element, and optionally the Spatial Element Type, exists
> - And the Spatial Element must contain at least a number within [MinSize..MaxSize] of the requested Element

</details>

### Element (De)Composition (Assemblies)

| **RULE ID** | **CRITERIA**                                       | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)**                      |
| ----------- | -------------------------------------------------- | ------------------------------------------------------------ | -------------------------- | ------------------------------------------- |
| ASSE_01     | Mandatory components are present in the assemblies | As per Element (De)Composition Table. See [Dataset description](Dataset/README.md) | na                         | Element Composition & Element Decomposition |

> **Acceptance criteria**: For the **ASSE_01 rule**, the validation procedure must verify that an assembly of the requested type (and name) aggregates (via `IfcRelAggregates`) at least a given number of elements of the requested type (and name).

<details><summary>ASSE_01 details: Mandatory components are present in the assemblies</summary>


> - Given a set of assemblies taken from the [Element (De)Composition Table](#Element-(De)Composition)
> - Then the Assembly, and optionally the Assembly Type, exists
> - And the Assembly must aggregate at least a number within [MinSize..MaxSize] of the requested Element

</details>

### Product placement

| **RULE ID** | **CRITERIA**                                                 | **VALUE [examples]**           | **ENTITY (if applicable)** | **CT (if applicable)**         |
| ----------- | ------------------------------------------------------------ | ------------------------------ | -------------------------- | ------------------------------ |
| PPLA_01     | Placement of products is verified                            | As per Product Placement Table |                            | Product Placement subtemplates |
| PPLA_02     | For a product that has ObjectPlacement as IfcLinearPlacement, the CartesianPosition of IfcLinearPlacement shall be available | depends on cases               |                            | Product Linear Placement       |

> **Acceptance criteria**: For the **Product Placement** capability, the validation procedure must verify that a Product of the requested type (and optionally a requested name) has the requested Object Placement, and optionally the Object Placement has PlacementRelTo reference to the Object Placement of Relative Placement Product with requested Relative Placement Product Type and Relative Placement Product Name.

<details><summary>PPLA_01 details:  Placement of products is verified</summary>


> - Given a set of products taken from the [Product Geometric Representation Table](#Product-Geometric-Representation-Table)
> - Then the Product with Product Type and Product Name, exists
> - And the Product must have Object Placement, and the Object Placement has PlacementRelTo reference to the ObjectPlacement of Relative Placement Product with requested Relative Placement Product Type and Relative Placement Product Name.

</details>

### Product relative positioning

| **RULE ID** | **CRITERIA**                             | **VALUE [examples]**                      | **ENTITY (if applicable)** | **CT (if applicable)**                                 |
| ----------- | ---------------------------------------- | ----------------------------------------- | -------------------------- | ------------------------------------------------------ |
| PPOS_01     | Product relative positioning is verified | As per Product Relative Positioning Table | na                         | Product Relative Positioning, Product Span Positioning |

> **Acceptance criteria**: For the **Spatial relative positioning** capability, the validation procedure must verify that a Product of the requested type is positioned (via `IfcRelPositions`) exactly a given number of Positioning Elements of the requested type, no more and no less.

<details><summary>PPOS_01 details: Product relative positioning is verified</summary>


> - Given a set of products taken from the [Product Relative Positioning Table](#Product-Relative-Positioning-Table)
> - Then the Product, and optionally the Product Type, exists
> - And the Product must be positioned on exactly [Size] of the requested Positioning Element

</details>

### Project global positioning

<details><summary>Click to expand</summary>

> **Acceptance criteria**: For the **Project global positioning** capability, the validation procedure must verify that there is an IfcMapConversion with the given parameters associated with the IfcGeometricRepresentationContext (via `HasCoordinateOperation`). Furthermore, the IfcMapConversion shall have an association with an IfcProjectedCRS (via `HasCoordinateOperation`) with the given parameters.
The parameters below shall be used for Project Global Positioning.

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
| IfcProjectedCRS  | VerticalDatum    | EPSG:3900 |         |

</details>

