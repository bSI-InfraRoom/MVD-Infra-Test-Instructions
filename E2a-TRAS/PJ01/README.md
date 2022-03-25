# Test instructions

| Documentation Code   | Test Title                    | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|-------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_PJ01  | Project Setup                 | E2a (TRAS)    | PJ01      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |



## Summary (Intent)

This test case addresses the **export** of the required IFC entities for the exchange of **project setup** information.

- Refer to [Test Case Imports](#Test-Case-Imports) to know the prerequisites for the present test.

- The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

- :zap: This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test :zap:




## Itemised Roots

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_E2a exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Model setup:
   1. IfcProject
   1. IfcSIUnit
   1. IfcGeometricRepresentationContext
   1. IfcUnitAssignment
</details>

<details><summary>Concept Templates</summary> 

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Project Context
   - Project Representation Context
   - Project Units
</details>




## Model Dataset

All information required to fulfil the test are captured in these Test Instructions. See [Entities Table](#Entities-Table)




## Test Case Imports

This test case has **no prerequisites**. All validation criteria to be verified are listed of these Test Instructions.




## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_PJ01_AmazingSoft.ifc`)




## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section** shall be verified, with no exception. :zap:

### General

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------------------|----------------------------|
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       | na                         | na                         |
| GENE_01     | All requested entities (and attributes) exist in file             | As per Entities Table | na                         | na                         |


### Project Setup

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------------------|----------------------------|
| ORIG_01     | Origin of Coordinate System is set as requested                   | [(0., 0., 0.)]        |                            | Project Global Positioning |
| ORIG_02     | True north is set as requested                                    | [(0., 1., 0.)]        |                            | Project Global Positioning |
| DIST_01     | Unit of measure for all distances                                 | [meter]               |                            | Project Units              |
| ANGL_01     | Unit of measure all angles                                        | [radian]              |                            | Project Units              |
| DIST_02     | Required precision for distances                                  | [0,0001]              | all alignment segments     | na                         |
| ANGL_02     | Required precision for angles and slope                           | [0,000001]            |                            | na                         |

> **Acceptance criteria**
 For the **Project Setup** capability, the validation procedure must verify that:
> - `IfcProject` entity is the top most element in the project structure. It represents the bare minimum of an IFC file exchange with no content, only boilerplate code.
> - `IfcUnitAssignment` entity is used to define the global units for measures and values, when the units are not otherwise defined. For the specific units required by this test refer to the table below.
> - `IfcGeometricRepresentationContext` entity is used to define the is the global context of the geometry.

#### Entities Table

| **Element**                       | **Attribute**            | **Value**            | **Notes**                                                                                                                               |
|-----------------------------------|--------------------------|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| IfcProject                        | GlobalId                 |                      | Machine-generated, according to [this specification](https://technical.buildingsmart.org/resources/ifcimplementationguidance/ifc-guid/) |
|                                   | Name                     | 'IFC4.3AbRV Project' |                                                                                                                                         |
|                                   | Description              | 'Project setup'      |                                                                                                                                         |
|                                   | RepresentationContexts   |                      | Points to `IfcGeometricRepresentationContext`                                                                                           |
|                                   | UnitsInContext           |                      | Points to `IfcUnitAssignment`                                                                                                           |
| IfcGeometricRepresentationContext | ContextType              | 'Model'              |                                                                                                                                         |
|                                   | CoordinateSpaceDimension | 3                    |                                                                                                                                         |
|                                   | Precision                | 1.00E-06             |                                                                                                                                         |
|                                   | WorldCoordinateSystem    |                      | Points to `IfcAxis2Placement3D`                                                                                                         |
|                                   | TrueNorth                |                      | Points to Y direction (0., 1., 0.)                                                                                                      |
| IfcAxis2Placement3D               | Location                 |                      | Points to `IfcCartesianPoint` (0., 0., 0.)                                                                                              |
|                                   | Axis                     |                      | Points to Z direction (0., 0., 1.)                                                                                                      |
|                                   | RefDirection             |                      | Points to X direction (1., 0., 0.)                                                                                                      |


Example of SI unit encoding
```
#17 = IFCUNITASSIGNMENT((#18, #19, #20, #24));
#18 = IFCSIUNIT(*, .LENGTHUNIT., $, .METRE.);
#19 = IFCSIUNIT(*, .AREAUNIT., $, .SQUARE_METRE.);
#20 = IFCSIUNIT(*, .VOLUMEUNIT., $, .CUBIC_METRE.);
```

Example of non-SI unit used for angles: degree instead of radian
```
#22 = IFCSIUNIT(*, .PLANEANGLEUNIT., $, .RADIAN.);
#23 = IFCMEASUREWITHUNIT(IFCPLANEANGLEMEASURE(0.017453292519943295), #22);
#24 = IFCCONVERSIONBASEDUNIT(#1, .PLANEANGLEUNIT., 'degree', #23);
```