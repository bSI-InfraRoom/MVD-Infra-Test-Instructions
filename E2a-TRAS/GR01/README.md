# Test instructions

| Documentation Code   | Test Title                    | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|-------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_GR01  | (RFI) Group objects           | E2a (TRAS)    | GR01      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |




## Summary (Intent)

This test case addresses the **export** of the required IFC entities for the exchange of **objects grouping** information. Specifically, this test will verify the ability to create groups, and groups of groups. The test uses railway objects from predecessors tests.

- Refer to [Test Case Imports](#Test-Case-Imports) to know the prerequisites for the present test.

- The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

- :zap: This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test :zap:




## Itemised Roots

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_E2a exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Model setup:
   1. IfcSite
   1. IfcRailway
   1. IfcFacilityPart
- Other test-specific entities:
   1. IfcGroup
</details>

<details><summary>Concept Templates</summary> 

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Object Assignment
   - Group Assignment
- Object Connectivity
   - Group Spatial Connectivity
- Project Context
   - Project Declaration
</details>




## Model Dataset

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename              | Description                                                                            |
|-----------------------|----------------------------------------------------------------------------------------|
| GroupingOverview.png) | Diagram describing the expected structure regarding grouping and spatial relationships |




## Test Case Imports

All validation criteria (and usages) of predecessors' tests shall be **verified for this test too** (regression test principle). Prerequisites for the present test case are listed below.

| TI Code                       | Test Instruction Title                       | Comments |
|-------------------------------|----------------------------------------------|----------|
| [IFC4.3AbRV_E2a_SP01](./SP01) | (RFI) Track super-structure for single track |          |
| [IFC4.3AbRV_E2a_TP01](./TP01) | (RFI) Turnout panel between two tracks       |          |




## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_GR01_AmazingSoft.ifc`)




## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section** shall be verified, with no exception. :zap:

### General

### General

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------------------|----------------------------|
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       | na                         | na                         |
| GENE_01     | All requested entities (and attributes) exist in file             | As per Entities Table | na                         | na                         |

#### Entities Table

(12 `IfcGroup` instances)

| **Element** | **Attribute** | **Value**                     | **Notes** |
|-------------|---------------|-------------------------------|-----------|
| IfcGroup    | Name          | LO1336-BC                     |           |
|             | Description   | Binari di corsa di Foligno    |           |
|             | ObjectType    | Binari di corsa (Contenitore) |           |
| IfcGroup    | Name          | LO1336-BC-BC01-DEV            |           |
|             | Description   | Deviatoi BC01                 |           |
|             | ObjectType    | Deviatoi                      |           |
| IfcGroup    | Name          | LO1336-BC-BC01-ROT            |           |
|             | Description   | Rotaie BC01                   |           |
|             | ObjectType    | Rotaie                        |           |
| IfcGroup    | Name          | LO1336-BC-BC01-MAS            |           |
|             | Description   | Massicciata BC01              |           |
|             | ObjectType    | Massicciata                   |           |
| IfcGroup    | Name          | LO1336-BC-BC01-TRA            |           |
|             | Description   | Traverse BC01                 |           |
|             | ObjectType    | Traverse                      |           |
| IfcGroup    | Name          | LO1336-BC-BC02-ROT            |           |
|             | Description   | Rotaie BC02                   |           |
|             | ObjectType    | Rotaie                        |           |
| IfcGroup    | Name          | LO1336-BC-BC02-MAS            |           |
|             | Description   | Massicciata BC02              |           |
|             | ObjectType    | Massicciata                   |           |
| IfcGroup    | Name          | LO1336-BC-BC02-TRA            |           |
|             | Description   | Traverse BC02                 |           |
|             | ObjectType    | Traverse                      |           |
| IfcGroup    | Name          | LO1336-BC-BC01-ROT-R01        |           |
|             | Description   | Segmento di rotaia BC01       |           |
|             | ObjectType    | Segmento di rotaia            |           |
| IfcGroup    | Name          | LO1336-BC-BC02-ROT-R02        |           |
|             | Description   | Segmento di rotaia BC02       |           |
|             | ObjectType    | Segmento di rotaia            |           |
| IfcGroup    | Name          | LO1336-BC-BC01-TRA-T01        |           |
|             | Description   | Segmento di traverse BC01     |           |
|             | ObjectType    | Segmento di traverse          |           |
| IfcGroup    | Name          | LO1336-BC-BC02-TRA-T02        |           |
|             | Description   | Segmento di traverse BC02     |           |
|             | ObjectType    | Segmento di traverse          |           |


### Object grouping

| **RULE ID** | **CRITERIA**                                | **VALUE [examples]**                                                                                                                                          | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|---------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|------------------------|
| GROU_00     | Mandatory objects are present in the groups | As per Groups Table                                                                                                                                           | na                         | na                     |
| GROU_01     | Circular reference is not allowed           | Circular reference is not allowed, neither direct (if A includes B, B cannot includes A), nor indirect (if A includes B and B includes C, C cannot include A) | IfcGroup                   | Group Assignment       |
| GROU_02     | Only direct inclusion is allowed            | Example: if A includes B and B includes C, A cannot includes C)                                                                                               | IfcGroup                   | Group Assignment       |
| GROU_03     | Same-level grouping is not allowed          | If two or more Group are part of the same Group, they cannot include each others. Example: if A groups B and C, B cannot group C and vice versa)              | IfcGroup                   | Group Assignment       |
| GROU_04     | Group rooting                               | All Groups that do not have a parent Group must be linked to the IfcProject with an IfcRelDeclares relationship, as per Project Declaration template          | IfcGroup                   | Project Declaration    |
| GROU_05     | Group typing via ObjectType                 | *All group types shall be expressed using the ObjectType (5th attribute) of each occurrence of IfcGroup                                                       | IfcGroup                   | na                     |
| GROU_06     | Allowed entity types for groups             | IfcGroup must be associated (via IfcRelAssignsToGroup) only to IfcProduct or IfcGroup (and subtypes)                                                          | IfcGroup                   | Group Assignment       |

