# Test instructions

| Documentation Code   | Test Title                    | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|-------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_PP01  | (RFI) Add properties          | E2a (TRAS)    | PP01      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |




## Summary (Intent)

This test case addresses the **export** of the required IFC entities for the exchange of **objects properties** information. The test includes both property sets belonging to the IFC standard and custom sets; both on types and occurrences.

- Refer to [Test Case Imports](#Test-Case-Imports) to know the prerequisites for the present test.

- The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

- :zap: This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test :zap:




## Itemised Roots

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_E2a exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Other test-specific entities:
   1. IfcPropertySet
   1. IfcPropertySingleValue
   1. IfcPropertyEnumeratedValue
</details>

<details><summary>Concept Templates</summary> 

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Object definition
   - Property Sets for Objects
   - Property Sets for Types
</details>




## Model Dataset

This test case utilises **no particular dataset**. All information required to fulfil the test are captured in these Test Instructions.




## Test Case Imports

All validation criteria (and usages) of predecessors' tests shall be **verified for this test too** (regression test principle). Prerequisites for the present test case are listed below.

| TI Code                       | Test Instruction Title | Comments |
|-------------------------------|------------------------|----------|
| [IFC4.3AbRV_E2a_GR01](./GR01) | (RFI) Group objects    |          |




## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_PP01_AmazingSoft.ifc`)
 



## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section** shall be verified, with no exception. :zap:

### General

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------------------|----------------------------|
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       | na                         | na                         |




### Standard & Custom properties for objects and object types

| **RULE ID** | **CRITERIA**                                             | **VALUE [examples]**    | **ENTITY (if applicable)** | **CT (if applicable)**                              |
|-------------|----------------------------------------------------------|-------------------------|----------------------------|-----------------------------------------------------|
| PSET_01     | The model does not contain unrequested property sets     | As per Properties Table | na                         | Property Sets for Objects & Property Sets for Types |
| PNAM_01     | The property set does not contain unrequested properties | As per Properties Table | na                         | Property Sets for Objects & Property Sets for Types |
| PTEX_01     | Property values belong to a list of values               | As per Properties Table | na                         | Property Sets for Objects & Property Sets for Types |
| PVAL_01     | Property values are not null and not empty               | As per Properties Table | na                         | Property Sets for Objects & Property Sets for Types |
| PVAL_02     | Requested property value types are found                 | As per Properties Table | na                         | Property Sets for Objects & Property Sets for Types |

> **Acceptance criteria**: For the **Properties for objects and object types** capability, the validation procedure must verify that both standard and custom property sets requested by the test case (including relative properties and values) are present in the IFC file.
> See below for further specification of each rule.

<details><summary>PSET_01: The model does not contain unrequested property sets</summary>

> - Given a set of properties taken from the [Properties Table](#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - Then the IfcEntity is associated at most to the property set with the PropertySet Name
</details>

<details><summary>PNAM_01: The property set does not contain unrequested properties</summary>

> - Given a set of properties taken from the [Properties Table](#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - Then the property set has at most the properties with the Property Name
</details>

<details><summary>PTEX_01: Property values belong to a list of values</summary>

> - Given a set of properties taken from the [Properties Table](#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - Then the property value is part of the List Of Values
</details>

<details><summary>PVAL_01: Property values are not null and not empty</summary>

> - Given a set of properties taken from the [Properties Table](#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - Then the property value is not null
> - And the property value is not empty
</details>

<details><summary>PVAL_02: Requested property value types are found</summary>

> - Given a set of properties taken from the [Properties Table](#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - And the property value is not null
> - Then the property type is equal to the Property Value Type
</details>

#### Properties Table

**NOTE**: the correct value of each property is not covered by this test. As long as the value is of the specified data type, and (if the case applies) belonging to the list of enumerated values, then the test shall be considered passed.

| **Entity**      | **Entity Type**         | **PropertySet Name**         | **Property Name**            | **Property Value Type**     | **Enumerated Values**                                                                              | **Value type**             |
|-----------------|-------------------------|------------------------------|------------------------------|-----------------------------|----------------------------------------------------------------------------------------------------|----------------------------|
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | Binario                      | IfcLabel                    | Pari, Dispari, Unico                                                                               | IfcPropertyEnumeratedValue |
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | Codice binario SAS           | IfcLabel                    |                                                                                                    | IfcPropertySingleValue     |
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | n. deviatoi elettrici        | IfcInteger                  |                                                                                                    | IfcPropertySingleValue     |
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | Profilo manutentivo L94      | IfcLabel                    | <=40 t/g, >100 t/g, 40< t/g <=100                                                                  | IfcPropertyEnumeratedValue |
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | Binario elettrificato        | IfcLogical                  |                                                                                                    | IfcPropertySingleValue     |
| IfcTrackElement | SLEEPER                 | Pset_TrackElementTypeSleeper | SleeperType                  | IfcLabel                    | COMPOSITESLEEPER, CONCRETESLEEPER, INSULATEDSTEELSLEEPER, MONOBLOCKCONCRETESLEEPER, NOTINSULATEDSTEELSLEEPER, NOTKNOWN, OTHER, TWOBLOCKCONCRETESLEEPER, UNSET, WOODENSLEEPER | IfcPropertyEnumeratedValue |
| IfcTrackElement | SLEEPER                 | Pset_TrackElementTypeSleeper | FasteningType                | IfcLabel                    |                                                                                                    | IfcPropertySingleValue     |
| IfcCourse       | Segmento di massicciata | PSet_CourseCommon            | NominalLength                | IfcNonNegativeLengthMeasure |                                                                                                    | IfcPropertySingleValue     |
| IfcCourse       | Segmento di massicciata | PSet_CourseCommon            | NominalThickness             | IfcNonNegativeLengthMeasure |                                                                                                    | IfcPropertySingleValue     |
| IfcCourse       | Segmento di massicciata | PSet_CourseCommon            | NominalWidth                 | IfcNonNegativeLengthMeasure |                                                                                                    | IfcPropertySingleValue     |
| IfcCourseType   | Segmento di massicciata | RFI_S22600                   | Tipo massicciata             | IfcLabel                    | Misto, Calcareo, Tenace                                                                            | IfcPropertyEnumeratedValue |
| IfcGroup        | Segmento di rotaia      | RFI_S22700                   | Galleria                     | IfcLogical                  |                                                                                                    | IfcPropertySingleValue     |
| IfcGroup        | Segmento di rotaia      | RFI_S22700                   | Tipo binario di appartenenza | IfcLabel                    | BINARIO CENTRALIZZATO, BINARIO DI CORSA, BINARIO DI FASCIO, BINARIO IMP. SMISTAMENTO AUTOMATICO    | IfcPropertyEnumeratedValue |