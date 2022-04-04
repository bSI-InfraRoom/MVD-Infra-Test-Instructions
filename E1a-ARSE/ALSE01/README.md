# Test Instruction

| Documentation Code    | Title                            | Exchange Code   | Test Code | Author        | Data Owner | Version | Date       |
| --------------------- | -------------------------------- | --------------- | --------- | ------------- | ---------- | ------- | ---------- |
| IFC4.3AbRV_E1a_ALSE01 | Alignment Superelevation & Width | IFC4x3_AbRV-E1a | ALSE01    | Lars WIkström | FTIA       | 1.0     | 07.01.2022 |


## Summary (Intent)

With these instructions the infrastructure (e.g. Road) alignment exchange is established. This test instruction use the same alignment definition as [ALIN06](../ALIN06).

The data comes from, and is a simplified version of, the IFC Infra Unit Test [MCON-2](https://github.com/bSI-InfraRoom/IFC-infra-unit-test/tree/main/MCON-2) which in turn is extracted from the IFC Rail [Level Crossing storyline](https://github.com/IFCRail/IFC-Rail-Unit-Test/tree/master/8_Storylines%20Test%20(SL)/SL08_Level%20Crossing). 

| Info                         |                                       |
| ---------------------------- | ------------------------------------- |
| Number of alignment(s)       | 1                                     |
| Properties of segments       | no                                    |
| Horizontal layout            | Straight Line, Circular Arc           |
| Vertical layout              | Straight Line, Circular Arc           |
| Geometric representation     | IfcCompositeCurve, IfcGradientCurve   |
| Superelevation               | 12  IfcAnnotation/SUPERELEVATIONEVENT |
| Width                        | 0                                     |
| IFC reference file available | Yes                                   |

- Refer to [Test Case Imports](#Test-Case-Imports) to know the prerequisites for the present test.

- The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

- :zap: This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test :zap:

## Itemised Roots
The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

- Inherited from imported tests:
  - Model setup
    - IfcProject
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

## Model Dataset

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename                                                     | Type (format) | Description                                  |
| ------------------------------------------------------------ | ------------- | -------------------------------------------- |
| [HorizontalAlignmentParameters](Dataset/HorizontalAlignmentParameters.csv) | csv           | Alignment parameters for horizontal segments |
| [VerticalAlignmentParameters](Dataset/VerticalAlignmentParameters.csv) | csv           | Alignment parameters for vertical segments   |
| [LandXML](Dataset/TOI-M14334-0000A.xml)                      | xml           | LandXML representation of the alignment      |

## Test Case Imports

Test instructions are defined with a modular approach to reduce repetition of validation criteria and test content, and improve vendors ability to solve issues and bugs. therefore this test instruction *imports/reuses* the following Test instructions and entities with the relevant associated validation criteria.


| TI Code                                                      | Test Instruction Title          | Comments |
| ------------------------------------------------------------ | ------------------------------- | -------- |
| [**IFC4x3_AbRV-E1a-ALIN06**](https://github.com/bSI-InfraRoom/MVD-Infra-Test-Instructions/blob/develop/E1a-ARSE/ALIN06) | Alignment Infrastructure Curves | na       |

## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`-`ExchangeCode`-`TestCode`-`SoftwareVendor`.`ifc` (Example: `IFC4.3_AbRV-E2b-ASTPC-AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet usefull to illustrate test results are:
- Screen-shot of a planar view and a "long section" showing the superelevation changes

---

## Validation criteria
:zap: For this test case to be considered passed **all capabilities** listed in this section shall be verified, with no exception. :zap:

### General


| **RULE ID** | **CRITERIA**                                                 | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | ------------------------------------------------------------ | ------------------------------------------------------------ | -------------------------- | ---------------------- |
| GENE_00     | All validation criteria of precondition's tests shall be verified |                                                              | na                         | na                     |
| GENE_01     | All requested entities (and attributes) exist in file        | As per Entities Table. See [Dataset specification](Dataset/README.md). | na                         | na                     |

### Superelevation & Width

| **ID**  | **CRITERIA**                             | **VALUE [examples]**                                         | **ENTITY (if applicable)**        | **CT (if applicable)**       |
| ------- | ---------------------------------------- | ------------------------------------------------------------ | --------------------------------- | ---------------------------- |
| SEWI_00 | Superelevation representation verified   |                                                              | IfcAnnotation/SUPERELEVATIONEVENT |                              |
| SEWI_01 | Width representation verified            |                                                              | IfcAnnotation/WIDTHEVENT          |                              |
| SEWI_02 | Superelevation linear placement verified | As per Product placement table. See [Dataset specification](Dataset/README.md). |                                   | Product Linear Placement     |
| SEWI_03 | Width linear placement verified          | As per Product placement table. See [Dataset specification](Dataset/README.md). |                                   |                              |
| SEWI_04 | Superelevation properties verified       | As per Properties table. See [Dataset specification](Dataset/README.md). |                                   | Property sets for objects    |
| SEWI_05 | Width properties verified                | As per Properties table. See [Dataset specification](Dataset/README.md). |                                   | Property sets for objects    |
| SEWI_06 | Relative Positioning verified            | As per Product Relative Positioning table. See [Dataset specification](Dataset/README.md). |                                   | Product Relative Positioning |

> **Acceptance criteria**: For the **Superelevation & Width** capability, the validation procedure must verify that **all** the above validation criteria are satisfied.

<details><summary>SEWI_02 details: Superelevation event linear placement verified verified</summary>



> - Given an `IfcAnnotation/SUPERELEVATIONEVENT`
> - Then the `IfcAnnotation/SUPERELEVATIONEVENT` has a linear placement that complies with the criteria in the [Product placement](#Product-placement) section and the specification in [Product Placement Table](Dataset/README.md#Product-Placement-Table)

</details>

<details><summary>SEWI_03 details: Width event linear placement verified verified</summary>



> - Given an `IfcAnnotation/WIDTHEVENT`
> - Then the `IfcAnnotation/WIDTHEVENT` has a linear placement that complies with the criteria in the [Product placement](#Product-placement) section and the specification in [Product Placement Table](Dataset/README.md#Product-Placement-Table)

</details>

<details><summary>SEWI_04 details: Superelevation properties verified</summary>



> - Given an `IfcAnnotation/SUPERELEVATIONEVENT`
> - Then `IfcAnnotation/SUPERELEVATIONEVENT` has a property set named `Pset_Superelevation`
> - And the property assignment for `Pset_Superelevation` complies with the criteria specified in the [Properties](#Properties) section and the specification in the [Properties table](Dataset/README.md#Properties-table)

</details>

<details><summary>SEWI_05 details: Width properties verified</summary>



> - Given an `IfcAnnotation/WIDTHEVENT`
> - Then `IfcAnnotation/WIDTHEVENT` has a property set named `Pset_Width`
> - And the property assignment complies with the criteria specified in the [Properties](#Properties) section and the specification in the [Properties table](Dataset/README.md#Properties-table)

</details>

<details><summary>SEWI_06 details: Relative positioning verified</summary>



> - Given an `IfcAnnotation/SUPERELEVATIONEVENT` or an `IfcAnnotation/WIDTHEVENT` having a linear placement relative to an alignment curve  
> - This instance shall be verified according to the criteria in the [Product Relative Positioning](#Product-relative-positioning) section and the specification in the [Product Relative Positioning table](Dataset/README.md#Product-Relative-Positioning-table)

</details>

### Product relative positioning

| **RULE ID** | **CRITERIA**                             | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)**                                 |
| ----------- | ---------------------------------------- | ------------------------------------------------------------ | -------------------------- | ------------------------------------------------------ |
| PPOS_01     | Product relative positioning is verified | As per Product Relative Positioning Table. See [Dataset specification](Dataset/README.md). | na                         | Product Relative Positioning, Product Span Positioning |

> **Acceptance criteria**: For the **Spatial relative positioning** capability, the validation procedure must verify that a Product of the requested type is positioned (via `IfcRelPositions`) exactly a given number of Positioning Elements of the requested type, no more and no less.

<details><summary>PPOS_01 details: Product relative positioning is verified</summary>


> - Given a set of products taken from the [Product Relative Positioning Table](Dataset/README.md#Product-Relative-Positioning-Table)
> - Then the Product, and optionally the Product Type, exists
> - And the Product must be positioned on exactly [Size] of the requested Positioning Element

</details>

### Properties

| **RULE ID** | **CRITERIA**                                             | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)**                              |
| ----------- | -------------------------------------------------------- | ------------------------------------------------------------ | -------------------------- | --------------------------------------------------- |
| PSET_01     | The model does not contain unrequested property sets     | As per Properties Table. See [Dataset specification](Dataset/README.md). | na                         | Property Sets for Objects & Property Sets for Types |
| PNAM_01     | The property set does not contain unrequested properties | As per Properties Table. See [Dataset specification](Dataset/README.md). | na                         | Property Sets for Objects & Property Sets for Types |
| PTEX_01     | Property values belong to a list of values               | As per Properties Table. See [Dataset specification](Dataset/README.md). | na                         | Property Sets for Objects & Property Sets for Types |
| PVAL_01     | Property values are not null and not empty               | As per Properties Table. See [Dataset specification](Dataset/README.md). | na                         | Property Sets for Objects & Property Sets for Types |
| PVAL_02     | Requested property value types are found                 | As per Properties Table. See [Dataset specification](Dataset/README.md). | na                         | Property Sets for Objects & Property Sets for Types |

> **Acceptance criteria**: For the **Properties for objects and object types** capability, the validation procedure must verify that both standard and custom property sets requested by the test case (including relative properties and values) are present in the IFC file.
> See below for further specification of each rule.

<details><summary>PSET_01: The model does not contain unrequested property sets</summary>


> - Given a set of properties taken from the [Properties Table](Dataset/README.md#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - Then the IfcEntity is associated at most to the property set with the PropertySet Name
>   </details>

<details><summary>PNAM_01: The property set does not contain unrequested properties</summary>


> - Given a set of properties taken from the [Properties Table](Dataset/README.md#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - Then the property set has at most the properties with the Property Name
>   </details>

<details><summary>PTEX_01: Property values belong to a list of values</summary>


> - Given a set of properties taken from the [Properties Table](Dataset/README.md#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - Then the property value is part of the List Of Values
>   </details>

<details><summary>PVAL_01: Property values are not null and not empty</summary>


> - Given a set of properties taken from the [Properties Table](Dataset/README.md#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - Then the property value is not null
> - And the property value is not empty
>   </details>

<details><summary>PVAL_02: Requested property value types are found</summary>


> - Given a set of properties taken from the [Properties Table](Dataset/README.md#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - And the property value is not null
> - Then the property type is equal to the Property Value Type
>   </details>

### Product placement

| **RULE ID** | **CRITERIA**                                                 | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)**         |
| ----------- | ------------------------------------------------------------ | ------------------------------------------------------------ | -------------------------- | ------------------------------ |
| PPLA_01     | Placement of products is verified                            | As per Product Placement Table. See [Dataset specification](Dataset/README.md). |                            | Product Placement subtemplates |
| PPLA_02     | For a product that has ObjectPlacement as IfcLinearPlacement, the CartesianPosition of IfcLinearPlacement shall be available | depends on cases                                             |                            | Product Linear Placement       |

> **Acceptance criteria**: For the **Product Placement** capability, the validation procedure must verify that a Product of the requested type (and optionally a requested name) has the requested Object Placement, and optionally the Object Placement has PlacementRelTo reference to the Object Placement of Relative Placement Product with requested Relative Placement Product Type and Relative Placement Product Name.

<details><summary>PPLA_01 details:  Placement of products is verified</summary>


> - Given a set of products taken from the [Product Geometric Representation Table](Dataset/README.md#Product-Geometric-Representation-Table)
> - Then the Product with Product Type and Product Name, exists
> - And the Product must have Object Placement, and the Object Placement has PlacementRelTo reference to the ObjectPlacement of Relative Placement Product with requested Relative Placement Product Type and Relative Placement Product Name.

</details>