*: this is the only method to express group typing, due to the fact that: i) IfcGroup misses the PredefinedType attribute; and ii) object typing by instantiation of IfcTypeObject is discouraged from IFC4 onward.

> **Acceptance criteria**: For the **GROU_00 rule**, the validation procedure must verify that a group of the requested type is grouping (via `IfcRelAssignsToGroup`) exactly a given number of objects of the requested type, no more and no less.

<details><summary>GROU_00 details: Mandatory objects are present in the groups</summary>

> - Given a set of groups taken from the [Groups Table](#Groups-Table)
> - Then the Group, and optionally the Group Type, exists
> - And the Group must group at least a number within [MinSize..MaxSize] of the requested Object

</details>
    

#### Groups Table

| **Group** | **Group Type**                | **MinSize** | **MaxSize** | **Object**         | **Object Type**      | **Notes** |
|-----------|-------------------------------|-------------|-------------|--------------------|----------------------|-----------|
| IfcGroup  | Binari di corsa (Contenitore) | 2           | 2           | IfcFacilityPart    | TRACKSTRUCTURE       | From AL22 |
| IfcGroup  | Deviatoi                      | 1           | 1           | IfcElementAssembly | TURNOUTPANEL         | From TP01 |
| IfcGroup  | Massicciata                   | 1           |             | IfcCourse          | BALLASTBED           | From SP01 |
| IfcGroup  | Traverse                      | 1           |             | IfcGroup           | Segmento di traverse |           |
| IfcGroup  | Segmento di traverse          | 1           |             | IfcTrackElement    | SLEEPER              | From SP01 |
| IfcGroup  | Rotaie                        | 1           | 1           | IfcGroup           | Segmento di rotaia   |           |
| IfcGroup  | Segmento di rotaia            | 2           | 2           | IfcRail            | RAIL                 | From SP01 |

NOTE:
- when **MinSize** and **MaxSize** have the same value, it means exactly. Example: MinSize=MaxSize=1, means that the group must groups exactly 1 object of that type.
- when **MaxSize is empty**, it means **unlimited**. Example: MinSize=1; MaxSize=empty, means that the group must group 1 or more object of the requested type.
- the **Notes** column indicates (when the object to be grouped is coming from a pre-requisite test) which is the mentioned test.


### Group Spatial Connectivity

| **RULE ID** | **CRITERIA**                            | **VALUE [examples]**                     | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-----------------------------------------|------------------------------------------|----------------------------|----------------------------|
| SREF_01     | Spatial reference of groups is verified | As per Groups Spatial Connectivity Table | IfcGroup                   | Group Spatial Connectivity |

> **Acceptance criteria**: For the **Group Spatial Connectivity** capability, the validation procedure must verify that a Spatial Element of the requested type references (via `IfcRelReferencedInSpatialStructure`) exactly a given number of Groups of the requested type, no more and no less.

<details><summary>SREF_01 details: Spatial reference of groups is verified</summary>

> - Given a set of elements and groups taken from the [Group Spatial Connectivity Table](#Group-Spatial-Connectivity-Table)
> - Then the Spatial Element, and optionally the Spatial Element Type, exists
> - And the Spatial Element must reference at least a number within [MinSize..MaxSize] of the requested Group

</details>

#### Groups Spatial Connectivity Table

| **Spatial Element** | **Spatial Element Type** | **MinSize** | **MaxSize** | **Group**            | **Group Type**                 |
|---------------------|--------------------------|-------------|-------------|----------------------|--------------------------------|
| IfcRailway          | Località                 | 1           | 1           | IfcGroup             | Binari di corsa (Contenitore)  |
| IfcFacilityPart     | TRACKSTRUCTURE           | 1           | 1           | IfcGroup             | Deviatoi                       |
| IfcFacilityPart     | TRACKSTRUCTURE           | 1           | 1           | IfcGroup             | Massicciata                    |
| IfcFacilityPart     | TRACKSTRUCTURE           | 1           | 1           | IfcGroup             | Rotaie                         |
| IfcFacilityPart     | TRACKSTRUCTURE           | 1           | 1           | IfcGroup             | Traverse                       |

Examples:
1. A spatial element `IfcRailway`, of type `Località`, must reference exactly 1 `IfcGroup` of type `Binari di corsa (Contenitore)`
2. A spatial element `IfcFacilityPart`, of type `TRACKSTRUCTURE`, must reference exactly 1 `IfcGroup` of type `Deviatoi`


**IMPORTANT**: the track turnout (`IfcElementAssembly.TURNOUT`) should be contained in one spatial structure element only (i.e., `IfcFacilityPart.TRACKSTRUCTURE` named BC01). This should be done in the test **TP01**. The IfcGroup named *Deviatoi* must be referenced to the same spatial structure element. If this is done correctly, a check on the second row of the table above should return an error - as the file will contain two `IfcFacilityPart.TRACKSTRUCTURE`.  