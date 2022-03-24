# Validation Criteria Master Document
This document contains a comprehensive list of validation criteria referenced by all Test Instructions.

Its objective is to guarantee consistency of criteria, allowing the authors to refer to the same table format.

> **ATTENTION**: for some rules a test-specific VALUE might be needed. In this case the tables below just capture an example between []

Utilities:  [Table converter](https://tableconvert.com/) (e.g., Excel to MD, MD to MD)




## Table Templates

<details><summary>Alignment Table template</summary>

**HORIZONTAL**
| Entity                        | PredefinedType | Name | Start Point X | Start Point Y | Start Direction | Start Radius Of Curvature | End Radius Of Curvature | Segment Length | Gravity Center Line Height |
|-------------------------------|----------------|------|---------------|---------------|-----------------|---------------------------|-------------------------|----------------|----------------------------|
| IfcAlignmentHorizontalSegment | LINE           | H1   | 452413.9199   | 4539456.401   | 0.214271681     | 0                         | 0                       | 234.719412     |                            |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H2   | 452634.415    | 4539536.869   | 0.214271681     | 0                         | -1000                   | 40             |                            |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H3   | 452671.898    | 4539550.832   | 0.236493911     | -1000                     | -1000                   | 193.464471     |                            |

**VERTICAL**
| Entity                      | PredefinedType   | Name | Start Dist Along | Horizontal Length | Start Height | Start Gradient | End Gradient | RadiusOfCurvature |
|-----------------------------|------------------|------|------------------|-------------------|--------------|----------------|--------------|-------------------|
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V1   | 0                | 0                 | 5            | 0              | 0            |                   |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V2   | 325.0006         | 49.9975           | 5            | 0              | -0.01        | 5000              |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V3   | 374.9981         | 250.0038          | 4.75         | -0.01          | -0.01        |                   |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V4   | 625.0019         | 49.9975           | 2.25         | -0.01          | 0            | -5000             |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V5   | 674.9994         | 201.3688          | 2            | 0              | 0            |

**CANT**
| Entity                  | PredefinedType   | Name | Start Dist Along | Horizontal Length | Start Cant left | End Cant left | Start Cant right | End Cant right |
|-------------------------|------------------|------|------------------|-------------------|-----------------|---------------|------------------|----------------|
| IfcAlignmentCantSegment | CONSTANTCANT     | C1   | 0                | 234.7194          | 0               | 0             | 0                | 0              |
| IfcAlignmentCantSegment | LINEARTRANSITION | C2   | 234.7194         | 40                | 0               | 0             | 0                | 0.06           |
| IfcAlignmentCantSegment | CONSTANTCANT     | C3   | 274.7194         | 193.4645          | 0               | 0             | 0.06             | 0.06           |
| IfcAlignmentCantSegment | LINEARTRANSITION | C4   | 468.1839         | 40                | 0               | 0             | 0.06             | 0              |
| IfcAlignmentCantSegment | CONSTANTCANT     | C5   | 508.1839         | 38.9815           | 0               | 0             | 0                | 0              |
| IfcAlignmentCantSegment | LINEARTRANSITION | C6   | 547.1654         | 40                | 0               | 0.06          | 0                | 0              |
| IfcAlignmentCantSegment | CONSTANTCANT     | C7   | 587.1654         | 109.4317          | 0.06            | 0.06          | 0                | 0              |
| IfcAlignmentCantSegment | LINEARTRANSITION | C8   | 696.5971         | 40                | 0.06            | 0             | 0                | 0              |
| IfcAlignmentCantSegment | CONSTANTCANT     | C9   | 736.5971         | 139.7711          | 0               | 0             | 0                | 0              |
| IfcAlignmentCantSegment | CONSTANTCANT     | C10  | 876.3682         | 876.3682          | 0               | 0             | 0                | 0              |

</details>

<details><summary>Entities Table template</summary>

> **HOW TO USE IT**: list first the entities' attributes and their values. Then, if needed, add additional information (e.g., placement, material, etc.). Be careful not to be redundant with other rules (e.g. placement-specific rules, material-specific rules, etc.)

| **Element**            | **Attribute**   | **Value**                 | **Notes**                       |
|------------------------|-----------------|---------------------------|---------------------------------|
| IfcAlignment           | Name            | Alignment 1_Primary route |                                 |
|                        | Description     | $                         |                                 |
|                        | ObjectType      | Railway track alignment   |                                 |
|                        | PredefinedType  | USERDEFINED               |                                 |
| IfcAlignmentHorizontal | Name            | AH1                       |                                 |
|                        | Description     | $                         |                                 |
| IfcAlignmentVertical   | Name            | AV1                       |                                 |
|                        | Description     | $                         |                                 |

</details>

<details><summary>Groups Table template</summary>

| **Group** | **Group Type**                | **MinSize** | **MaxSize** | **Object**         | **Object Type**      | **Notes** |
|-----------|-------------------------------|-------------|-------------|--------------------|----------------------|-----------|
| IfcGroup  | Binari di corsa (Contenitore) | 2           | 2           | IfcFacilityPart    | TRACKSTRUCTURE       | From AL22 |
| IfcGroup  | Deviatoi                      | 1           | 1           | IfcElementAssembly | TURNOUTPANEL         | From TP01 |
| IfcGroup  | Massicciata                   | 1           |             | IfcCourse          | BALLASTBED           | From SP01 |
| IfcGroup  | Traverse                      | 1           |             | IfcGroup           | Segmento di traverse |           |
| IfcGroup  | Segmento di traverse          | 1           |             | IfcTrackElement    | SLEEPER              | From SP01 |
| IfcGroup  | Rotaie                        | 1           | 1           | IfcGroup           | Segmento di rotaia   |           |
| IfcGroup  | Segmento di rotaia            | 2           | 2           | IfcRail            | RAIL                 | From SP01 |

NOTE:
- when **MinSize** and **MaxSize** have the same value, it means exactly. Example: MinSize=MaxSize=1, means that the group must groups exactly 1 object of that type.
- when **MaxSize is empty**, it means **unlimited**. Example: MinSize=1; MaxSize=empty, means that the group must group 1 or more object of the requested type.
- the **Notes** column indicates (when the object to be grouped is coming from a pre-requisite test) which is the mentioned test.

</details>

<details><summary>Properties Table template</summary>

> THE COLUMN "Property Value" IS OPTIONAL. FILL IT IN IF YOUR TEST REQUIRES A SPECIFIC VALUE FOR A GIVEN PROPERTY 

| **Entity**      | **Entity Type**         | **PropertySet Name**         | **Property Name**            | **Property Value Type**     | **List Of Values**                                                                                 | **Value type**             | **Property Value** |
|-----------------|-------------------------|------------------------------|------------------------------|-----------------------------|----------------------------------------------------------------------------------------------------|----------------------------|--------------------|
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | Binario                      | IfcLabel                    | Pari, Dispari, Unico                                                                               | IfcPropertyEnumeratedValue | Pari               |
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | Codice binario SAS           | IfcLabel                    |                                                                                                    | IfcPropertySingleValue     | 2 Ovest            |
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | n. deviatoi elettrici        | IfcInteger                  |                                                                                                    | IfcPropertySingleValue     | 1                  |
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | Profilo manutentivo L94      | IfcLabel                    | <=40 t/g, >100 t/g, 40< t/g <=100                                                                  | IfcPropertyEnumeratedValue | >100 t/g           |
| IfcFacilityPart | TRACKSTRUCTURE          | RFI_S16000                   | Binario elettrificato        | IfcLogical                  |                                                                                                    | IfcPropertySingleValue     | TRUE               |
| IfcTrackElement | SLEEPER                 | Pset_TrackElementTypeSleeper | SleeperType                  | IfcLabel                    | COMPOSITESLEEPER, CONCRETESLEEPER, MONOBLOCKCONCRETESLEEPER, NOTKNOWN, OTHER, UNSET, WOODENSLEEPER | IfcPropertyEnumeratedValue | CONCRETESLEEPER    |
| IfcTrackElement | SLEEPER                 | Pset_TrackElementTypeSleeper | FasteningType                | IfcLabel                    |                                                                                                    | IfcPropertySingleValue     | VS34               |
| IfcCourse       | Segmento di massicciata | PSet_CourseCommon            | NominalLength                | IfcNonNegativeLengthMeasure |                                                                                                    | IfcPropertySingleValue     | 400.00             |
| IfcCourse       | Segmento di massicciata | PSet_CourseCommon            | NominalThickness             | IfcNonNegativeLengthMeasure |                                                                                                    | IfcPropertySingleValue     | 0.35               |
| IfcCourse       | Segmento di massicciata | PSet_CourseCommon            | NominalWidth                 | IfcNonNegativeLengthMeasure |                                                                                                    | IfcPropertySingleValue     | 3.40               |
| IfcCourseType   | Segmento di massicciata | RFI_S22600                   | Tipo massicciata             | IfcLabel                    | Misto, Calcareo, Tenace                                                                            | IfcPropertyEnumeratedValue | Misto              |
| IfcGroup        | Segmento di rotaia      | RFI_S22700                   | Galleria                     | IfcLogical                  |                                                                                                    | IfcPropertySingleValue     | FALSE              |
| IfcGroup        | Segmento di rotaia      | RFI_S22700                   | Tipo binario di appartenenza | IfcLabel                    | BINARIO CENTRALIZZATO, BINARIO DI CORSA, BINARIO DI FASCIO, BINARIO IMP. SMISTAMENTO AUTOMATICO    | IfcPropertyEnumeratedValue | BINARIO DI CORSA   |

</details>

<details><summary>Groups Spatial Connectivity Table template</summary>

| **Spatial Element** | **Spatial Element Type** | **MinSize** | **MaxSize** | **Group**            | **Group Type**                 |
|---------------------|--------------------------|-------------|-------------|----------------------|--------------------------------|
| IfcRailway          | Località                 | 1           | 1           | IfcGroup             | Binari di corsa (Contenitore)  |
| IfcFacilityPart     | TRACKSTRUCTURE           | 1           | 1           | IfcGroup             | Deviatoi                       |
| IfcFacilityPart     | TRACKSTRUCTURE           | 1           | 1           | IfcGroup             | Massicciata                    |
| IfcFacilityPart     | TRACKSTRUCTURE           | 1           | 1           | IfcGroup             | Rotaie                         |
| IfcFacilityPart     | TRACKSTRUCTURE           | 1           | 1           | IfcGroup             | Traverse                       |

Examples:
1. A spatial element `IfcRailway`, of type `Località`, must reference exactly 1 `IfcGroup` of type `Binari di corsa (Contenitore)`
2. A spatial element `IfcFacilityPart`, of type `TRACKSTRUCTURE`, must reference exactly 1 `IfcGroup` of type `Deviatoi`

</details>

<details><summary>Spatial (De)Composition Table template</summary>

> OPTION 1: Use this template if you need to check at predefined type or object type level

| **Parent Element** | **Parent Element Type** | **MinSize** | **MaxSize** | **Child Element** | **Child Element Type** |
|--------------------|-------------------------|-------------|-------------|-------------------|------------------------|
| IfcRailway         | Località                | 2           | 2           | IfcFacilityPart   | TRACKSTRUCTURE         |

> OPTION 2: Use this template if you need to check at the individual instance level

| **Parent Element** | **Parent Element Type** | **Parent Element Name** | **MinSize** | **MaxSize** | **Child Element** | **Child Element Type** | **Child Element Name** |
|--------------------|-------------------------|-------------------------|-------------|-------------|-------------------|------------------------|------------------------|
| IfcRailway         | Località                | LO1336                  | 1           | 1           | IfcFacilityPart   | TRACKSTRUCTURE         | LO1336-BC01            |
| IfcRailway         | Località                | LO1336                  | 1           | 1           | IfcFacilityPart   | TRACKSTRUCTURE         | LO1336-BC02            |

**NOTE**:
- when **MinSize** and **MaxSize** have the same value, it means exactly. Example: MinSize=MaxSize=1, means that the Parent Element must aggregates exactly 1 Child Element with that Type (and Name).

</details>

<details><summary>Spatial Containment Table template</summary>

> OPTION 1: Use this template if you need to check at predefined type or object type level

| **Spatial Element** | **Spatial Element Type** | **MinSize** | **MaxSize** | **Element**     | **Element Type** |
|---------------------|--------------------------|-------------|-------------|-----------------|------------------|
| IfcFacilityPart     | TRACKSTRUCTURE           | 1           |             | IfcCourse       | BALLASTBED       |
| IfcFacilityPart     | TRACKSTRUCTURE           | 2           |             | IfcRail         | RAIL             |
| IfcFacilityPart     | TRACKSTRUCTURE           | 1           |             | IfcTrackElement | SLEEPER          |

> OPTION 2: Use this template if you need to check at the individual instance level

| **Spatial Element** | **Spatial Element Type** | **Spatial Element Name** | **MinSize** | **MaxSize** | **Element**     | **Element Type** | **Element Name** |
|---------------------|--------------------------|--------------------------|-------------|-------------|-----------------|------------------|------------------|
| IfcFacilityPart     | TRACKSTRUCTURE           | LO1336-BC01              | 1           | 1           | IfcRail         | RAIL             | Left rail        |
| IfcFacilityPart     | TRACKSTRUCTURE           | LO1336-BC01              | 1           | 1           | IfcRail         | RAIL             | Right rail       |
| IfcFacilityPart     | TRACKSTRUCTURE           | LO1336-BC01              | 1           |             | IfcCourse       | BALLASTBED       |                  |
| IfcFacilityPart     | TRACKSTRUCTURE           | LO1336-BC02              | 1           |             | IfcCourse       | BALLASTBED       |                  |

**NOTE**:
- when **MaxSize is empty**, it means **unlimited**. Example: MinSize=1; MaxSize=empty, means that the Spatial Element must contain 1 or more elements of the requested type.
- when **MinSize** and **MaxSize** have the same value, it means exactly. Example: MinSize=MaxSize=1, means that the Spatial Element must contain exactly 1 Element with that Type (and Name).

</details>

<details><summary>Element (De)Composition Table template</summary>

> OPTION 1: Use this template if you need to check at predefined type or object type level

| **Assembly**       | **Assembly Type** | **MinSize** | **MaxSize** | **Element** | **Element Type** | 
|--------------------|-------------------|-------------|-------------|-------------|------------------|
| IfcElementAssembly | TURNOUTPANEL      | 2           | 8           | IfcRail     |                  |


> OPTION 2: Use this template if you need to check at the individual instance level

| **Assembly Element** | **Assembly Type** | **Assembly Name** | **MinSize** | **MaxSize** | **Element** | **Element Type** | **Element Name** |
|----------------------|-------------------|-------------------|-------------|-------------|-------------|------------------|------------------|
| IfcElementAssembly   | TURNOUTPANEL      | DEV FS40          | 2           | 2           | IfcRail     | BLADE            |                  |
| IfcElementAssembly   | TURNOUTPANEL      | DEV FS60          | 4           | 4           | IfcRail     | BLADE            |                  |

**NOTE**:
- when **MinSize** and **MaxSize** have the same value, it means exactly. Example: MinSize=MaxSize=1, means that the Assembly must aggregates exactly 1 Element with that Type (and Name).

</details>

<details><summary>Product Relative Positioning Table template</summary>

> OPTION 1: Use this template if you need to check at predefined type or object type level

| **Product**     | **Product Type** | **Size** | **Positioning Element** | **Positioning Element Type** |
|---------------- |------------------|----------|-------------------------|------------------------------|
| IfcRail         | RAIL             | 2        | IfcReferent             |       STATION                |


> OPTION 2: Use this template if you need to check at the individual instance level

| **Product**     | **Product Type** | **Product Name** | **Size** | **Positioning Element** | **Positioning Element Type** | **Element Name** |
|-----------------|------------------|------------------|----------|-------------------------|------------------------------|------------------|
| IfcRail         | RAIL             | RAIL-01          | 2        | IfcReferent             | na                           |   Alignment-1 Primary Route               |
| IfcTrackElement | SLEEPER          | Sleeper-01       | 1        | IfcReferent             | STATION                      |   PA+220         |


</details>
  
<details><summary>Product Geometric Representation Table template</summary>

> OPTION 1: Use this template if you need to check at predefined type or object type level

| **Product**     | **Product Type** | **Representation Identifier** | **Representation Type** |**Items**           |
|-----------------|------------------|-------------------------------|-------------------------|--------------------|
| IfcAlignment    | na               | Axis                          |       Curve3D           |1 IfcGradientCurve  |


> OPTION 2: Use this template if you need to check at the individual instance level

| **Product**     | **Product Type** | **Product Name**   | **Representation Identifier** | **Representation Type** |**Items**           |
|-----------------|------------------|--------------------|-------------------------------|-------------------------|--------------------|
| IfcAlignment    | na               | Alignment Primary_1| Axis                          |       Curve3D           |1 IfcGradientCurve  |

**NOTE**:
- Items should be listed in the cell with their number.
- One shape representation for a product should be documented in one row. If there are multiple representations, they should be documented in multiple rows.

</details>

<details><summary>Product Placement Table template</summary>

> OPTION 1: Use this template if you need to check at predefined type or object type level

| **Product**     | **Product Type** | **Object Placement** | Relative Placement Product | Relative Placement Product Type |
|-----------------|------------------|----------------------|----------------------------|---------------------------------|
| IfcAlignment    | na               | IfcLocalPlacement    |  IfcSite                   |      na                         |


> OPTION 2: Use this template if you need to check at the individual instance level

| **Product**     | **Product Type** | **Product Name**     | **Object Placement** |Relative Placement Product | Relative Placement Product Type | Relative Placement Product Name |
|-----------------|------------------|----------------------|----------------------|----------------------------|---------------------------------|---------------------------------|
| IfcReferent     | STATION          | 10+599               | IfcLinearPlacement   |    IfcAlignment            |      na                         | Alignment Primary 1             |

**NOTE**:
- Columns **Relative Placement Product**, **Relative Placement Product Type**, **Relative Placement Product Name** are optional. If omitted, it means the Object Placement of the Product has no PlacementRelTo attribute.

</details>























## General

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------------------|----------------------------|
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       | na                         | na                         |
| GENE_01     | All requested entities (and attributes) exist in file             | As per Entities Table | na                         | na                         |
| ORIG_01     | Origin of Coordinate System is set as requested                   | [(0., 0., 0.)]        |                            | Project Global Positioning |
| ORIG_02     | True north is set as requested                                    | [(0., 1., 0.)]        |                            | Project Global Positioning |
| DIST_01     | Unit of measure for all distances                                 | [meter]               |                            | Project Units              |
| ANGL_01     | Unit of measure all angles                                        | [radian]              |                            | Project Units              |
| DIST_02     | Required precision for distances                                  | [0,0001]              | all alignment segments     | na                         |
| ANGL_02     | Required precision for angles and slope                           | [0,000001]            |                            | na                         |




## Alignment

| **RULE ID** | **CRITERIA**                                             | **VALUE [examples]**                           | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|----------------------------------------------------------|------------------------------------------------|----------------------------|------------------------|
| SITE_00     | All IfcAlignment shall always be contained in an IfcSite |                                                |                            | Spatial Containment    |
| ALIG_00     | Alignment layout structure is verified                   | See steps                                      |                            | Alignment Layout       |
| ALIG_01     | Number of alignments contained in file                   | [2]                                            |                            |                        |
| ALIG_02     | Parameters of alignment segments are verified            | As per Alignment Table                         |                            |                        |
| ALIG_03     | Alignment geometric compliance is verified               | As per Alignment geometric compliance document |                            |                        |
| ALIG_04     | Value of the RailHeadDistance along the entire alignment | [1500 mm]                                      | IfcAlignmentCant           |                        |

<details><summary>ALIG_00 steps</summary>

| **STEP ID** | **STEP**                                                                                                                                           |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| ALIG_00.1   | Each IfcAlignment must nest exactly 1 IfcAlignmentHorizontal                                                                                       |
| ALIG_00.2   | Each IfcAlignment must nest at most 1 IfcAlignmentVertical                                                                                         |
| ALIG_00.3   | Each IfcAlignment must nest exactly 1 IfcAlignmentVertical                                                                                         |
| ALIG_00.4   | Each IfcAlignment must nest at most 1 IfcAlignmentCant                                                                                             |
| ALIG_00.5   | Each IfcAlignment must nest exactly 1 IfcAlignmentCant                                                                                             |
| ALIG_00.6   | Each IfcAlignmentHorizontal must be nested only by 1 IfcAlignment                                                                                  |
| ALIG_00.7   | Each IfcAlignmentVertical must be nested only by 1 IfcAlignment                                                                                    |
| ALIG_00.8   | Each IfcAlignmentCant must be nested only by 1 IfcAlignment                                                                                        |
| ALIG_00.9   | Each IfcAlignment must nest only the following entities: IfcAlignmentHorizontal, IfcAlignmentVertical, IfcAlignmentCant, IfcReferent, IfcAlignment |
| ALIG_00.10  | Each IfcAlignmentHorizontal nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentHorizontalSegment         |
| ALIG_00.11  | Each IfcAlignmentVertical nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentVerticalSegment             |
| ALIG_00.12  | Each IfcAlignmentCant nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentCantSegment                     |

</details>




## Alignment (import verification)

| **RULE ID** | **CRITERIA**                                                        | **VALUE (all examples)** |
|-------------|---------------------------------------------------------------------|--------------------------|
| ALIG_10     | Horizontal Starting point Mileage (pk)                              | 0+000                    |
| ALIG_11     | Horizontal Starting point DistAlong                                 | 0                        |
| ALIG_12     | Horizontal Starting point X                                         | 452413.9199              |
| ALIG_13     | Horizontal Starting point Y                                         | 4539456.401              |
| ALIG_14     | Vertical Starting point Mileage                                     | 0+000                    |
| ALIG_15     | Vertical Starting point Z                                           | 5                        |
| ALIG_16     | Horizontal Ending point Mileage (pk)                                | 0+876.3682               |
| ALIG_17     | Horizontal Ending point DistAlong                                   | 876.3682                 |
| ALIG_18     | Horizontal Ending point X                                           | 453202.5241              |
| ALIG_19     | Horizontal Ending point Y                                           | 4539831.929              |
| ALIG_20     | Vertical Ending point Mileage                                       | 0+876.3682               |
| ALIG_21     | Vertical Ending point Z                                             | 2                        |
| ALIG_22     | Total 2D length of alignment (horizontal projection)                | 876.3682                 |
| ALIG_23     | Total 3D length of alignment                                        | 876.3819                 |
| ALIG_24     | Height difference between start and end point of alignment 3D curve | -3                       |

## Superelevation & Width
:construction: under construction :construction:
## Referent & Mileage
:construction: under construction :construction:
## Product relative positioning
  
| **RULE ID** | **CRITERIA**                      | **VALUE [examples]**                 | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|-----------------------------------|--------------------------------------|----------------------------|------------------------|
| PPOS_01     | Product relative positioning is verified | As per Product Relative Positioning Table | na                         | Product Relative Positioning, Product Span Positioning |

> **Acceptance criteria**: For the **Spatial relative positioning** capability, the validation procedure must verify that a Product of the requested type is positioned (via `IfcRelPositions`) exactly a given number of Positioning Elements of the requested type, no more and no less.

<details><summary>PPOS_01 details: Product relative positioning is verified</summary>

> - Given a set of products taken from the [Product Relative Positioning Table](#Product-Relative-Positioning-Table)
> - Then the Product, and optionally the Product Type, exists
> - And the Product must be positioned on exactly [Size] of the requested Positioning Element

</details>

## Object typing
:construction: under construction :construction:
## Material association
:construction: under construction :construction:

## Element (De)Composition (Assemblies)

| **RULE ID** | **CRITERIA**                                       | **VALUE [examples]**                 | **ENTITY (if applicable)** | **CT (if applicable)**                      |
|-------------|----------------------------------------------------|--------------------------------------|----------------------------|---------------------------------------------|
| ASSE_01     | Mandatory components are present in the assemblies | As per Element (De)Composition Table | na                         | Element Composition & Element Decomposition |

> **Acceptance criteria**: For the **ASSE_01 rule**, the validation procedure must verify that an assembly of the requested type (and name) aggregates (via `IfcRelAggregates`) at least a given number of elements of the requested type (and name).

<details><summary>ASSE_01 details: Mandatory components are present in the assemblies</summary>

> - Given a set of assemblies taken from the [Element (De)Composition Table](#Element-(De)Composition)
> - Then the Assembly, and optionally the Assembly Type, exists
> - And the Assembly must aggregate at least a number within [MinSize..MaxSize] of the requested Element

</details>




## Object grouping

| **RULE ID** | **CRITERIA**                                | **VALUE [examples]**                                                                                                                                          | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|---------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|------------------------|
| GROU_00     | Mandatory objects are present in the groups | As per Groups Table                                                                                                                                           | na                         | na                     |
| GROU_01     | Circular reference is not allowed           | Circular reference is not allowed, neither direct (if A includes B, B cannot includes A), nor indirect (if A includes B and B includes C, C cannot include A) | IfcGroup                   | Group Assignment       |
| GROU_02     | Only direct inclusion is allowed            | Example: if A includes B and B includes C, A cannot includes C)                                                                                               | IfcGroup                   | Group Assignment       |
| GROU_03     | Same-level grouping is not allowed          | If two or more Group are part of the same Group, they cannot include each others. Example: if A groups B and C, B cannot group C and vice versa)              | IfcGroup                   | Group Assignment       |
| GROU_04     | Group rooting                               | All Groups that do not have a parent Group must be linked to the IfcProject with an IfcRelDeclares relationship, as per Project Declaration template          | IfcGroup                   | Project Declaration    |
| GROU_05     | Group typing via ObjectType                 | *All group types shall be expressed using the ObjectType (5th attribute) of each occurrence of IfcGroup                                                       | IfcGroup                   | na                     |
| GROU_06     | Allowed entity types for groups             | IfcGroup must be associated (via IfcRelAssignsToGroup) only to IfcProduct or IfcGroup (and subtypes)                                                          | IfcGroup                   | Group Assignment       |

*: this is the only method to express group typing, due to the fact that: i) IfcGroup misses the PredefinedType attribute; and ii) object typing by instantiation of IfcTypeObject is discouraged from IFC4 onward.

