# Test Instruction Template

| Documentation Code   | Title                                          | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|------------------------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_TSLC   | Track Structures Level Crossing               | E2a-TRST      | TSLC      |                 | FTIA      | 1.0     | 24.02.2022 |


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
- Signal assembly
  - *IfcMember*
  - *IfcSignal*
  - *IfcSign*
- Boom barrier
  - IfcDoor

- Other physical elements
  - *IfcDoor*
  - *IfcFooting*
  - *IfcRailing*
  - *IfcSensor* (axle counters)
  - *IfcDiscreteAccessory* (snow plough protection)
  - IfcJunctionBox

</details>

<details><summary>Concept Templates</summary>

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- *Optional Grouping*
  - *Project Units*
  - *Project Representation Context*
  - *Project Global Positioning*
  - *Spatial Composition*
  - *Spatial Decomposition*
  - *Spatial Interference*
  - *Spatial Container*
  - *Alignment Layout*
  - *Alignment Geometry Gradient*
  - *Product Linear Placement*
  - *Product Local Placement*
  - *Product Relative Positioning*
  - *Material Constituent Set*
  - *Object Typing*

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

| **ID**  | **CRITERIA**                                  | **VALUE**                           | **COMMENT** |
| ------- | --------------------------------------------- | ----------------------------------- | ----------- |
| SE_00   | Spatial structure is verified                 | See below for further specification |             |
| ALIG_00 | Alignment layout structure is verified        | See below for further specification |             |
| SITE_00 | Alignment shall always be contained in a Site | na                                  |             |
| SC_00   | Spatial Containment is verified               | See below for further specification |             |
| EC_00   | Element Composition is verified               | See below for further specification |             |
| EP_00   | Element Placement is verified                 | See below for further specification |             |
| ERP_00  | Element relative positioning verified         | See below for further specification |             |

SE_00: Spatial structure is verified

>1. The dataset shall contain one *IfcSite* instance
>2. The dataset shall contain one `IfcRailway` instance that is aggregated into the *IfcSite* according to CT Spatial Composition. 
>3. The dataset shall contain one `IfcRoad` instance that is aggregated into the *IfcSite* according to CT Spatial Composition. 
>4. The *IfcRailway* instance shall be decomposed into three *IfcFacilityPart* instances according to CT Spatial Decomposition
>   1. One `IfcFacilityPart` with `PredefinedType=IfcRailwayPartTypeEnum.TRACKSTRUCTURE`
>   2. One `IfcFacilityPart` with `PredefinedType=IfcFacilityPartCommonTypeEnum.LEVELCROSSING`
>   3. One `IfcFacilityPart` with `PredefinedType=IfcRailwayPartTypeEnum.TRACKSTRUCTURE`
>5. The `IfcRoad` instance shall be decomposed into three `IfcFacilityPart` instances according to CT Spatial Decomposition
>   1. One `IfcFacilityPart` with `PredefinedType=IfcRoadPartTypeEnum.ROADSEGMENT`
>   2. One `IfcFacilityPart` with `PredefinedType=IfcFacilityPartCommonTypeEnum.LEVELCROSSING`
>   3. One `IfcFacilityPart` with `PredefinedType=IfcRoadPartTypeEnum.ROADSEGMENT`
>6. The two facility parts representing the level crossing in the road and railway facilities shall be linked as interfering according to CT Spatial Interference

ALIG_00: Alignment layout structure is verified

> 1. Each `IfcAlignment` must nest exactly 1 `IfcAlignmentHorizontal`
> 2. Each `IfcAlignment` must nest at most 1 `IfcAlignmentVertical`
> 3. Each `IfcAlignmentHorizontal` must be nested only by 1 `IfcAlignment`
> 4. Each `IfcAlignmentVertical` must be nested only by 1 `IfcAlignment`
> 5. Each `IfcAlignment` must nest only `IfcAlignmentHorizontal`, or `IfcAlignmentVertical`
> 6. Each `IfcAlignmentHorizontal` must nest only `IfcAlignmentHorizontalSegment`
> 7. Each `IfcAlignmentVertical` must nest only `IfcAlignmentVerticalSegment`
> 8. Each `IfcAlignmentHorizontalSegment` must be nested only by 1 `IfcAlignmentHorizontal`
> 9. Each `IfcAlignmentVerticalSegment` must be nested only by 1 `IfcAlignmentVertical`

