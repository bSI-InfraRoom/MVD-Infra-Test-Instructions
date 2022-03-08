# Test instructions

| Documentation Code   | Test Title                        | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|-----------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E1_AL24   | (RFI) Mileage for two alignments  | E1 (ALRF)     | AL24      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |




## Summary (Intent)

This test case addresses the **export** and the **import** of the required IFC entities for the exchange of **stationing information for railway alignment without cant**. It builds on the test **AL22**, adding two `IfcReferent` entities, respectively to *Alignment 1_Primary route* and *Alignment 2_Diverted route*. These entities will be used:
- by the **export test** to verify the correct use of the nesting structure for `IfcReferent` into the `IfcAlignment`
- by the **import test**, along with some validation parameters, to verify the correct import of the provided alignemnt dataset.

Additional information:

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
- Alignment:
   1. IfcAlignment
   1. IfcAlignmentHorizontal
   1. IfcAlignmentVertical
   1. IfcAlignmentSegment
   1. IfcReferent
</details>

<details><summary>Concept Templates</summary> 

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the MVD**

- Project Context
   - Project Global Positioning
- Object Composition
   - Spatial Decomposition
- Object Connectivity
   - Spatial Containment
- Product Shape
   - Product Geometric Representation
       - Alignment Geometry
          - Alignment Geometry Gradient
 - Nesting
   - Alignment Layout
   - Object Nesting (IfcReferent usage)
</details>




## Model Dataset

This test case utilises **no particular dataset**. All information required to fulfil the test are captured in these Test Instructions.




## Test Case Imports

All validation criteria (and usages) of predecessors' tests shall be **verified for this test too** (regression test principle). Prerequisites for the present test case are listed below.

| TI Code                        | Test Instruction Title               | Comments |
|--------------------------------|--------------------------------------|----------|
| [IFC4.3AbRV_E1_AL22](./AL22)   | (RFI) Two alignments without cant    | none     |




## Usages, Constraints & Logic 

Other than the logic embedded by the IFC Entities & Concept Templates required for this test, **and** the constraints captured in the *Usages, Constraints & Logic* section of of precondition tests (**AL22**), **no additional constraints are applied**




## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`_`ExchangeCode`_`TestCode`_`SoftwareVendor`.`ifc` (Example: `IFC4.3AbRV_E2a_AL24_AmazingSoft.ifc`)




## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section**, and **the ones of pre-required tests** shall be verified, with no exception. :zap:

### General

- All the concept templates must be correctly implemented as presented in the validation criteria
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file
- All validation criteria of the pre-required tests shall apply here too

| **ID**  | **CRITERIA**                                      | **VALUE** | **COMMENT** |
|---------|---------------------------------------------------|-----------|-------------|
| ENAT_01 | Requested entities (and attributes) exist in file | See below |             |

<details><summary>Entities and attributes</summary>

`IfcReferent` (Alignment 1_Primary route)

| Attribute      | Value                            |
|----------------|----------------------------------|
| Name           | 0+000                            |
| Description    | Starting mileage for Alignemnt 1 |
| PredefinedType | REFERENCEMARKER                  |


`IfcReferent` (Alignment 2_Diverted route)

| Attribute      | Value                            |
|----------------|----------------------------------|
| Name           | 0+000                            |
| Description    | Starting mileage for Alignemnt 2 |
| PredefinedType | REFERENCEMARKER                  |

</details>

### Railway alignment (without cant)

