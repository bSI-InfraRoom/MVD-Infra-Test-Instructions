# Test Instruction

| Documentation Code  | Title                                         | Exchange Code | Test Code | Author        | Data Owner | Version | Date       |
| ------------------- | --------------------------------------------- | ------------- | --------- | ------------- | ---------- | ------- | ---------- |
| IFC4.3AbRV_E2_EWAJN | Aggregate Structures on Alignment - Junctions | E2            | EWAJN     | Lars Wikström | FTIA       | 1.0     | 14.11.2022 |


## Summary (Intent)

With these instructions the Aggregate structures on Alignment - Junctions exchange is established.

The test instruction specifies a dataset including two intersecting roads in a T junction (a secondary road ending at and joining a primary road).

The test instruction includes the main alignments for the primary and the secondary roads and alignments for the pavement edges where the two roads meet. In addition to these, an alignment is defined to separate the pavements belonging to the primary road from the pavements belonging to the secondary road.

For each road, the pavements aggregates of a couple of courses that are represented by IfcFacetedBrep. 

- Refer to [Test Case Imports](#Test-Case-Imports) to know the prerequisites for the present test.

- The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

- :zap: This is a test-driven process: refer to the [Validation Criteria](#validation-criteria) to understand what is required by the test :zap:

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
  - *IfcCompositeCurve*
  - *IfcGradientCurve*
  - *IfcCurveSegment*
  - *IfcLine*
  - *IfcCircle*
- Physical objects

  - *IfcPavement*
  - *IfcCourse*
- Properties
  - *IfcPropertySet*
  - *IfcPropertySingleValue*
  - *IfcPropertyEnumeratedValue*
- Product shape
  - *IfcLinearPlacement*
  - *IfcLocalPlacement*
  - *IfcFacetedBrep*

</details>

<details><summary>Concept Templates</summary>

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- Project Context
  - *Project Units*
  - *Project Representation Context*
  - *Project Global Positioning*
- Nesting
  - *Alignment layout*
- Object Composition
  - *Spatial Decomposition*
  - *Element Decomposition*
- Object Connectivity 
  - *Spatial Containment*
- Object definition
  - *Object typing*
  - *Property sets for objects*
- Object association
  - *Material Single*
- Product shape
  - *Alignment Geometry Gradient*
  - *Product Linear Placement*
  - *Product Local Placement*
  - *Body Brep Geometry*
  - *Axis 3D Geometry*
  - *Axis 2D Geometry*

</details>

## Model Dataset

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename                                                     | Description                                   |
| ------------------------------------------------------------ | --------------------------------------------- |
| [HorizontalAlignmentParameters](Dataset/HorizontalAlignmentParameters.csv) | Parameters for the horizontal segments as csv |
| [VerticalAlignmentParameters](Dataset/VerticalAlignmentParameters.csv) | Parameters for the vertical segments as csv   |
| [LandXML](Dataset/Testi_101_ml.xml)                          | LandXML-file representing the alignment       |
| [Pavement composition](./Dataset/Pavement-composition.png)   | Image showing the pavement composition        |

## Test Case Imports

Test instructions are defined with a modular approach to reduce repetition of validation criteria and test content, and improve vendors ability to solve issues and bugs. therefore this test instruction *imports/reuses* the following Test instructions and entities with the relevant associated validation criteria.

| TI Code | Test Instruction Title | Comments |
| ------- | ---------------------- | -------- |
| -       | -                      | na       |

## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`-`ExchangeCode`-`TestCode`-`SoftwareVendor`.`ifc` (Example: `IFC4.3_AbRV-E2b-ASTPC-AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet usefull to illustrate test results are:
- Screen-shot of a planar view and a "long section" similar to the provided examples
- CSV export of the horizontal and vertical alignment segment parameters

---

## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section**, and **the ones of pre-required tests** shall be verified, with no exception. :zap:

### General

| **RULE ID** | **CRITERIA**                                                 | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | ------------------------------------------------------------ | ------------------------------------------------------------ | -------------------------- | ---------------------- |
| GENE_00     | All validation criteria of precondition's tests shall be verified |                                                              | na                         | na                     |
| GENE_01     | All requested entities (and attributes) exist in file        | As per Entities Table. See [Dataset description](Dataset/README.md) | na                         | na                     |

### Object typing

| **RULE ID** | **CRITERIA**              | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | ------------------------- | ------------------------------------------------------------ | -------------------------- | ---------------------- |
| OBTP_01     | Object types are verified | As per [Object Types Table](Dataset/README.md#object-types-table) | na                         | Object Typing          |

> **Acceptance criteria**: For the **Object typing** capability, the validation procedure must verify that an IFC entity type with the given Name is typing (via `IfcRelDefinesByType`) exactly a given number of objects of the requested Name, no more and no less.

<details><summary>OBTP_01 details: Object types are verified</summary>

> - Given a set of types and objects taken from the [Object Types Table](Dataset/README.md#object-types-table)
> - Then the Entity Type, with the Entity Type Name, exists
> - And the Entity Type must type exactly [MinSize..MaxSize] of the requested Object

</details>


### Material association

| **RULE ID** | **CRITERIA**                     | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | -------------------------------- | ------------------------------------------------------------ | -------------------------- | ---------------------- |
| MATE_01     | Material association is verified | As per [Material Association Table](Dataset/README.md#material-association-table) | na                         | Material Association   |

> **Acceptance criteria**: For the **Material association** capability, the validation procedure must verify that an Object of the requested type is associated (via `IfcRelAssociatesMaterial`) to a material definition with the requested name.

<details><summary>MATE_01 details: Material association is verified</summary>

> - Given a set of objects and materials taken from the [Material Association Table](Dataset/README.md#material-association-table)
> - Then the Objects, and optionally the Object Type, exists
> - And the Object must be associated to the requested Material

</details>

### Element (De)Composition (Assemblies)

| **RULE ID** | **CRITERIA**                                       | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)**                      |
| ----------- | -------------------------------------------------- | ------------------------------------------------------------ | -------------------------- | ------------------------------------------- |
| ASSE_01     | Mandatory components are present in the assemblies | As per [Element (De)Composition Table](Dataset/README.md#element-(de)composition-table) | na                         | Element Composition & Element Decomposition |

> **Acceptance criteria**: For the **ASSE_01 rule**, the validation procedure must verify that an assembly of the requested type (and name) aggregates (via `IfcRelAggregates`) at least a given number of elements of the requested type (and name).

<details><summary>ASSE_01 details: Mandatory components are present in the assemblies</summary>

> - Given a set of assemblies taken from the [Element (De)Composition Table](Dataset/README.md#element-(de)composition-table)
> - Then the Assembly, and optionally the Assembly Type, exists
> - And the Assembly must aggregate at least a number within [MinSize..MaxSize] of the requested Element

</details>

### Properties

| **RULE ID** | **CRITERIA**                                             | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)**                              |
| ----------- | -------------------------------------------------------- | ------------------------------------------------------------ | -------------------------- | --------------------------------------------------- |
| PSET_01     | The model does not contain unrequested property sets     | As per [Properties Table](Dataset/README.md#properties-table) | na                         | Property Sets for Objects & Property Sets for Types |
| PNAM_01     | The property set does not contain unrequested properties | As per [Properties Table](Dataset/README.md#properties-table) | na                         | Property Sets for Objects & Property Sets for Types |
| PTEX_01     | Property values belong to a list of values               | As per [Properties Table](Dataset/README.md#properties-table) | na                         | Property Sets for Objects & Property Sets for Types |
| PVAL_01     | Property values are not null and not empty               | As per [Properties Table](Dataset/README.md#properties-table) | na                         | Property Sets for Objects & Property Sets for Types |
| PVAL_02     | Requested property value types are found                 | As per [Properties Table](Dataset/README.md#properties-table) | na                         | Property Sets for Objects & Property Sets for Types |

> **Acceptance criteria**: For the **Properties for objects and object types** capability, the validation procedure must verify that both standard and custom property sets requested by the test case (including relative properties and values) are present in the IFC file.
> See below for further specification of each rule.

<details><summary>PSET_01: The model does not contain unrequested property sets</summary>

> - Given a set of properties taken from the [Properties Table](Dataset/README.md#properties-table)
> - When the IfcEntity, and optionally the Type, exists
> - Then the IfcEntity is associated at most to the property set with the PropertySet Name
</details>

<details><summary>PNAM_01: The property set does not contain unrequested properties</summary>

> - Given a set of properties taken from the [Properties Table](Dataset/README.md#properties-table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - Then the property set has at most the properties with the Property Name
</details>

<details><summary>PTEX_01: Property values belong to a list of values</summary>

> - Given a set of properties taken from the [Properties Table](Dataset/README.md#properties-table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - Then the property value is part of the List Of Values
</details>

<details><summary>PVAL_01: Property values are not null and not empty</summary>

> - Given a set of properties taken from the [Properties Table](Dataset/README.md#properties-table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - Then the property value is not null
> - And the property value is not empty
</details>

<details><summary>PVAL_02: Requested property value types are found</summary>

> - Given a set of properties taken from the [Properties Table](Dataset/README.md#properties-table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - And the property value is not null
> - Then the property type is equal to the Property Value Type
</details>

### Spatial (De)Composition

| **RULE ID** | **CRITERIA**                      | **VALUE [examples]**                 | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|-----------------------------------|--------------------------------------|----------------------------|------------------------|
| SDEC_01     | Spatial decomposition is verified | As per Spatial (De)Composition Table | na                         | Spatial Decomposition  |

> **Acceptance criteria**: For the **Spatial decomposition** capability, the validation procedure must verify that a Parent Element of the requested type aggregates (via `IfcRelAggregates`) exactly a given number of Child Elements of the requested type, no more and no less.

<details><summary>SDEC_01 details: Spatial decomposition is verified</summary>

> - Given a set of elements taken from the [Spatial (De)Composition Table](#Spatial-(De)Composition-Table)
> - Then the Parent Element, and optionally the Parent Element Type, exists
> - And the Parent Element must aggregate at least a number within [MinSize..MaxSize] of the requested Child Element

</details>

## Spatial containment

| **RULE ID** | **CRITERIA**                    | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | ------------------------------- | ------------------------------------------------------------ | -------------------------- | ---------------------- |
| SCON_01     | Spatial containment is verified | As per [Spatial Containment Table](Dataset/README.md#spatial-containment-table) | na                         | Spatial Containment    |

> **Acceptance criteria**: For the **Spatial containment** capability, the validation procedure must verify that a Spatial Element of the requested type contains (via `IfcRelContainedInSpatialStructure`) exactly a given number of Elements of the requested type, no more and no less.

<details><summary>SCON_01 details: Spatial containment is verified</summary>

> - Given a set of elements taken from the [Spatial Containment Table](Dataset/README.md#spatial-containment-table)
> - Then the Spatial Element, and optionally the Spatial Element Type, exists
> - And the Spatial Element must contain at least a number within [MinSize..MaxSize] of the requested Element

</details>

### Product geometric representation

| **RULE ID** | **CRITERIA**                            | **VALUE [examples]**                     | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-----------------------------------------|------------------------------------------|----------------------------|----------------------------|
| PREP_01     | Geometric representation of products is verified | As per [Product Geometric Representation Table](Dataset/README.md#product-geometric-representation-table) |                   | Product Geometric Representation and its subtemplates |

> **Acceptance criteria**: For the **Group Geometric Representation** capability, the validation procedure must verify that a Product of the requested type (and optionally a requested name) has an IfcShapeRepresentation with the requested Representation Identifier, Representation Type and Items.

<details><summary>PREP_01 details:  Geometric representation of products is verified</summary>

> - Given a set of products taken from the [Product Geometric Representation Table](#product-geometric-representation-table)
> - Then the Product, and optionally the Product Type, exists
> - And the Product must have an IfcShapeRepresentation (via IfcProductDefinitionShape) with the requested Representation Identifier, Representation Type and Items.

</details>


### Product placement

| **RULE ID** | **CRITERIA**                            | **VALUE [examples]**                     | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-----------------------------------------|------------------------------------------|----------------------------|----------------------------|
| PPLA_01     | Placement of products is verified | As per [Product Placement Table](Dataset/README.md#product-placement-table) |                   | Product Placement subtemplates |
| PPLA_02     | For a product that has ObjectPlacement as IfcLinearPlacement, the CartesianPosition of IfcLinearPlacement shall be available | depends on cases |                   | Product Linear Placement |

> **Acceptance criteria**: For the **Product Placement** capability, the validation procedure must verify that a Product of the requested type (and optionally a requested name) has the requested Object Placement, and optionally the Object Placement has PlacementRelTo reference to the Object Placement of Relative Placement Product with requested Relative Placement Product Type and Relative Placement Product Name.

<details><summary>PPLA_01 details:  Placement of products is verified</summary>

> - Given a set of products taken from the [Product Placement Table](Dataset/README.md#product-placement-table)
> - Then the Product with Product Type and Product Name, exists
> - And the Product must have Object Placement, and the Object Placement has PlacementRelTo reference to the ObjectPlacement of Relative Placement Product with requested Relative Placement Product Type and Relative Placement Product Name.

</details>
