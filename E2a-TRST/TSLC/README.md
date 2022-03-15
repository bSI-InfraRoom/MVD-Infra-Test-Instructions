# Test Instruction Template

| Documentation Code   | Title                                          | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|------------------------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_TSLC   | Track Structures Level Crossing               | E2a-TRST      | TSLC      |                 | FTIA      | 1.0     | 07.03.2022 |


## Summary (Intent)

This test case is defined for IFC4.3 AbRV_E2a_TSLC Track Structures Level Crossing. The basis for the test instruction is taken from the [Level Crossing Storyline](https://github.com/IFCRail/IFC-Rail-Unit-Test/tree/master/8_Storylines%20Test%20(SL)/SL08_Level%20Crossing).  

The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

:zap: **This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test** :zap:

## Itemised Roots
*This section lists the primary entities and concept templates being validated by this test instruction, these are listed to understand the scope of the data entities being addressed. this is the documentation of the data placed within BIMQ*

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

:construction: under construction :construction:

<details><summary>IFC Entities</summary>

These entities represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- Model setup
  - *IfcProject*
  - *IfcSite*
  - *IfcRailway*
  - *IfcRoad*
  - *IfcFacilityPart/IfcRailwayPart/IfcRoadPart*
  - *IfcUnitAssignment*
  - *IfcGeometricRepresentationContext*
  - *IfcMapConversion*
  - *IfcProjectedCRS*
- Alignment (Track)
  - *IfcAlignment*
  - *IfcAlignmentHorizontal*
  - *IfcAlignmentVertical*
  - *IfcAlignmentSegment*
  - *IfcAlignmentHorizontalSegment*
  - *IfcAlignmentVerticalSegment*
  - *IfcCompositeCurve*
  - *IfcGradientCurve*
  - *IfcCurveSegment*
  - *IfcLine*
  - *IfcCircle*
  - *IfcClothoid*
- Boom barrier
  - Signal assembly
    - *IfcMember*
    - *IfcSignal*
    - *IfcSign*
  - *IfcDoor*
  - *IfcFooting*
  - *IfcRailing*
  
- Signaling equipment
  - *IfcSensor* (axle counters)
  - *IfcDiscreteAccessory* (snow plough protection)
  - *IfcJunctionBox*

</details>

<details><summary>Concept Templates</summary>

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- *Model setup*
  - *Project Units*
  - *Project Representation Context*
  - *Project Global Positioning*
- *Spatial structure, spatial interference and spatial containment*
  - *Spatial Composition*
  - *Spatial Decomposition*
  - *Spatial Interference*
  - *Spatial Container*
- *Alignment*
  - *Alignment Decomposition*
  - *Alignment Geometry Gradient*
- *Element composition*
  - *Element Composition*
  - *Element Decomposition*

- *Product placement and relative positioning*
  - *Product Linear Placement*
  - *Product Local Placement*
  - *Product Relative Positioning*
- *Other (missing in this spec at the moment)*
  - *(Material Constituent Set)*
  - *(Object Typing)*

</details>

## Test Case Imports
Test instructions are defined with a modular approach to reduce repetition of validation criteria and test content, and improve vendors ability to solve issues and bugs. therefore this test instruction *imports/reuses* the following Test instructions and entities with the relevant associated validation criteria.

:construction: under construction :construction:

<details><summary>Imports & Reuses</summary>

| TI Code                                  | Test Instruction Title    | Comments                     |
|------------------------------------------|---------------------------|------------------------------|
| [IFC4.3AbRV_E0_MSTP](../../E0-SCFD/MSTP) | Model Setup & Positioning | PROJ-01 imported along with RCTX-01 and associated configuration and history data |

</details>

## Usages, Constraints & Logic
The following itemised restrictions and constraints shall be placed on IFC Entities & Concept Templates:

:construction: under construction :construction:

<details><summary>Semantic Usages, Constraints & Logic</summary>
The following itemised Usages, Constraints & Logic are normative entries within the AbRV MVD and MUST be satisfied to meet the defined validation criteria.
| ID      | CRITERIA                                                     | Concept template                                             | COMMENT                                                      |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| TSLC_01 | All Alignments shall be contained in a Site<br />All Physical Elements shall be directly or indirectly contained in a spatial structure element | Spatial Containment                                          | See [Validation Criteria](#Validation criteria)              |
| TSLC_02 | Alignment layout structure is verified                       | Alignment Decomposition                                      | See below and [Validation Criteria](#Validation criteria) for further specification |
| TSLC_03 | Spatial structure is verified                                | Spatial Composition<br />Spatial Decomposition<br />Spatial Interference | See [Validation Criteria](#Validation criteria)              |
| TSLC_04 | Elements are aggregated as required                          | Element Composition                                          | See [Validation Criteria](#Validation criteria)              |
| TSLC_05 | Elements are placed as required                              | Product Placement                                            | See [Validation Criteria](#Validation criteria)              |
| TSLC_06 | Elements placed relative to the alignments use relative positioning as required | Product Relative Positioning                                 | See below and [Validation Criteria](#Validation criteria) for further specification |
| TSLC_07 | Spatial interference is defined where spatial structure elements interfere | Spatial Interference (is this CT missing?)                   | See below and [Validation Criteria](#Validation criteria) for further specification |

TSLC_02: Alignment layout structure is verified

> 1. Each `IfcAlignment` must nest exactly 1 `IfcAlignmentHorizontal`
> 2. Each `IfcAlignment` must nest at most 1 `IfcAlignmentVertical`
> 3. Each `IfcAlignmentHorizontal` must be nested only by 1 `IfcAlignment`
> 4. Each `IfcAlignmentVertical` must be nested only by 1 `IfcAlignment`
> 5. Each `IfcAlignment` must nest only `IfcAlignmentHorizontal`, or `IfcAlignmentVertical`
> 6. Each `IfcAlignmentHorizontal` must nest only `IfcAlignmentHorizontalSegment`
> 7. Each `IfcAlignmentVertical` must nest only `IfcAlignmentVerticalSegment`

TSLC_06: Element Relative Positioning

> 1. All elements in the dataset having an associated IfcLinearPlacement and that are not nested into the IfcAlignment shall have a relative positioning relationship with the corresponding IfcAlignment according to CT Product Relative Positioning.

TSLC_07: Spatial Interference

> 1. Where two spatial structure elements interfere, there shall be one `IfcRelInterferesElements` instance specifying the interference relationship.

</details>

<details><summary>Model Geometry</summary>
The Test case requires the following additional checks related to Model Geometry:
| ID      | CRITERIA                                       | Concept template            | COMMENT                                         |
| ------- | ---------------------------------------------- | --------------------------- | ----------------------------------------------- |
| TSLC_08 | Alignment geometric representation is verified | Alignment Geometry Gradient | See [Validation Criteria](#Validation criteria) |

</details>

## Expected Results

For certification of capabilities the only source will be:

:construction: under construction :construction:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`-`ExchangeCode`-`TestCode`-`SoftwareVendor`.`ifc` (Example: `IFC4.3_AbRV-E2b-ASTPC-AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet useful to illustrate test results are:
- Screen-shot of the model with all elements clearly visible
- CSV export of the linear, local and global (map) coordinates for each element

---

## Validation criteria
:zap: For this test case to be considered passed **all capabilities** listed in this section shall be verified, with no exception. :zap:

:construction: under construction :construction:

### General & Imports

<details><summary>Click to expand</summary>

- All the concept templates must be correctly implemented as presented in the validation criteria
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file.


#### Imports
| **TI Code**        | **Criteria Codes** | *COMMENT**                                         |
|--------------------|--------------------|----------------------------------------------------|
| IFC4.3AbRV_E0_MSTP | ALL CRITERIA       | As outlined in the dataset [Imported Entities Table](Dataset/README.md#Imported-Entities-Table) |


#### General
| **ID**  | **CRITERIA**                                        | **VALUE**                                     | **COMMENT** |
|---------|-----------------------------------------------------|-----------------------------------------------|-------------|
| GENE_01 | All requested entities are present in the IFC model | per [Entities Table](Dataset/README.md#Entities-Table) |    |

</details>

### Spatial decomposition

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Spatial decomposition** capability, the validation procedure must verify that a Spatial Element of the requested type is decomposed by (via `IfcRelAggregates`) exactly a given number of Spatial Elements of the requested type, no more and no less.
| ID      | CRITERIA                                                     | VALUE                                                  | COMMENT |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------ | ------- |
| SPAT_00 | The file contains exactly 1 IfcSite element                  | per [Entities Table](Dataset/README.md#Entities-Table) |         |
| SPAT_01 | The IfcSite is composed of exactly 1 IfcRoad element         | per [Entities Table](Dataset/README.md#Entities-Table) |         |
| SPAT_02 | The IfcSite is composed of exactly 1 IfcRailway element      | per [Entities Table](Dataset/README.md#Entities-Table) |         |
| SPAT_03 | The IfcRoad is composed of Exactly 2 elements of type IfcFacilityPart/IfcRoadPartTypeEnum(ROADSEGMENT) | per [Entities Table](Dataset/README.md#Entities-Table) |         |
| SPAT_04 | The IfcRoad is composed of Exactly 1 element of type IfcFacilityPart/IfcFacilityPartCommonTypeEnum(LEVELCROSSING) | per [Entities Table](Dataset/README.md#Entities-Table) |         |
| SPAT_05 | The IfcRailway is composed of Exactly 2 elements of type IfcFacilityPart/IfcRailwayPartTypeEnum(TRACKSTRUCTURE) | per [Entities Table](Dataset/README.md#Entities-Table) |         |
| SPAT_06 | The IfcRailway is composed of Exactly 1 element of type IfcFacilityPart/IfcFacilityPartCommonTypeEnum(LEVELCROSSING) | per [Entities Table](Dataset/README.md#Entities-Table) |         |

</details>

### Spatial Interference

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Spatial interference** capability, the validation procedure must verify that a Spatial Element of the requested type interferes with (via `IfcRelInterferesElements`) a Spatial Element of the requested type.
| ID      | CRITERIA                                                     | VALUE                                                  | COMMENT |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------ | ------- |
| SPIF_00 | There shall be one IfcRelInterferesElements relationship relating the two IfcFacilityPart instances typed as LEVELCROSSING. The IfcRelInterferesElements.InterferenceType shall have the value 'Crosses'. | per [Entities Table](Dataset/README.md#Entities-Table) |         |

</details>

### Alignment layout structure

<details><summary>Click to expand</summary>
| **ID**  | **CRITERIA**                                                 | **VALUE**                                              | **COMMENT** |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------ | ----------- |
| ALIG_01 | The model contains exactly 2 IfcAlignment instances          | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ALIG_02 | Each IfcAlignment nests exactly 1 IfcAlignmentHorizontal and exactly 1 IfcAlignmentVertical | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ALIG_03 | Each IfcAlignmentHorizontal nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentHorizontalSegment | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ALIG_04 | Each IfcAlignmentVertical nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentVerticalSegment | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ALIG_05 | Parameters of alignment segments shall be defined according to the dataset description | per [Entities Table](Dataset/README.md#Entities-Table) |             |

</details>

### Alignment Geometry Gradient

<details><summary>Click to expand</summary>

| **ID**  | **CRITERIA**                                                 | **VALUE**                                              | **COMMENT** |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------ | ----------- |
| ALGG_00 | Each IfcAlignment shall have one Representation of type IfcProductShapeRepresentation having one Representation of type IfcShapeRepresentation having RepresentationIdentifier="Axis" and RepresentationType="Curve3D" and having one Item of type IfcGradientCurve. | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ALGG_01 | Each IfcAlignmentHorizontal shall have one Representation of type IfcProductShapeRepresentation having one Representation of type IfcShapeRepresentation having RepresentationIdentifier="Axis" and RepresentationType="Curve2D" and having one Item of type IfcCompositeCurve. | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ALGG_02 | Each IfcAlignmentVertical shall have one Representation of type IfcProductShapeRepresentation having one Representation of type IfcShapeRepresentation having RepresentationIdentifier="Axis" and RepresentationType="Curve3D" and having one Item of type IfcGradientCurve (same instance as referred to by IfcAlignment). | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ALGG_03 | Each IfcGradientCurve shall have the corresponding IfcCompositeCurve as BaseCurve | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ALGG_04 | Each IfcGradientCurve shall have Segments that exactly match the corresponding vertical segments in the IfcAlignmentVertical and in the same order | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ALGG_05 | Each IfcCompositeCurve shall have Segments that exactly match the corresponding horizontal segments in the IfcAlignmentHorizontal and in the same order | per [Entities Table](Dataset/README.md#Entities-Table) |             |

### Spatial containment

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Spatial containment** capability, the validation procedure must verify that a Spatial Element of the requested type contains (via `IfcRelContainedInSpatialStructure`) exactly a given number of Elements of the requested type, no more and no less.
| **ID**  | **CRITERIA**                                                 | **VALUE**                                              | **COMMENT** |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------ | ----------- |
| SPAC_00 | The IfcSite contains exactly 2 IfcAlignment instances        | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| SPAC_01 | The IfcRoad contains exactly one IfcElementAssembly/SIGNALASSEMBLY | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| SPAC_02 | The IfcFacilityPart/IfcFacilityPartCommonTypeEnum(LEVELCROSSING) that decomposes IfcRail contains exactly 2 IfcSensor/WHEELSENSOR | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| SPAC_03 | The IfcFacilityPart/IfcFacilityPartCommonTypeEnum(LEVELCROSSING) that decomposes IfcRail contains exactly 2 IfcJunctionBox/DATA | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| SPAC_04 | The IfcFacilityPart/IfcFacilityPartCommonTypeEnum(LEVELCROSSING) that decomposes IfcRail contains exactly 2 IfcDiscreteAccessory/RAIL_MECHANICAL_EQUIPMENT | per [Entities Table](Dataset/README.md#Entities-Table) |             |

</details>

### Element decomposition

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Element decomposition** capability, the validation procedure must verify that an Element of the requested type is decomposed by (via `IfcRelAggregates`) exactly a given number of Elements of the requested type, no more and no less.
| **ID**  | **CRITERIA**                                                 | **VALUE**                                              | **COMMENT** |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------ | ----------- |
| ELDC_00 | The top level IfcElementAssembly aggregates exactly 1 lower level IfcElementAssembly/SIGNALASSEMBLY | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ELDS_01 | The top level IfcElementAssembly aggregates exactly 1 IfcDoor/BOOM_BARRIER | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ELDS_02 | The top level IfcElementAssembly aggregates exactly 1 IfcFooting/PAD_FOOTING | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ELDS_03 | The top level IfcElementAssembly aggregates exactly 1 IfcRailing/GUARDRAIL | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ELDS_04 | The lower level level IfcElementAssembly aggregates exactly 1 IfcMember/POST | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ELDS_05 | The lower level level IfcElementAssembly aggregates exactly 1 IfcSignal/VISUAL | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ELDS_06 | The lower level level IfcElementAssembly aggregates exactly 1 IfcSignal/AUDIO | per [Entities Table](Dataset/README.md#Entities-Table) |             |
| ELDS_07 | The lower level level IfcElementAssembly aggregates exactly 1 IfcSign/PICTORAL | per [Entities Table](Dataset/README.md#Entities-Table) |             |

</details>

### Element placement

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Element placement** capability, the validation procedure must verify that an Element of the requested type is placed according to the specified placement with the specified values.

| **ID**  | **CRITERIA**                                                 | **VALUE**                                              | **COMMENT** |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------ | ----------- |
| ELPL_00 | Elements are placed at the specified location using the specified ObjectPlacement | per [Entities Table](Dataset/README.md#Entities-Table) |             |

</details>

### Element Relative Positioning

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Element Relative Positioning** capability, the validation procedure must verify that an Element of the requested type has a position relative to the specified positioning element via IfcRelPositions.

| **ID**  | **CRITERIA**                                                 | **VALUE**                                              | **COMMENT** |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------ | ----------- |
| ERPO_01 | Each element that is placed linearly using IfcLinearPlacement shall have an IfcRelPositions relationship with the corresponding IfcAlignment | per [Entities Table](Dataset/README.md#Entities-Table) |             |

</details>

### Project global positioning

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Project global positioning** capability, the validation procedure must verify that there is an IfcMapConversion with the given parameters associated with the IfcGeometricRepresentationContext (via `HasCoordinateOperation`). Furthermore, the IfcMapConversion shall have an association with an IfcProjectedCRS (via `HasCoordinateOperation`) with the given parameters.
The parameters below shall be used for Project Global Positioning.

| Element          | Attribute        | Value     | Comment |
| ---------------- | ---------------- | --------- | ------- |
| IfcMapConversion | Eastings         | 24525000  |         |
| IfcMapConversion | Northings        | 6876000   |         |
| IfcMapConversion | OrthogonalHeight | 0         |         |
| IfcMapConversion | XAxisAbscissa    | 1         |         |
| IfcMapConversion | XAxisOrdinate    | 0         |         |
| IfcMapConversion | Scale            | 1         |         |
| IfcProjectedCRS  | Name             | EPSG:3878 |         |
| IfcProjectedCRS  | GeodeticDatum    | EPSG:6258 |         |
| IfcProjectedCRS  | VerticalDatum    | EPSG:3900 |         |

</details>

