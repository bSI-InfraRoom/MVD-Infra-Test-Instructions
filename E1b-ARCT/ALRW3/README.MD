
# ALRW3 - Cosine (Horizontal Layout + Cant Layout)

# Summary (Intent)

The testcases provided in this folder shall check the proper implementation of IfcAlignment transition bend with cant in a very compact but nevertheless comprehensive manner. The testparameters given describe synthetic cases for the tested transition bend types.

The testcases were developed in the alignment workpackage of the IFC Rail project and were later on refined with the cant parameter. Input data are the parameters as the are typically used in track engineering.

The supplied parameterlists and pointlists were calculated according to the principle of diverse development using two  independent implementations.

Implementation 1 is based on a set of preexisting python modules using a very generic double integration approach to calculate x,y coordinates from the base parameters length, curvature and cant.

Implementation 2 is based on the first implementation of an IFC tool vendor consisting of the following steps:
Translation of the segment parameters from the so called business representation in the product layer into IFC entities belonging to the IFC geometry core. (a.k.a. enrichment).
Evaluation of geometry core entities to obtain the 3D geometry.
Export of the obtained points into 2D x,y pointlists and an applied cant value which represents the contribution of cant to the track axis (a.k.a. alignment).

The lists of x,y and cant contribution to track axis z + the resulting inclination angle are given as a result list.
Testdata is provided for transition  bends stated below.

* Clothoid
* Helmert
* Bloss
* Cosine
* Sine
* Viennese Bend

# Itemised Roots

*This section lists the primary entities and concept templates being validated by this test instruction, these are listed to understand the scope of the data entities being addressed. this is the documentation of the data placed within BIMQ*

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- *Rooted entities*
  - *IfcProject*
  - *IfcSite*
  - *IfcAlignment*
  - *IfcAlignmentSegment*
  - *IfcAlignmentHorizontal*
  - *IfcAlignmentCant*

- *Non-Rooted entities*
  - *IfcUnitAssignment*
  - *IfcSIUnit*
  - *IfcProductDefinitionShape*
  - *IfcShapeRepresentation*
  - *IfcAlignmentHorizontalSegment*
  - *IfcAlignmentCantSegment*
  - *IfcAxis2Placement2D*
  - *IfcAxis2Placement3D*
  - *IfcCompositeCurve*
  - *IfcCurveSegment*
  - *IfcLocalPlacement*
  - *IfcGeometricRepresentationContext*
  - *IfcSegmentedReferenceCurve*
  - *IfcThirdOrderPolynomialSpiral*

</details>

<details><summary>Concept Templates</summary>

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- *Rooted Templates*
  - *Project Units*
  - *Project Representation Context*
  - *Spatial Decomposition*
  - *Spatial Container*
  - *Alignment Layout*
  - *Alignment Geometry Cant*
  - *Object User Identity*
  - *Software Identity*

- *Partial Templates*
  - *Bloss Transition Segment*



</details>

# Test Case Imports

For each of the 64 supplied testcases the required set of baseparameters are given.

# Usages, Constraints & Logic

Each test consist of one alignment segment only. Change in curvature and change in applied cant extend along the complete length of the segment.

For each transition bend types the following combinations are given:

* straight line connected with leftleaning circular arc segment
* straight line connected with rightleaning circular arc segment
* leftleaning circular arc segment connected to straight line
* rightleaning circular arc segment connected to straight line
* leftleaning circular arc segment connected to a second leftleaning circular arc segment with smaller radius
* rightleaning circular arc segment connected to a second rightleaning circular arc segment with smaller radius
* leftleaning circular arc segment connected to a second leftleaning circular arc segment with greater radius
* rightleaning circular arc segment connected to a second rightleaning circular arc segment with greater radius

## Expected Results

For each case, it requires:

* an IFC 4.3 file, and optionally

* Tables of points (one row for each station) along the tested alignment segment containing the values listed below:
  * Station on segment
  * Seg-specific X-coordinate
  * Seg-specific Y-coordinate
  * Curvature at station
  * Applied Cant at station
  * Cant Angle at station