SC_00: Spatial Containment is verified

> 1. The top level signal assembly (`IfcElementAssembly/SIGNALASSEMBLY`) is contained in the `IfcRoad` facility.
> 2. The axle counters (`IfcSensor/WHEELSENSOR`) is contained in the `LEVELCROSSING` facility part belonging to the `IfcRailway` facility.
> 3. The junction boxes (`IfcJunctionBox/DATA`) is contained in the `LEVELCROSSING` facility part belonging to the `IfcRailway` facility.
> 4. The snow plough protection equipment (`IfcDiscreteAccessory/RAIL_MECHANICAL_EQUIPMENT`) is contained in the `LEVELCROSSING` facility part belonging to the `IfcRailway` facility.

EC_00: Element Composition is verified

> 1. A second level signal assembly (`IfcElementAssembly/SIGNALASSEMBLY`) is a component of the top level signal assembly.
> 2. The boom barrier (`IfcDoor/BOOM_BARRIER`) is a component of the top level signal assembly.
> 3. The footing (`IfcFooting/PAD_FOOTING`) is a component of the top level signal assembly.
> 4. The railing (`IfcRailing/GUARDRAIL`) is a component of the top level signal assembly.
> 5. The post  (`IfcMember/POST`)  is a component of the second level signal assembly.
> 6. The visual signal (`IfcSignal/VISUAL`)  is a component of the second level signal assembly.
> 7. The audio signal (`IfcSignal/AUDIO`)  is a component of the second level signal assembly.
> 8. The sign (`IfcSign/PICTORAL`)  is a component of the second level signal assembly.

EP_00: Element Placement is verified

> 1. The track alignment (`IfcAlignment`) shall have an `IfcLocalPlacement` relative to the placement of the `IfcSite`.
> 2. The top level signal assembly shall have an associated `IfcLinearPlacement` relative to the track alignment curve according to CT Product Linear Placement at the specified location.
> 3. The components of the top level signal assembly shall have an associated `IfcLocalPlacement` relative to the `IfcLinearPlacement` of the top level signal assembly at the specified locations according to CT Product Local Placement.
> 4. The axle counters (IfcSensor/WHEELSENSOR) shall have an associated `IfcLinearPlacement` relative to the track alignment curve according to CT Product Linear Placement at the specified location.
> 5. The snow plough protection (IfcDiscreteAccessory/RAIL_MECHANICAL_EQUIPMENT) shall have an associated `IfcLinearPlacement` relative to the track alignment curve according to CT Product Linear Placement at the specified location.
> 6. The junction boxes (IfcJunctionBox/DATA) shall have an associated `IfcLinearPlacement` relative to the track alignment curve according to CT Product Linear Placement at the specified location.

ERP_00: Element Relative Positioning

> 1. All elements in the dataset having an associated IfcLinearPlacement shall have a relative positioning relationship with the corresponding track alignment according to CT Product Relative Positioning.

</details>

<details><summary>Model Geometry</summary>
The Test case requires the following additional checks related to Model Geometry:



| **ID**  | **CRITERIA**                                   | **VALUE**                           | **COMMENT** |
| ------- | ---------------------------------------------- | ----------------------------------- | ----------- |
| ALIG_01 | Alignment geometric representation is verified | See below for further specification |             |


> 1. Each `IfcAlignment` shall have one Representation with RepresentationIdentifier="Axis" and RepresentationType="Curve3D" referencing 1 `IfcGradientCurve`
> 1. Each `IfcAlignmentHorizontal` shall have one Representation with RepresentationIdentifier="Axis" and RepresentationType="Curve2D" referencing 1 `IfcCompositeCurve`
> 1. Each `IfcAlignmentVertical` shall have one Representation with RepresentationIdentifier="Axis" and RepresentationType="Curve3D" referencing 1 `IfcGradientCurve` (the same instance as is referred from the owning `IfcAlignment` instance). 
> 1. Geometric representations shall correspond to the semantic definitions.

</details>

## Expected Results

For certification of capabilities the only source will be:

