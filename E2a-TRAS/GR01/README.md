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

This test case utilises **no particular dataset**. All information required to fulfil the test are captured in these Test Instructions.




## Test Case Imports

All validation criteria (and usages) of predecessors' tests shall be **verified for this test too** (regression test principle). Prerequisites for the present test case are listed below.

| TI Code                       | Test Instruction Title                       | Comments |
|-------------------------------|----------------------------------------------|----------|
| [IFC4.3AbRV_E2a_SP01](./SP01) | (RFI) Track super-structure for single track |          |
| [IFC4.3AbRV_E2a_TP01](./TP01) | (RFI) Turnout panel between two tracks       |          |



## Usages, Constraints & Logic 

The following itemised restrictions and constraints shall be placed on IFC Entities & Concept Templates:

<details><summary>Semantic Usages, Constraints & Logic</summary>

The following itemised Usages, Constraints & Logic are normative entries within the AbRV MVD and MUST be satisfied to meet the defined validation criteria

| ID       | CRITERIA                           | COMMENTS                                                                                                                                                       |
|----------|------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| GROU_101 | Circular reference is not allowed  | Circular reference is not allowed, neither direct (if A includes B, B cannot includes A), nor indirect (if A includes B and B includes C, C cannot includes A) |
| GROU_102 | Only direct inclusion is allowed   | Example: if A includes B and B includes C, A cannot includes C)                                                                                                |
| GROU_103 | Same-level grouping is not allowed | If two or more Group are part of the same Group, they cannot include each others. Example: if A groups B and C, B cannot group C and vice versa)               |
| GROU_104 | Group rooting                      | All Groups that do not have a parent Group must be linked to the IfcProject with an IfcRelDeclares relationship, as per Project Declaration template           |
| GROU_105 | Group typing via ObjectType        | *All group types shall be expressed using the ObjectType (5<sup>th</sup> attribute) of each occurrence of IfcGroup                                             |

*: this is the only method to express group typing, due to the fact that: i) IfcGroup misses the PredefinedType attribute; and ii) object typing by instantiation of IfcTypeObject is discouraged from IFC4 onward.

</details>

<details><summary>Model Geometry</summary>
The Test case does not require additional checks related to Model Geometry

</details>



## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_GR01_AmazingSoft.ifc`)




## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section** shall be verified, with no exception. :zap:

### General

- All the concept templates must be correctly implemented as presented in the validation criteria
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file
- All validation criteria of the pre-required tests shall apply here too


| **ID**  | **CRITERIA**                                      | **VALUE** | **COMMENT** |
|---------|---------------------------------------------------|-----------|-------------|
| ENAT_01 | Requested entities (and attributes) exist in file | See below |             |

<details><summary>Entities and attributes</summary>

`IfcGroup` (12 occurrences)

| #  | Name                   | Description                | ObjectType                    |
|----|------------------------|----------------------------|-------------------------------|
| 01 | LO1336-BC              | Binari di corsa di Foligno | Binari di corsa (Contenitore) |
| 02 | LO1336-BC-BC01-DEV     | Deviatoi BC01              | Deviatoi                      |
| 03 | LO1336-BC-BC01-ROT     | Rotaie BC01                | Rotaie                        |
| 04 | LO1336-BC-BC01-MAS     | Massicciata BC01           | Massicciata                   |
| 05 | LO1336-BC-BC01-TRA     | Traverse BC01              | Traverse                      |
| 06 | LO1336-BC-BC02-ROT     | Rotaie BC02                | Rotaie                        |
| 07 | LO1336-BC-BC02-MAS     | Massicciata BC02           | Massicciata                   |
| 08 | LO1336-BC-BC02-TRA     | Traverse BC02              | Traverse                      |
| 09 | LO1336-BC-BC01-ROT-R01 | Segmento di rotaia BC01    | Segmento di rotaia            |
| 10 | LO1336-BC-BC02-ROT-R02 | Segmento di rotaia BC02    | Segmento di rotaia            |
| 11 | LO1336-BC-BC01-TRA-T01 | Segmento di traverse BC01  | Segmento di traverse          |
| 12 | LO1336-BC-BC02-TRA-T02 | Segmento di traverse BC02  | Segmento di traverse          |