## Validation criteria

The calculated values shall be identical up to the ??? digit after the decimal point.

### General

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------------------|----------------------------|
| GENE_01     | All requested entities (and attributes) exist in file             | As per Entities Table | na                         | na                         |

#### Entities Table

| **Element**            | **Attribute**   | **Value**                                               | **Notes** |
|------------------------|-----------------|---------------------------------------------------------|-----------|
| IfcAlignment           | Name            | Alignment_1                                             |           |
|                        | ObjectType      | Railway track alignment                                 |           |
|                        | PredefinedType  | USERDEFINED                                             |           |
| IfcAlignmentHorizontal | Name            | AH1                                                     |           |
| IfcAlignmentCant       | Name            | AC1                                                     |           |
| IfcSite                | Name            | Site_1                                                  |           |
| IfcProject             | Name            | Project_1                                               |           |



### Railway alignment (without cant)

> **Acceptance criteria**: For the **Railway alignment (without cant)** capability, the validation procedure must verify that **all** the following validation criteria are satisfied.

| **RULE ID** | **CRITERIA**                                             | **VALUE [examples]**                           | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|----------------------------------------------------------|------------------------------------------------|----------------------------|------------------------|
| SITE_00     | All IfcAlignment shall always be contained in an IfcSite |                                                |                            | Spatial Containment    |
| ALIG_00     | Alignment layout structure is verified                   | See steps                                      |                            | Alignment Layout       |
| ALIG_01     | Number of alignments contained in file                   | [1]                                            |                            |                        |
| ALIG_02     | Parameters of alignment segments are verified            | As per Excel dataset of each case              |                            |                        |
| ALIG_03     | Alignment geometric compliance is verified               | As per Alignment geometric compliance document |                            |                        |
| ALIG_04     | Value of the RailHeadDistance along the entire alignment | [1500 mm]                                      | IfcAlignmentCant           |                        |

<details><summary>ALIG_00 steps</summary>

| **STEP ID** | **STEP**                                                                                                                                           |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| ALIG_00.1   | Each IfcAlignment must nest exactly 1 IfcAlignmentHorizontal                                                                                       |
| ALIG_00.2   | Each IfcAlignment must nest at most 1 IfcAlignmentVertical                                                                                         |
| ALIG_00.5   | Each IfcAlignment must nest exactly 1 IfcAlignmentCant                                                                                         |
| ALIG_00.6   | Each IfcAlignmentHorizontal must be nested only by 1 IfcAlignment                                                                                  |
| ALIG_00.8   | Each IfcAlignmentCant must be nested only by 1 IfcAlignment                                                                                    |
| ALIG_00.10  | Each IfcAlignmentHorizontal nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentHorizontalSegment         |
| ALIG_00.12  | Each IfcAlignmentCant nests a list of IfcCantSegment, each of which has DesignParameters typed as IfcAlignmentCantSegment             |

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

#### Spatial (De)Composition Table

| **Parent Element** | **Parent Element Type** | **Parent Element Name** | **MinSize** | **MaxSize** | **Child Element** | **Child Element Type** | **Child Element Name** |
|--------------------|-------------------------|-------------------------|-------------|-------------|-------------------|------------------------|------------------------|
| IfcProject         |                         | Project_1      | 1           | 1           | IfcSite           |                        | Site_1                   |

**Bullet point example**:
- IfcProject *(Name: Project_1)*
  - IfcSite *(Name: Site_1)*



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

| **Spatial Element** | **Spatial Element Type** | **MinSize** | **MaxSize** | **Element**     | **Element Type**        |
|---------------------|--------------------------|-------------|-------------|-----------------|-------------------------|
| IfcSite             |                          | 1           | 1           | IfcAlignment    | Railway track alignment |

**Bullet point example**:

- IfcProject *(Name: Project_1)*
  - IfcSite *(Name: Site_1)*
    - `IfcAlignment` *(Name: Alignment_1)*