:construction: under construction :construction:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`-`ExchangeCode`-`TestCode`-`SoftwareVendor`.`ifc` (Example: `IFC4.3_AbRV-E2b-ASTPC-AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet useful to illustrate test results are:
- Screen-shot of ...
- CSV export of ...

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


| Relating Spatial Element | Relating Spatial Element Type | Minimum | Maximum | Related Spatial element | Related Spatial Element Type                | Usage type   |
| ------------------------ | ----------------------------- | ------- | ------- | ----------------------- | ------------------------------------------- | ------------ |
| IfcSite                  |                               | 1       | 1       | IfcRoad                 |                                             |              |
| IfcSite                  |                               | 1       | 1       | IfcRailway              |                                             |              |
| IfcRoad                  |                               | 2       | 2       | IfcFacilityPart         | IfcRoadPartTypeEnum.ROADSEGMENT             | LONGITUDINAL |
| IfcRoad                  |                               | 1       | 1       | IfcFacilityPart         | IfcFacilityPartCommonTypeEnum.LEVELCROSSING | LONGITUDINAL |
| IfcRailway               |                               | 2       | 2       | IfcFacilityPart         | IfcRailwayPartTypeEnum.TRACKSTRUCTURE       | LONGITUDINAL |
| IfcRailway               |                               | 2       | 2       | IfcFacilityPart         | IfcFacilityPartCommonTypeEnum.LEVELCROSSING | LONGITUDINAL |

</details>

### Spatial Interference

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Spatial interference** capability, the validation procedure must verify that a Spatial Element of the requested type interferes with (via `IfcRelInterferesElements`) a Spatial Element of the requested type.


| Relating Spatial Element | Relating Spatial Element Type               | Related Spatial element | Related Spatial Element Type                |
| ------------------------ | ------------------------------------------- | ----------------------- | ------------------------------------------- |
| IfcFacilityPart          | IfcFacilityPartCommonTypeEnum.LEVELCROSSING | IfcFacilityPart         | IfcFacilityPartCommonTypeEnum.LEVELCROSSING |

</details>

### Track alignment

<details><summary>Click to expand</summary>


| **ID**  | **CRITERIA**                                                 | **VALUE**                                      | **COMMENT** |
| ------- | ------------------------------------------------------------ | ---------------------------------------------- | ----------- |
| ALIG_01 | Alignments contained in file                                 | 1                                              |             |
| ALIG_02 | Components for Alignment                                     | 1 horizontal, 1 vertical                       |             |
| ALIG_03 | The horizontal (H) layout matches exactly the layout specified in the [Dataset description](./Dataset/README.md) | See [Dataset description](./Dataset/README.md) |             |
| ALIG_04 | The vertical (V) layout matches exactly the layout specified in the [Dataset description](./Dataset/README.md) | See [Dataset description](./Dataset/README.md) |             |
| ALIG_05 | The IfcAlignment shall have one Representation of type IfcProductShapeRepresentation having one Representation of type IfcShapeRepresentation having RepresentationIdentifier="Axis" and RepresentationType="Curve3D" and having one Item of type IfcGradientCurve. |                                                |             |
| ALIG_06 | The IfcAlignmentHorizontal shall have one Representation of type IfcProductShapeRepresentation having one Representation of type IfcShapeRepresentation having RepresentationIdentifier="Axis" and RepresentationType="Curve2D" and having one Item of type IfcCompositeCurve. |                                                |             |
| ALIG_07 | The IfcAlignmentVertical shall have one Representation of type IfcProductShapeRepresentation having one Representation of type IfcShapeRepresentation having RepresentationIdentifier="Axis" and RepresentationType="Curve3D" and having one Item of type IfcGradientCurve (same instance as referred to by IfcAlignment). |                                                |             |
| ALIG_06 | The IfcGradientCurve shall have the IfcCompositeCurve as BaseCurve |                                                |             |
| ALIG_07 | The IfcGradientCurve shall have Segments that exactly match the corresponding vertical segments in the IfcAlignmentVertical and in the same order |                                                |             |
| ALIG_08 | The IfcCompositeCurve shall have Segments that exactly match the corresponding horizontal segments in the IfcAlignmentHorizontal and in the same order |                                                |             |

