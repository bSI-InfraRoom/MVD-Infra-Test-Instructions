# Test instructions

| Documentation Code   | Test Title                             | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|----------------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_SP01  | 	(RFI) Track super-structure for single track | E2a (TRAS)    | SP01      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |




## Summary (Intent)

This test case addresses the **export** of the required IFC entities for the exchange of **track super-structure** information.

This test case focuses only on track super-structure (green in picture below). For the track sub-structure part (red in picture below), refer to test case **IFC4.3AbRV_E2a_SB01**, of which SP01 is an extension.

Snippet:
<img src="./Dataset/TrackCrossSection_snippet.png" width="500"/>

The test also includes the association of some track products (rails, sleepers, ballast, etc.) to: i) the required model breakdown elements (aka, **spatial structure containment**); ii) the required materials (aka, **material association**).

- Refer to [Test Case Imports](#Test-Case-Imports) to know the prerequisites for the present test.

- The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

- :zap: This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test :zap:





## Itemised Roots
:construction: **under construction, check CT for product shape** :construction:

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_E2a exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Model setup:
   1. IfcFacilityPart
- Track domain physical products:
   1. IfcRail / IfcRailType
   1. IfcTrackElement
   1. IfcCourse / IfcCourseType
</details>

<details><summary>Concept Templates</summary> 

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Object Attributes
   - Object Predefined Type
- Object definition
   - Object Typing
- Product Shape
   - Product Geometric Representation
   - Body SectionedSolidHorizontal
   - Body Tessellation Geometry
- Product Placement
   - Product Local Placement
   - Product Linear Placement
- Object Composition
   - Spatial Decomposition
- Object Connectivity
   - Spatial Containment
- Object Association
   - Material Association
     - Material Single
     - Material Profile Set
     - Material Constituent Set

</details>




## Model Dataset

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename             | Type (format) | Description                                                 |
|----------------------|---------------|-------------------------------------------------------------|
| TrackCrossSection    | drawing (png) | Track cross section to be used as example                   |
| Cant-CantAngle       | figure (png)  | Information on how cant is applied to rail                  |
| CantFromLowerRail    | figure (png)  | Information on how cant is applied to rail                  |
| SleeperPlacement     | figure (png)  | Information on how to position sleepers along the alignment |
| RailProfile60UIC     | drawing (jpg) | Drawing of the rail profile E601 (aka, UIC 60) to be used   |
| SleeperExampleRFI230 | drawing (png) | Example of shape and tolerances of a concrete sleeper       |




## Test Case Imports

All validation criteria (and usages) of predecessors' tests shall be **verified for this test too** (regression test principle). Prerequisites for the present test case are listed below.

| TI Code                        | Test Instruction Title               | Comments |
|--------------------------------|--------------------------------------|----------|
| [IFC4.3AbRV_E1b_AL23](./AL23)  | (RFI) Two alignments with cant       | **For the test to be passed, the track sub-structure shall be modelled ONLY for the Primary Route (i.e., Alignment 1_Primary route)** |
| [IFC4.3AbRV_E2a_SB01](./SB01)  | (RFI) Track sub-structure for single track |  |




## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_SP01_AmazingSoft.ifc`)




# Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section**, and **the ones of pre-required tests** shall be verified, with no exception. :zap:

### General

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------------------|----------------------------|
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       | na                         | na                         |
| GENE_01     | All requested entities (and attributes) exist in file             | As per Entities Table | na                         | na                         |

#### Entities Table

| **Element**     | **Attribute**  | **Value**                           | **Notes**                                                                                                                                                                                                                                                           |
|-----------------|----------------|-------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| IfcFacilityPart | Name           | LO1336-BC-BC01                      |                                                                                                                                                                                                                                                                     |
|                 | Description    | Binario IV dispari - Orte Falconara |                                                                                                                                                                                                                                                                     |
|                 | ObjectType     | $                                   |                                                                                                                                                                                                                                                                     |
|                 | PredefinedType | TRACKSTRUCTURE                      |                                                                                                                                                                                                                                                                     |
| IfcFacilityPart | Name           | LO1336-BC-BC02                      |                                                                                                                                                                                                                                                                     |
|                 | Description    | Binario V dispari - Orte Falconara  |                                                                                                                                                                                                                                                                     |
|                 | ObjectType     | $                                   |                                                                                                                                                                                                                                                                     |
|                 | PredefinedType | TRACKSTRUCTURE                      |                                                                                                                                                                                                                                                                     |
| IfcCourse       | Name           | LO1336-BC-BC01-MAS-M01              | NOTE: all IfcCourse entities are to be typed by the IfcCourseType entity below (via `IfcRelDefinesByType`). This is important because in a following test properties will be associated to the type, and are expected to be inherited by the IfcCourse occurrences. |
|                 | Description    | Segmento di massicciata M01         |                                                                                                                                                                                                                                                                     |
|                 | ObjectType     | $                                   |                                                                                                                                                                                                                                                                     |
|                 | PredefinedType | BALLASTBED                          |                                                                                                                                                                                                                                                                     |
| IfcCourseType   | Name           | Segmento di massicciata             |                                                                                                                                                                                                                                                                     |
|                 | Description    | $                                   |                                                                                                                                                                                                                                                                     |
|                 | PredefinedType | BALLASTBED                          |                                                                                                                                                                                                                                                                     |
| IfcRail         | Name           | Rotaia BC01 DX                      | NOTE: all IfcRail entities are to be typed by the IfcRailType entity below (via `IfcRelDefinesByType`). This is important because in this test materials will be associated to the type, and are expected to be inherited by the IfcRail occurrences.               |
|                 | Description    | $                                   |                                                                                                                                                                                                                                                                     |
|                 | ObjectType     | $                                   |                                                                                                                                                                                                                                                                     |
|                 | PredefinedType | RAIL                                |                                                                                                                                                                                                                                                                     |
| IfcRail         | Name           | Rotaia BC01 SX                      |                                                                                                                                                                                                                                                                     |
|                 | Description    | $                                   |                                                                                                                                                                                                                                                                     |
|                 | ObjectType     | $                                   |                                                                                                                                                                                                                                                                     |
|                 | PredefinedType | RAIL                                |                                                                                                                                                                                                                                                                     |
| IfcRailType     | Name           | Rotaia 60E1                         |                                                                                                                                                                                                                                                                     |
|                 | Description    | Rail UIC 60                         |                                                                                                                                                                                                                                                                     |
|                 | PredefinedType | RAIL                                |                                                                                                                                                                                                                                                                     |
| IfcTrackElement | Name           | Traversa 0000                       | NOTE: 0000 indicates the progressive number of each sleeper (i.e., Traversa 0001, Traversa 0002, Traversa 0003, etc.)                                                                                                                                               |
|                 | Description    | $                                   |                                                                                                                                                                                                                                                                     |
|                 | ObjectType     | $                                   |                                                                                                                                                                                                                                                                     |
|                 | PredefinedType | SLEEPER                             |


### Object typing


| **RULE ID** | **CRITERIA**              | **VALUE [examples]**      | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|---------------------------|---------------------------|----------------------------|------------------------|
| OBTP_01     | Object types are verified | As per Object Types Table | na                         | Object Typing          |

> **Acceptance criteria**: For the **Object typing** capability, the validation procedure must verify that an IFC entity type with the given Name is typing (via `IfcRelDefinesByType`) exactly a given number of objects of the requested Name, no more and no less.

<details><summary>OBTP_01 details: Object types are verified</summary>

> - Given a set of types and objects taken from the [Object Types Table](#Object-Types-Table)
> - Then the Entity Type, with the Entity Type Name, exists
> - And the Entity Type must type exactly [MinSize..MaxSize] of the requested Object

</details>

#### Object Types Table

| **Entity Type** | **Entity Type Name**    | **MinSize** | **MaxSize** | **IfcObject** | **IfcObject Name**          |
|-----------------|-------------------------|-------------|-------------|---------------|-----------------------------|
| IfcCourseType   | Segmento di massicciata | 1           |             | IfcCourse     | Segmento di massicciata M01 |
| IfcRailType     | Rotaia 60E1             | 1           |             | IfcRail       | Rotaia BC01 DX              |
| IfcRailType     | Rotaia 60E1             | 1           |             | IfcRail       | Rotaia BC01 SX              |

**NOTE**:
- when **Minimum** and **Maximum** have the same value, it means exactly. Example: Minimum=Maximum=1, means that the entity type must type exactly 1 object with that Name.
- when **Maximum is empty**, it means **unlimited**. Example: Minimum=1; Maximum=empty, means that the Entity Type must type 1 or more Object of the requested name.




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

#### Spatial (De)Composition Table

| **Parent Element** | **Parent Element Type** | **MinSize** | **MaxSize** | **Child Element** | **Child Element Type** |
|--------------------|-------------------------|-------------|-------------|-------------------|------------------------|
| IfcRailway         | Località                | 2           | 2           | IfcFacilityPart   | TRACKSTRUCTURE         |

**Bullet point example**:
- IfcRailway *(Name: LO1336)*
  - IfcFacilityPart.TRACKSTRUCTURE *(Name: LO1336-BC-BC01)*
  - IfcFacilityPart.TRACKSTRUCTURE *(Name: LO1336-BC-BC02)*




### Spatial Containment

| **RULE ID** | **CRITERIA**                    | **VALUE [examples]**             | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|---------------------------------|----------------------------------|----------------------------|------------------------|
| SCON_01     | Spatial containment is verified | As per Spatial Containment Table | na                         | Spatial Containment    |

> **Acceptance criteria**: For the **Spatial containment** capability, the validation procedure must verify that a Spatial Element of the requested type contains (via `IfcRelContainedInSpatialStructure`) exactly a given number of Elements of the requested type, no more and no less.

<details><summary>SCON_01 details: Spatial containment is verified</summary>

> - Given a set of elements taken from the [Spatial Containment Table](#Spatial-Containment-Table)
> - Then the Spatial Element, and optionally the Spatial Element Type, exists
> - And the Spatial Element must contain at least a number within [MinSize..MaxSize] of the requested Element

</details>

#### Spatial Containment Table

| **Spatial Element** | **Spatial Element Type** | **MinSize** | **MaxSize** | **Element**     | **Element Type** |
|---------------------|--------------------------|-------------|-------------|-----------------|------------------|
| IfcFacilityPart     | TRACKSTRUCTURE           | 1           |             | IfcCourse       | BALLASTBED       |
| IfcFacilityPart     | TRACKSTRUCTURE           | 2           |             | IfcRail         | RAIL             |
| IfcFacilityPart     | TRACKSTRUCTURE           | 1           |             | IfcTrackElement | SLEEPER          |

**NOTE**:
- when **MaxSize is empty**, it means **unlimited**. Example: MinSize=1; MaxSize=empty, means that the Spatial Element must contain 1 or more elements of the requested type.
- when **MinSize** and **MaxSize** have the same value, it means exactly. Example: MinSize=MaxSize=1, means that the Spatial Element must contain exactly 1 Element with that Type (and Name).

**Bullet point example**:

- IfcRailway *(Name: LO1336)*
  - IfcFacilityPart.TRACKSTRUCTURE *(Name: LO1336-BC-BC01)*
    - `IfcCourse.BALLASTBED` *(Name: BC01)*
    - `IfcRail.RAIL` *(Name: Rotaia BC01 SX)*
    - `IfcRail.RAIL` *(Name: Rotaia BC01 DX)*
    - `IfcTrackElement.SLEEPER` *(Name: Traversa 0001)*
    - `IfcTrackElement.SLEEPER` *(Name: Traversa 0002)*
    - `IfcTrackElement.SLEEPER` *(Name: Traversa 000n)*
  - IfcFacilityPart.TRACKSTRUCTURE *(Name: LO1336-BC-BC02)*




### Material association

| **RULE ID** | **CRITERIA**                     | **VALUE [examples]**              | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|----------------------------------|-----------------------------------|----------------------------|------------------------|
| MATE_01     | Material association is verified | As per Material Association Table | na                         | Material Association   |

> **Acceptance criteria**: For the **Material association** capability, the validation procedure must verify that an Object of the requested type is associated (via `IfcRelAssociatesMaterial`) to a material definition with the requested name.

<details><summary>MATE_01 details: Material association is verified</summary>

> - Given a set of objects and materials taken from the [Material Association Table](#Material-Association-Table)
> - Then the Objects, and optionally the Object Type, exists
> - And the Object must be associated to the requested Material

</details>

#### Material Association Table

| **Object**      | **Object Type** | **Material Definition** | **Material Name** |
|-----------------|-----------------|-------------------------|-------------------|
| IfcCourseType   | BALLASTBED      | IfcMaterial             | Gravel            |
| IfcRail         | RAIL            | IfcMaterialProfile      | 60E1              |
| IfcTrackElement | SLEEPER         | IfcMaterial             | Concrete          |


