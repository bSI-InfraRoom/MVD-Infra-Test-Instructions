# Test instructions

| Documentation Code   | Test Title                    | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|-------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_CL01  | (RFI) Classify objects        | E2a (TRAS)    | CL01      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |




## Summary (Intent)

This test case addresses the **export** of the required IFC entities for the exchange of **objects classification** information. Specifically, this test will use an external reference (i.e., buildingSMART Data Dictionary) to classify some railway objects.

- Refer to [Test Case Imports](#Test-Case-Imports) to know the prerequisites for the present test.

- The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

- :zap: This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test :zap:




## Itemised Roots

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_E2a exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Track domain physical products:
   1. IfcTrackElement
- Other test-specific entities:
   1. IfcClassification
   1. IfcClassificationReference
</details>

<details><summary>Concept Templates</summary> 

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Object Association
   - Classification Association
</details>




## Model Dataset

This test case utilises **no particular dataset**. All information required to fulfil the test are captured in these Test Instructions.




## Test Case Imports

All validation criteria (and usages) of predecessors' tests shall be **verified for this test too** (regression test principle). Prerequisites for the present test case are listed below.

| TI Code                       | Test Instruction Title                 | Comments |
|-------------------------------|----------------------------------------|----------|
| [IFC4.3AbRV_E2a_SP01](./SP01) | (RFI) Track super-structure for single track |          |




## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_CL01_AmazingSoft.ifc`)




## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section** shall be verified, with no exception. :zap:

### General

### General

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------------------|----------------------------|
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       | na                         | na                         |




### Object classification via external reference

> **Acceptance criteria**: For the **Object classification via external reference** capability the validation procedure must verify that all the sleepers (IfcTrackElement.SLEEPER) are to be classified using the correspondent classification inside the bSDD (buildingSMART Data Dictionary). The example below shows how the classification is expected to be done.

**Given** all sleepers present in the model (below is an example of two instances of type sleeper)

> `#21 = IFCTRACKELEMENT('0$kRFU7b50rP3_$BI9iljk', #1, 'Sleeper 0001', 'Sleeper', $, #368035, #368038, $, .SLEEPER.);`
>
> `#22 = IFCTRACKELEMENT('00sqkYXHv4OfDNJGKpHKi$', #1, 'Sleeper 0002', 'Sleeper', $, #368052, #368055, $, .SLEEPER.);`

**Then** these are classified using `IfcClassification`, `IfcClassificationReference`, and `IfcRelAssociatesClassification`.

<ins>Below is an example of the attributes' values, plus a mapping of these attributes to the bSDD data model.</ins>

`IfcClassification`

| Example instance             | Source           | Edition       | EditionDate | Name       | Description | Specification                                                 | ReferenceTokens |
|------------------------------|------------------|---------------|-------------|------------|-------------|---------------------------------------------------------------|-----------------|
| #45 = IFCCLASSIFICATION      | 'buildingSMART'    | '4.3rc4'        | $           | 'IFC'        | $           | http://identifier.buildingsmart.org/uri/buildingsmart/ifc-4.3 | $               |
|                              | IFCLABEL         | IFCLABEL      | IFCDATE     | IFCLABEL   | IFCTEXT     | IFCURIREFERENCE                                               | IFCIDENTIFIER   |
| **Mapping with bSDD data model** | *OrganizationCode* | *DomainVersion* | *ReleaseDate* | *DomainName* | NA          | *DomainNamespaceUri*                                            | NA              |

`IfcClassificationReference`

| Example instance                 | Location                                                                                   | Identification         | Name                    | ReferencedSource                 | Description                                                                                                        | Sort          |
|----------------------------------|--------------------------------------------------------------------------------------------|------------------------|-------------------------|----------------------------------|--------------------------------------------------------------------------------------------------------------------|---------------|
| #46 = IFCCLASSIFICATIONREFERENCE | http://identifier.buildingsmart.org/uri/buildingsmart/ifc-4.3/class/ifctrackelementsleeper | 'ifctrackelementsleeper' | 'IfcTrackElement.SLEEPER' | #45                              | $ | $             |
|                                  | IFCURIREFERENCE                                                                            | IFCIDENTIFIER          | IFCLABEL                | IFCCLASSIFICATIONREFERENCESELECT | IFCTEXT                                                                                                            | IFCIDENTIFIER |
| **Mapping with bSDD data model**     | *DomainNamespaceUri/class/code*                                                              | *Code*                   | *Name*                    | NA                               | *Definition*                                                                                                         | NA            |

`IfcRelAssociatesClassification`

| Example instance                     | GlobalId               | OwnerHistory    | Name                        | Description | RelatedObjects      | RelatingClassification  |
|--------------------------------------|------------------------|-----------------|-----------------------------|-------------|---------------------|-------------------------|
| #47 = IFCRELASSOCIATESCLASSIFICATION | `0OLroQf6D0tfjW0rwFRKeK` | #10             | 'Classification Relationship' | $           | (#21,#22)           | #46                     |
|                                      | IFCGLOBALLYUNIQUEID    | IFCOWNERHISTORY | IFCLABEL                    | IFCTEXT     | IFCDEFINITIONSELECT | IFCCLASSIFICATIONSELECT |


</details>