> **Acceptance criteria**: For the **GROU_00 rule**, the validation procedure must verify that a group of the requested type is grouping (via `IfcRelAssignsToGroup`) exactly a given number of objects of the requested type, no more and no less.

<details><summary>GROU_00 details: Mandatory objects are present in the groups</summary>

> - Given a set of groups taken from the [Groups Table](#Groups-Table)
> - Then the Group, and optionally the Group Type, exists
> - And the Group must group at least a number within [MinSize..MaxSize] of the requested Object

</details>




## Properties

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




## Spatial (De)Composition

| **RULE ID** | **CRITERIA**                      | **VALUE [examples]**                 | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|-----------------------------------|--------------------------------------|----------------------------|------------------------|
| SDEC_01     | Spatial decomposition is verified | As per Spatial (De)Composition Table | na                         | Spatial Decomposition  |

> **Acceptance criteria**: For the **Spatial decomposition** capability, the validation procedure must verify that a Parent Element of the requested type aggregates (via `IfcRelAggregates`) exactly a given number of Child Elements of the requested type, no more and no less.

<details><summary>SDEC_01 details: Spatial decomposition is verified</summary>

> - Given a set of elements taken from the [Spatial (De)Composition Table](#Spatial-(De)Composition-Table)
> - Then the Parent Element, and optionally the Parent Element Type, exists
> - And the Parent Element must aggregate at least a number within [MinSize..MaxSize] of the requested Child Element

</details>
___

**Bullet point example**:
- IfcRailway *(Name: LO1336)*
  - IfcFacilityPart.TRACKSTRUCTURE *(Name: LO1336-BC-BC01)*
  - IfcFacilityPart.TRACKSTRUCTURE *(Name: LO1336-BC-BC02)*




## Spatial containment

| **RULE ID** | **CRITERIA**                    | **VALUE [examples]**             | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|---------------------------------|----------------------------------|----------------------------|------------------------|
| SCON_01     | Spatial containment is verified | As per Spatial Containment Table | na                         | Spatial Containment    |

> **Acceptance criteria**: For the **Spatial containment** capability, the validation procedure must verify that a Spatial Element of the requested type contains (via `IfcRelContainedInSpatialStructure`) exactly a given number of Elements of the requested type, no more and no less.

<details><summary>SCON_01 details: Spatial containment is verified</summary>

> - Given a set of elements taken from the [Spatial Containment Table](#Spatial-Containment-Table)
> - Then the Spatial Element, and optionally the Spatial Element Type, exists
> - And the Spatial Element must contain at least a number within [MinSize..MaxSize] of the requested Element

</details>
___

**Bullet point example**:
- IfcRailway *(Name: LO1336)*
  - IfcFacilityPart.TRACKSTRUCTURE *(Name: LO1336-BC-BC01)*
    - `IfcCourse.BALLASTBED` *(Name: BC01)*
    - `IfcRail.RAIL` *(Name: Rotaia BC01 SX)*
    - `IfcRail.RAIL` *(Name: Rotaia BC01 DX)*
    - `IfcTrackElement.SLEEPER` *(Name: Traversa 0001)*
    - `IfcTrackElement.SLEEPER` *(Name: Traversa 0002)*
    - `IfcTrackElement.SLEEPER` *(Name: Traversa 000n)*
  - IfcFacilityPart.TRACKSTRUCTURE *(Name: LO1336-BC-BC02)*




## Group Spatial Connectivity

| **RULE ID** | **CRITERIA**                            | **VALUE [examples]**                     | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-----------------------------------------|------------------------------------------|----------------------------|----------------------------|
| SREF_01     | Spatial reference of groups is verified | As per Groups Spatial Connectivity Table | IfcGroup                   | Group Spatial Connectivity |

> **Acceptance criteria**: For the **Group Spatial Connectivity** capability, the validation procedure must verify that a Spatial Element of the requested type references (via `IfcRelReferencedInSpatialStructure`) exactly a given number of Groups of the requested type, no more and no less.

<details><summary>SREF_01 details: Spatial reference of groups is verified</summary>

> - Given a set of elements and groups taken from the [Group Spatial Connectivity Table](#Group-Spatial-Connectivity-Table)
> - Then the Spatial Element, and optionally the Spatial Element Type, exists
> - And the Spatial Element must reference at least a number within [MinSize..MaxSize] of the requested Group

</details>




## Spatial interference
:construction: under construction :construction:
  
## Product geometric representation

| **RULE ID** | **CRITERIA**                            | **VALUE [examples]**                     | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-----------------------------------------|------------------------------------------|----------------------------|----------------------------|
| PREP_01     | Geometric representation of products is verified | As per Product Geometric Representation Table |                   | Product Geometric Representation and its subtemplates |

> **Acceptance criteria**: For the **Group Spatial Connectivity** capability, the validation procedure must verify that a Product of the requested type (and optionally a requested name) has an IfcShapeRepresentation with the requested Representation Identifier, Representation Type and Items.

<details><summary>PREP_01 details:  Geometric representation of products is verified</summary>

> - Given a set of products taken from the [Product Geometric Representation Table](#Product-Geometric-Representation-Table)
> - Then the Product, and optionally the Product Type, exists
> - And the Product must have an IfcShapeRepresentation (via IfcProductDefinitionShape) with the requested Representation Identifier, Representation Type and Items.

</details>
  
## Product placement

| **RULE ID** | **CRITERIA**                            | **VALUE [examples]**                     | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-----------------------------------------|------------------------------------------|----------------------------|----------------------------|
| PPLA_01     | Placement of products is verified | As per Product Placement Table |                   | Product Placement subtemplates |
| PPLA_02     | For a product that has ObjectPlacement as IfcLinearPlacement, the CartesianPosition of IfcLinearPlacement shall be available | depends on cases |                   | Product Linear Placement |
  
> **Acceptance criteria**: For the **Product Placement** capability, the validation procedure must verify that a Product of the requested type (and optionally a requested name) has the requested Object Placement, and optionally the Object Placement has PlacementRelTo reference to the Object Placement of Relative Placement Product with requested Relative Placement Product Type and Relative Placement Product Name.

<details><summary>PPLA_01 details:  Placement of products is verified</summary>

> - Given a set of products taken from the [Product Geometric Representation Table](#Product-Geometric-Representation-Table)
> - Then the Product with Product Type and Product Name, exists
> - And the Product must have Object Placement, and the Object Placement has PlacementRelTo reference to the ObjectPlacement of Relative Placement Product with requested Relative Placement Product Type and Relative Placement Product Name.

</details>
