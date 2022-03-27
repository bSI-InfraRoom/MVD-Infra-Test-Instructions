# Test Instruction

| Documentation Code   | Title                                          | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|------------------------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_TSTP   | Track Structures Turnout Panel                      | Ex2a-TRST            | TSTP      | Chi Zhang    | RFI        | 1.0     | 09.02.2022 |


## Summary (Intent)

This test instruction is defined for IFC4.3AbRV_E2a_TSTP Track Structures Turnout Panel.

It covers following subjects:
- A basic project structure setup including units, context and global positioning
- Two alignments for a section of railway, including the horizontal and vertical layouts
- A track turnout panel linearly placed based on one alignment
- Breakdown structure of a track turnout panel (simplified) with relative placement between elements and assembly
- Swept area solid geometry of rail elements in the turnout panel

The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

:zap: **This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test** :zap:

## Itemised Roots

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- Inherited from imported tests:
  - *IfcProject*
  - *IfcSite*
  - *IfcRailway*
  - *IfcAlignment*
  - *IfcAlignmentHorizontal*
  - *IfcAlignmentVertical*
  - *IfcAlignmentSegment*

- For this test instruction:
  - *IfcRailwayPart*
  - *IfcElementAssembly*
  - *IfcTrackElement*
  - *IfcRail*
  - *IfcMechnicalFastner*
  - *IfcFastener*
  - *IfcReferent*


</details>

<details><summary>Concept Templates</summary>

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- Inherited from imported tests:
  - *Project Units*
  - *Project Representation Context*
  - *Project Global Positioning*
  - *Spatial Decomposition*
  - *Spatial Composition*
  - *Alignment Layout*
  - *Alignment Geometry Gradient*
  - *Spatial Container*
  - *Product Local Placement*
  - *Object User Identity*
  - *Software Identity*
  - *Axis Geometry*
  
- For this test instruction:
  - *Product Linear Placement*
  - *Object Predefined Type*
  - *Element Composition*
  - *Element Decomposition*
  - *Product Relative Positioning*
  - *Product Span Positioning*
  - *Spatial Containment*
  - *Body AdvancedSwept Directrix Geometry*
  - *Body Tessallated Geometry*
  - *Object Typing*
  - *Type Body Tessellated Geometry*

</details>

## Test Case Imports
Test instructions are defined with a modular approach to reduce repetition of validation criteria and test content, and improve vendors ability to solve issues and bugs. therefore this test instruction *imports/reuses* the following Test instructions and entities with the relevant associated validation criteria.

<details><summary>Imports & Reuses</summary>

| TI Code                                  | Test Instruction Title    | Comments                     |
|------------------------------------------|---------------------------|------------------------------|
| [IFC4.3AbRV_E1_AL22](../../E2a-TRST/AL22) | (RFI) Two alignments without cant       | As outlined in the dataset Imported Entities Table |

</details>

## Usages, Constraints & Logic
The following itemised restrictions and constraints shall be placed on IFC Entities & Concept Templates:

<details><summary>Semantic Usages, Constraints & Logic</summary>

The following itemised Usages, Constraints & Logic are normative entries within the AbRV MVD and MUST be satisfied to meet the defined validation criteria

</details>

<details><summary>Model Geometry</summary>
The Test case requires the following additional checks related to Model Geometry:

- *Constraint*

</details>

## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`-`ExchangeCode`-`TestCode`-`SoftwareVendor`.`ifc` (Example: `IFC4.3_AbRV-E2b-ASTPC-AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet useful to illustrate test results are:
- Screen-shot of the IFC file visualization
- Screen-shot of the IFC file structure (spatial decomposition, element decomposition).

---

## Validation criteria
:zap: For this test case to be considered passed **all capabilities** listed in this section shall be verified, with no exception. :zap:

### General & Imports

<details><summary>Click to expand</summary>

- All the concept templates must be correctly implemented as presented in the validation criteria
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file.


