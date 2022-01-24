# Scaffold Test Instructions

| Exchange Code       | Abbreviation | Exchange Name               | Test Cases |
|---------------------|--------------|-----------------------------|------------|
| **IFC4x3_AbRV-E0**  | SCAF         | Scaffold Test Instructions  | 2          |

Exchange Lead: @Alex.Brad1eyCT

## Summary

The E0 group of test instructions does not constitute a testable exchange definition, it is a group of test case definitions that form common functional blocks within other test cases. Examples include cases such as project setup and global positioning which form the scaffold (or 'boiler plate') of any IFC exchange file, or cases such as classification and grouping which are common templates that can be applied to any entities within an IFC exchange file.

The purpose of the definition of functional block test cases is to reduce the repetition of common concepts within test cases, and provide a single set of validation criteria for the given functional block. Test cases reuse IFC exchange file content and related validation criteria from the functional blocks to focus on the scope and testing of the case on the relevant concepts of the test, not the supporting content required for a valid IFC exchange file. In Addition, functional blocks look to reduce the overall implementation and debugging process for implementers by providing a test once use many times approach to dependent test concepts, that is documented in a traceable and declarative manner.


### Scope
The following entities & concept templates are addressed within the scope of scaffold test instructions for reuse and application in dependent test cases:

:construction: under construction :construction:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- Model Setup
  - *IfcProject*
  - *IfcUnitAssignment*
  - *IfcSIUnit*
  - *IfcMonetaryUnit*
  - *IfcDerivedUnit*
  - *IfcConversionBasedUnit*
  - *IfcConversionBasedUnitWithOffset*
- Global Positioning
  - *IfcGeometricRepresentationContext*
  - *IfcMapConversion*
  - *IfcProjectedCRS*
- Classification
  - *IfcClassification*
  - *IFcClassificationReference*

</details>

<details><summary>Concept Templates</summary>

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- Project Context
  - *Project Classification Information*
  - *Project Declaration*
  - *Project Global Positioning*
  - *Project Representation Context*
  - *Project Units*
- Object Definition
  - *Property Sets for Objects*
- Object Attributes
  - *Software Identity*
  - *Revision Control*

</details>


## Test Instructions

| TI Code                            | Test Instruction Title             |
|------------------------------------|------------------------------------|
| [**IFC4x3_AbRV-E0-PROJ**](./PROJ)  | Project Setup                      |
| [**IFC4x3_AbRV-E0-PROJ**](./GLPO)  | Global Positioning                 |
| [**IFC4x3_AbRV-E0-PROJ**](./CLAS)  | Object Classification              |
  