</details>

### Spatial containment

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Spatial containment** capability, the validation procedure must verify that a Spatial Element of the requested type contains (via `IfcRelContainedInSpatialStructure`) exactly a given number of Elements of the requested type, no more and no less.


| Spatial Element | Spatial Element Type                 | Minimum | Maximum | Element              | Element Type              |
| --------------- | ------------------------------------ | ------- | ------- | -------------------- | ------------------------- |
| IfcSite         |                                      | 1       | 1       | IfcAlignment         |                           |
| IfcRoad         |                                      | 1       | 1       | IfcElementAssembly   | SIGNALASSEMBLY            |
| IfcFacilityPart | IfcRailwayPartTypeEnum.LEVELCROSSING | 2       | 2       | IfcSensor            | WHEELSENSOR               |
| IfcFacilityPart | IfcRailwayPartTypeEnum.LEVELCROSSING | 2       | 2       | IfcJunctionBox       | DATA                      |
| IfcFacilityPart | IfcRailwayPartTypeEnum.LEVELCROSSING | 2       | 2       | IfcDiscreteAccessory | RAIL_MECHANICAL_EQUIPMENT |

</details>

### Element decomposition

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Element decomposition** capability, the validation procedure must verify that an Element of the requested type is decomposed by (via `IfcRelAggregates`) exactly a given number of Elements of the requested type, no more and no less.


| Spatial Element              | Spatial Element Type | Minimum | Maximum | Element                      | Element Type   |
| ---------------------------- | -------------------- | ------- | ------- | ---------------------------- | -------------- |
| IfcElementAssembly (level 1) | SIGNALASSEMBLY       | 1       | 1       | IfcElementAssembly (level 2) | SIGNALASSEMBLY |
| IfcElementAssembly (level 1) | SIGNALASSEMBLY       | 1       | 1       | IfcDoor                      | BOOM_BARRIER   |
| IfcElementAssembly (level 1) | SIGNALASSEMBLY       | 1       | 1       | IfcFooting                   | PAD_FOOTING    |
| IfcElementAssembly (level 1) | SIGNALASSEMBLY       | 1       | 1       | IfcRailing                   | GUARDRAIL      |
| IfcElementAssembly (level 2) | SIGNALASSEMBLY       | 1       | 1       | IfcMember                    | POST           |
| IfcElementAssembly (level 2) | SIGNALASSEMBLY       | 1       | 1       | IfcSignal                    | VISUAL         |
| IfcElementAssembly (level 2) | SIGNALASSEMBLY       | 1       | 1       | IfcSignal                    | AUDIO          |
| IfcElementAssembly (level 2) | SIGNALASSEMBLY       | 1       | 1       | IfcSign                      | PICTORAL       |

</details>

### Element placement

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Element placement** capability, the validation procedure must verify that an Element of the requested type is placed according to the specified placement with the specified values.

| **ID** | **CRITERIA**                                                 | **VALUE**                                      | **COMMENT** |
| ------ | ------------------------------------------------------------ | ---------------------------------------------- | ----------- |
| EP_01  | Elements are placed at the specified location using the specified ObjectPlacement | See [Dataset description](./Dataset/README.md) |             |

</details>

### Element Relative Positioning

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Element Relative Positioning** capability, the validation procedure must verify that an Element of the requested type has a position relative to the specified positioning element via IfcRelPositions.

| **ID** | **CRITERIA**                                                 | **VALUE**                                      | **COMMENT** |
| ------ | ------------------------------------------------------------ | ---------------------------------------------- | ----------- |
| ERP_01 | Each element that is placed linearly using `IfcLinearPlacement` shall have an IfcRelPositions relationship with the corresponding `IfcAlignment` | See [Dataset description](./Dataset/README.md) |             |

</details>

### Project global positioning

<details><summary>Click to expand</summary>
> **Acceptance criteria**: For the **Project global positioning** capability, the validation procedure must verify that there is an IfcMapConversion with the given parameters associated with the IfcGeometricRepresentationContext (via `HasCoordinateOperation`). Furthermore, the IfcMapConversion shall have an association with an IfcProjectedCRS (via `HasCoordinateOperation`) with the given parameters.




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