</details>


### Object grouping

> **Acceptance criteria**: For the **Object grouping** capability, the validation procedure must verify that a group of the requested type is grouping (via `IfcRelAssignsToGroup`) exactly a given number of objects of the requested type, no more and no less.

(See below the table for further specification of each criteria)
| ID       | CRITERIA                                    | VALUE                                         |
|----------|---------------------------------------------|-----------------------------------------------|
| GROU_001 | Mandatory objects are present in the groups | See below the table for further specification |


GROU_001: Mandatory objects are present in the groups
> - Given a set of groups taken from the [Test Case Group Table](#Test-Case-Group-Table)
> - When the Group, and optionally the Group Type, exists
> - Then the Group must group at least a number within [Minimum..Maximum] of the requested Object
>
> NOTE:
> - for typing of groups refer to the Validation criteria of the **Object typing** capability
> - when **Minimum** and **Maximum** have the same value, it means exactly. Example: Minimum=Maximum=2, means that the group must group exactly 2 objects of the requested type.
> - when **Maximum** is empty, it means unlimited. Example: Minimum=1; Maximum=empty, means that the group must group 1 or more elements of the requested type.
    

#### Test Case Group Table

| Group    | Group Type                    | Minimum | Maximum | Object             | Object Type          | COMMENT   | 
|----------|-------------------------------|---------|---------|--------------------|----------------------|-----------|
| IfcGroup | Binari di corsa (Contenitore) | 2       | 2       | IfcFacilityPart    | TRACKSTRUCTURE       | From AL22 |
| IfcGroup | Deviatoi                      | 1       | 1       | IfcElementAssembly | TURNOUTPANEL         | From TP01 |
| IfcGroup | Massicciata                   | 1       |         | IfcCourse          | BALLASTBED           | From SP01 |
| IfcGroup | Traverse                      | 1       |         | IfcGroup           | Segmento di traverse |           |
| IfcGroup | Segmento di traverse          | 1       |         | IfcTrackElement    | SLEEPER              | From SP01 |
| IfcGroup | Rotaie                        | 1       | 1       | IfcGroup           | Segmento di rotaia   |           |
| IfcGroup | Segmento di rotaia            | 2       | 2       | IfcRail            | RAIL                 | From SP01 |

NOTE:
- when **Minimum** and **Maximum** have the same value, it means exactly. Example: Minimum=Maximum=1, means that the group must groups exactly 1 object of that type.
- when **Maximum is empty**, it means **unlimited**. Example: Minimum=1; Maximum=empty, means that the group must group 1 or more object of the requested type.
- the **COMMENT** column indicates (when the object to be grouped is coming from a pre-requisite test) which is the mentioned test.


### Group Spatial Connectivity

> **Acceptance criteria**: For the **Group Spatial Connectivity** capability, the validation procedure must verify that a Spatial Element of the requested type references (via `IfcRelReferencedInSpatialStructure`) exactly a given number of Groups of the requested type, no more and no less.

| Spatial Element | Spatial Element Type | Minimum | Maximum | Product or Group | Product Type or Group Type    |
|-----------------|----------------------|---------|---------|------------------|-------------------------------|
| IfcRailway      | Località             | 1       | 1       | IfcGroup         | Binari di corsa (Contenitore) |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Deviatoi                      |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Massicciata                   |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Rotaie                        |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Traverse                      |

**IMPORTANT**: the track turnout (`IfcElementAssembly.TURNOUT`) should be contained in one spatial structure element only (i.e., `IfcFacilityPart.TRACKSTRUCTURE` named BC01). This should be done in the test **TP01**. The IfcGroup named *Deviatoi* must be referenced to the same spatial structure element. If this is done correctly, a check on the second row of the table above should return an error - as the file will contain two `IfcFacilityPart.TRACKSTRUCTURE`.  