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




## Usages, Constraints & Logic 

Other than the logic embedded by the IFC Entities & Concept Templates required for this test, **and** the constraints captured in the *Usages, Constraints & Logic* section of of precondition tests, **no additional constraints are applied**




## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_PP01_AmazingSoft.ifc`)
 



## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section** shall be verified, with no exception. :zap:

### General

- All the concept templates must be correctly implemented as presented in the validation criteria
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file
- All validation criteria of the pre-required tests shall apply here too




### Standard & Custom properties for objects and object types

> **Acceptance criteria**: For the **Properties for objects and object types** capability, the validation procedure must verify that both standard and custom property sets requested by the test case (including relative properties and values) are present in the IFC file.

(See below the table for further specification of each criteria)
| ID       | CRITERIA                                                 |
|----------|----------------------------------------------------------|
| PSET_002 | The model does not contain unrequested property sets     |
| PNAM_002 | The property set does not contain unrequested properties |
| PTEX_001 | Property values belong to a list of values               |
| PVAL_001 | Property values are not null and not empty               |
| PVAL_002 | Requested property value types are found                 |

PSET_002: The model does not contain unrequested property sets
> - Given a set of properties taken from the [Test Case Properties Table](#Test-Case-Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - Then the IfcEntity is associated at most to the property set with the PropertySet Name

PNAM_002: The property set does not contain unrequested properties
> - Given a set of properties taken from the [Test Case Properties Table](#Test-Case-Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - Then the property set has at most the properties with the Property Name

PTEX_001: Property values belong to a list of values
> - Given a set of properties taken from the [Test Case Properties Table](#Test-Case-Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - Then the property value is part of the List Of Values

PVAL_001: Property values are not null and not empty
> - Given a set of properties taken from the [Test Case Properties Table](#Test-Case-Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - Then the property value is not null
> - And the property value is not empty

PVAL_002: Requested property value types are found
> - Given a set of properties taken from the [Test Case Properties Table](#Test-Case-Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - And the property value is not null
> - Then the property type is equal to the Property Value Type

#### Test Case Properties Table

:construction: under construction :construction:

| Entity          | Entity Type             | PropertySet Name             | Property Name                | Property Value Type         | List Of Values                                                                                                                                                               | Value type                 |
|-----------------|-------------------------|------------------------------|------------------------------|-----------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | Binario                      | IfcLabel                    | Pari, Dispari, Unico                                                                                                                                                         | IfcPropertyEnumeratedValue |
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | Codice binario SAS           | IfcLabel                    |                                                                                                                                                                              | IfcPropertySingleValue     |
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | n. deviatoi elettrici        | IfcInteger                  |                                                                                                                                                                              | IfcPropertySingleValue     |
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | Profilo manutentivo L94      | IfcLabel                    | <=40 t/g, >100 t/g, 40< t/g <=100                                                                                                                                            | IfcPropertyEnumeratedValue |
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | Binario elettrificato        | IfcLogical                  |                                                                                                                                                                              | IfcPropertySingleValue     |
| IfcTrackElement | SLEEPER                 | Pset_TrackElementTypeSleeper | SleeperType                  | IfcLabel                    | COMPOSITESLEEPER, CONCRETESLEEPER, INSULATEDSTEELSLEEPER, MONOBLOCKCONCRETESLEEPER, NOTINSULATEDSTEELSLEEPER, NOTKNOWN, OTHER, TWOBLOCKCONCRETESLEEPER, UNSET, WOODENSLEEPER | IfcPropertyEnumeratedValue |
| IfcTrackElement | SLEEPER                 | Pset_TrackElementTypeSleeper | FasteningType                | IfcLabel                    |                                                                                                                                                                              | IfcPropertySingleValue     |
| IfcCourse       | Segmento di massicciata | PSet_CourseCommon            | NominalLength                | IfcNonNegativeLengthMeasure |                                                                                                                                                                              | IfcPropertySingleValue     |
| IfcCourse       | Segmento di massicciata | PSet_CourseCommon            | NominalThickness             | IfcNonNegativeLengthMeasure |                                                                                                                                                                              | IfcPropertySingleValue     |
| IfcCourse       | Segmento di massicciata | PSet_CourseCommon            | NominalWidth                 | IfcNonNegativeLengthMeasure |                                                                                                                                                                              | IfcPropertySingleValue     |
| IfcCourseType   | Segmento di massicciata | RFI_S22600                   | Tipo massicciata             | IfcLabel                    | Misto, Calcareo, Tenace                                                                                                                                                      | IfcPropertyEnumeratedValue |
| IfcGroup        | Segmento di rotaia      | RFI_S22700                   | Galleria                     | IfcLogical                  |                                                                                                                                                                              | IfcPropertySingleValue     |
| IfcGroup        | Segmento di rotaia      | RFI_S22700                   | Tipo binario di appartenenza | IfcLabel                    | BINARIO CENTRALIZZATO, BINARIO DI CORSA, BINARIO DI FASCIO, BINARIO IMP. SMISTAMENTO AUTOMATICO                                                                              | IfcPropertyEnumeratedValue |


</details>