> **Acceptance criteria**: For the **Railway alignment (without cant)** capability, the validation procedure must verify that **all** the following validation criteria are satisfied.
>
> If present, all criteria listed in [Usages, Constraints & Logic](#Usages,-Constraints-&-Logic), and in the same section of precondition tests, shall be verified too.

<details open><summary>Railway alignment (without cant)</summary> 

| **ID**  | **CRITERIA**                                                     | **VALUE**                                   | **COMMENT**                |
|---------|------------------------------------------------------------------|---------------------------------------------|----------------------------|
| ALIG_01 | Alignments contained in file                                     | 2                                           |                            |
| ALIG_02 | Component for Alignment 1_Primary route                          | 1 horizontal, 1 vertical                    |                            |
| ALIG_03 | Component for Alignment 2_Diverted route                         | 1 horizontal, 1 vertical                    |                            |
| ALIG_04 | The horizontal (H) layout is made only by these type of segments | straight line, circular arc, clothoid       |                            |
| ALIG_05 | The vertical (V) layout is made only by these type of segments   | straight line, circular arc                 |                            |

</details>

### Referent nesting

> **Acceptance criteria**: For the **Referent nesting** capability, the validation procedure must verify that **all** the following validation criteria are satisfied.
>
> If present, all criteria listed in [Usages, Constraints & Logic](#Usages,-Constraints-&-Logic), and in the same section of precondition tests, shall be verified too.


| **ID**  | **CRITERIA**                                                    | **COMMENT**                                                              |
|---------|-----------------------------------------------------------------|--------------------------------------------------------------------------|
| REFE_01 | Each alignment nests exactly 1 `IfcReferent`                    |                                                                          |
| REFE_02 | One referent is placed at the starting point of Alignment 1     | DistanceAlong = 0.000                                                    |
| REFE_03 | One referent is placed at the starting point of Alignment 2     | DistanceAlong = 0.000                                                    |
| REFE_04 | Each `IfcAlignment` has exactly two `IfcRelNests` relationships | One for Horizontal and Vertical components; another one for the referent |


Snippet:

<img src="./Dataset/referentNestingExample.png" width="900"/>

*Figure 1: Example of the pattern of entities to be instantiated for referent nesting, along with other structures such as alignment nesting, spatial containment, geometric representation.*




#### Validation parameters for import test
The parameters contained in the following sections are meant to verify the **correct import** of the alignment dataset provided in this test, into a receiving application.

**IMPORTANT**: to check most of the parameters below, the two `IfcReferent` entities above have to be defined.

<details open><summary> Alignment 1_Primary route </summary>

| ID      | CRITERIA                                                            | VALUE        |
|---------|---------------------------------------------------------------------|--------------|
| ALIG_10 | Horizontal Starting point Mileage (pk)                              | 0+000        |
| ALIG_11 | Horizontal Starting point DistAlong                                 | 0.0000       |
| ALIG_12 | Horizontal Starting point X                                         | 452413.9199  |
| ALIG_13 | Horizontal Starting point Y                                         | 4539456.4011 |
| ALIG_14 | Vertical Starting point Mileage                                     | 0+000        |
| ALIG_15 | Vertical Starting point Z                                           | 5.0000       |
| ALIG_16 | Horizontal Ending point Mileage (pk)                                | 0+876.3682   |
| ALIG_17 | Horizontal Ending point DistAlong                                   | 876.3682     |
| ALIG_18 | Horizontal Ending point X                                           | 453202.5241  |
| ALIG_19 | Horizontal Ending point Y                                           | 4539831.9287 |
| ALIG_20 | Vertical Ending point Mileage                                       | 0+876.3682   |
| ALIG_21 | Vertical Ending point Z                                             | 2.0000       |
| ALIG_22 | Total 2D length of alignment (horizontal projection)                | 876.3682     |
| ALIG_23 | Total 3D length of alignment                                        | 876.3819     |
| ALIG_24 | Height difference between start and end point of alignment 3D curve | -3.0000      |

</details>


<details open><summary> Alignment 2_Diverted route </summary>

| ID      | CRITERIA                                                            | VALUE        |
|---------|---------------------------------------------------------------------|--------------|
| ALIG_10 | Horizontal Starting point Mileage (pk)                              | 0+000        |
| ALIG_11 | Horizontal Starting point DistAlong                                 | 0.0000       |
| ALIG_12 | Horizontal Starting point X                                         | 452460.8898  |
| ALIG_13 | Horizontal Starting point Y                                         | 4539473.5425 |
| ALIG_14 | Vertical Starting point Mileage                                     | 0+000        |
| ALIG_15 | Vertical Starting point Z                                           | 5.0000       |
| ALIG_16 | Horizontal Ending point Mileage (pk)                                | 0+828.0965   |
| ALIG_17 | Horizontal Ending point DistAlong                                   | 828.0965     |
| ALIG_18 | Horizontal Ending point X                                           | 453208.8311  |
| ALIG_19 | Horizontal Ending point Y                                           | 4539818.3191 |
| ALIG_20 | Vertical Ending point Mileage                                       | 0+828.0965   |
| ALIG_21 | Vertical Ending point Z                                             | 2.0000       |
| ALIG_22 | Total 2D length of alignment (horizontal projection)                | 828.0965     |
| ALIG_23 | Total 3D length of alignment                                        | 828.1099     |
| ALIG_24 | Height difference between start and end point of alignment 3D curve | -3.0000      |

</details>



#### Notes on Pset usage for Linear Referencing Method and Stationing

There are two Pset applicable to IfcReferent that can be used for this test.
- `Pset_LinearReferencingMethod`: Describes the manner in which measurements are made along (and optionally offset from) a linear element.
- `Pset_Stationing`: Specifies stationing parameters for IfcReferent.

Below are some notes on the use of these Pset for `IfcReferent`. These are mainly note for a good use, **not to be considered as validation criteria to be passed**.

For `Pset_LinearReferencingMethod`, you will want to check that: 
- The property **LRMType** is set correctly. Example: in this test, being the referents placed at the origin point of each alignment to mark its initial stationing (i.e., 0+000), the the property value shall be set to **LRM_ABSOLUTE**

For `Pset_Stationing`:
- The **Station** property shall have a value consistent with the *DistanceAlong* value used to place teh referent (in this case, 0.000 m) 