#### Imports
| **TI Code**        | **Criteria Codes** | *COMMENT**                                         |
|--------------------|--------------------|----------------------------------------------------|
| IFC4.3AbRV_E1_AL22 | ALL CRITERIA       | As outlined in the dataset [Imported Entities Table](Dataset/README.md#Imported-Entities-Table) |


#### General

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------------------|----------------------------|
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       | na                         | na                         |
| GENE_01     | All requested entities (and attributes) exist in file             | As per Entities Table | na                         | na                         |
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


- IfcProject
  - IfcSite
    - IfcRailway
      - IfcFacilityPart.TRACKSTRUCTURE
	


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

- IfcSite
  - IfcAlignment
  - IfcRailway 
    - IfcFacilityPart.TRACKSTRUCTURE
      - IfcElementAssembly.TURNOUTPANEL



### Element (De)Composition (Assemblies)

| **RULE ID** | **CRITERIA**                                       | **VALUE [examples]**                 | **ENTITY (if applicable)** | **CT (if applicable)**                      |
|-------------|----------------------------------------------------|--------------------------------------|----------------------------|---------------------------------------------|
| ASSE_01     | Mandatory components are present in the assemblies | As per Element (De)Composition Table | na                         | Element Composition & Element Decomposition |

> **Acceptance criteria**: For the **ASSE_01 rule**, the validation procedure must verify that an assembly of the requested type (and name) aggregates (via `IfcRelAggregates`) at least a given number of elements of the requested type (and name).

<details><summary>ASSE_01 details: Mandatory components are present in the assemblies</summary>

> - Given a set of assemblies taken from the [Element (De)Composition Table](#Element-(De)Composition)
> - Then the Assembly, and optionally the Assembly Type, exists
> - And the Assembly must aggregate at least a number within [MinSize..MaxSize] of the requested Element

</details>

- IfcElementAssembly.TURNOUTPANEL 
  - IfcRail.RAIL
  - IfcRail.CHECKRAIL
  - IfcRail.BLADE
  - IfcTrackElement.SLEEPER
  - IfcTrackElement.FROG
  - IfcMechanicalFastener.RAILFASTENING
  - IfcMechanicalFastner.RAILJOINT
  - IfcFastener.WELD
	




### Referent & Mileage

| **ID**  | **CRITERIA**                                                                        | **VALUE [examples]**   | **ENTITY (if applicable)** | **CT (if applicable)**             |
|---------|-------------------------------------------------------------------------------------|------------------------|----------------------------|------------------------------------|
| REFE_00 | There are two nesting relationships for referents and for alignment components      |                        |                            |                                    |
| REFE_01 | Relating Object and Distance Along for referent nesting are verified                | As per Referents Table | IfcReferent                | Object Nesting (IfcReferent usage) |
| REFE_02     | Each IfcReferent should be nested into the alignment where it is placed linearly |     1 IfcAlignment  | IfcReferent | Object Nesting (to be reversed) |

> **Acceptance criteria**: For the **Referent nesting** capability, the validation procedure must verify that **all** the above validation criteria are satisfied.

<details><summary>REFE_00 details: There are two nesting relationships for referents and for alignment components</summary>

> - Given an `IfcAlignment`
> - When `IfcAlignment` has an `IfcRelNests` relationship
> - Then the `IfcRelNests` relationship is related either to an `IfcReferent` OR to an `IfcLinearElement`

</details>

<details><summary>REFE_01 details: Relating Object and Distance Along for referent nesting are verified</summary>

> - Given a set of referents taken from the [Referents Table](#Referents-Table)
> - Then the Referent, with the Referent Type and Name, exists
> - And the Referent is placed relative to the Placement Product, using the requested Object Placement
> - And the Referent is placed at the requested DistanceAlong

</details>

### Product placement
	
| **RULE ID** | **CRITERIA**                            | **VALUE [examples]**                     | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-----------------------------------------|------------------------------------------|----------------------------|----------------------------|
| PPLA_01     | Placement of products is verified | As per Product Placement Table |                   | Product Placement subtemplates |
| PPLA_02     | For a product that has ObjectPlacement as IfcLinearPlacement, the CartesianPosition of IfcLinearPlacement shall be available | depends on cases |                   | Product Linear Placement |

> **Acceptance criteria**: For the **Product Placement** capability, the validation procedure must verify that a Product of the requested type (and optionally a requested name) has the requested Object Placement, and optionally the Object Placement has PlacementRelTo reference to the Object Placement of Relative Placement Product with requested Relative Placement Product Type and Relative Placement Product Name.

<details><summary>PPLA_01 details:  Placement of products is verified</summary>

> - Given a set of products taken from the [Product Geometric Representation Table](#Product-Geometric-Representation-Table)
> - Then the Product with Product Type and Product Name, exists
> - And the Product must have Object Placement, and the Object Placement has PlacementRelTo reference to the ObjectPlacement of Relative Placement Product with requested Relative Placement Product Type and Relative Placement Product Name.

</details>
	


### Product relative positioning

| **RULE ID** | **CRITERIA**                      | **VALUE [examples]**                 | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|-----------------------------------|--------------------------------------|----------------------------|------------------------|
| PPOS_01     | Product relative positioning is verified | As per Product Relative Positioning Table | na                         | Product Relative Positioning, Product Span Positioning |

> **Acceptance criteria**: For the **Spatial relative positioning** capability, the validation procedure must verify that a Product of the requested type is positioned (via `IfcRelPositions`) exactly a given number of Positioning Elements of the requested type, no more and no less.

<details><summary>PPOS_01 details: Product relative positioning is verified</summary>

> - Given a set of products taken from the [Product Relative Positioning Table](#Product-Relative-Positioning-Table)
> - Then the Product, and optionally the Product Type, exists
> - And the Product must be positioned on exactly [Size] of the requested Positioning Element

</details>

	
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


	

