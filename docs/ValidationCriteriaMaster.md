# Validation Criteria Master Document
This document contains a comprehensive list of validation criteria referenced by all Test Instructions.

Its objective is to guarantee consistency of criteria, allowing the authors to refer to the same table format.

> **ATTENTION**: for some rules a test-specific VALUE might be needed. In this case the tables below just capture an example between []



## Utilities
 [Table converter](https://tableconvert.com/) (e.g., Excel to MD, MD to MD)

<details><summary>Alignment Table template</summary>

| Entity                        | PredefinedType | Name | Start Point X | Start Point Y | Start Direction | Start Radius Of Curvature | End Radius Of Curvature | Segment Length |
|-------------------------------|----------------|------|---------------|---------------|-----------------|---------------------------|-------------------------|----------------|
| IfcAlignmentHorizontalSegment | LINE           | H1   | 452413.9199   | 4539456.401   | 0.214271681     | 0                         | 0                       | 234.719412     |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H2   | 452634.415    | 4539536.869   | 0.214271681     | 0                         | -1000                   | 40             |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H3   | 452671.898    | 4539550.832   | 0.236493911     | -1000                     | -1000                   | 193.464471     |

</details>

<details><summary>Entities Table template</summary>

> Agree on template table

> **OPTION 1**: strictly just the attributes of the entity

| **Element**  | **Attribute**  | **Value**                  |
|--------------|----------------|----------------------------|
| IfcAlignment | Name           | Alignment 1_Primary route  |
|              | Description    | This is just an example    |
|              | ObjectType     | Railway track alignment    |
|              | PredefinedType | USERDEFINED                |
| IfcAlignment | Name           | Alignment 2_Diverted route |
|              | Description    | This is another example    |
|              | ObjectType     | Railway track alignment    |
|              | PredefinedType | USERDEFINED                |

> **OPTION 2**: extend with some other info, with the risk of being redundant with other rules (i.e, rule for properties, material, placement, etc.)

| **Element**            | **Attribute**  | **Value**                 | **Notes**                       |
|------------------------|----------------|---------------------------|---------------------------------|
| IfcAlignment           | Name           | Alignment 1_Primary route |                                 |
|                        | Description    | $                         |                                 |
|                        | ObjectType     | Railway track alignment   |                                 |
|                        | PredefinedType | USERDEFINED               |                                 |
|                        | ************** | ************************  | ************************        |
|                        | Placement      | IfcLocalPlacement         | IfcGradientCurve                |
|                        |                |                           | RepresentationIdentifier="Axis" |
|                        |                |                           | RepresentationType="Curve3D"    |
| IfcAlignmentHorizontal | Name           | AH1                       |                                 |
|                        | Description    | $                         |                                 |
|                        | ************** | ************************  | ************************        |
|                        | Placement      | IfcLocalPlacement         | IfcCompositeCurve               |
|                        |                |                           | RepresentationIdentifier="Axis" |
|                        |                |                           | RepresentationType="Curve2D"    |
| IfcAlignmentVertical   | Name           | AV1                       |                                 |
|                        | Description    | $                         |                                 |
|                        | ************** | ************************  | ************************        |
|                        | Placement      | IfcLocalPlacement         | IfcGradientCurve                |
|                        |                |                           | RepresentationIdentifier="Axis" |
|                        |                |                           | RepresentationType="Curve3D"    |

</details>

<details><summary>Group Table template</summary>

| **Group** | **Group Type**                | **Minimum** | **Maximum** | **Object**         | **Object Type**      | **Notes** |
|-----------|-------------------------------|-------------|-------------|--------------------|----------------------|-----------|
| IfcGroup  | Binari di corsa (Contenitore) | 2           | 2           | IfcFacilityPart    | TRACKSTRUCTURE       | From AL22 |
| IfcGroup  | Deviatoi                      | 1           | 1           | IfcElementAssembly | TURNOUTPANEL         | From TP01 |
| IfcGroup  | Massicciata                   | 1           |             | IfcCourse          | BALLASTBED           | From SP01 |
| IfcGroup  | Traverse                      | 1           |             | IfcGroup           | Segmento di traverse |           |
| IfcGroup  | Segmento di traverse          | 1           |             | IfcTrackElement    | SLEEPER              | From SP01 |
| IfcGroup  | Rotaie                        | 1           | 1           | IfcGroup           | Segmento di rotaia   |           |
| IfcGroup  | Segmento di rotaia            | 2           | 2           | IfcRail            | RAIL                 | From SP01 |

NOTE:
- when **Minimum** and **Maximum** have the same value, it means exactly. Example: Minimum=Maximum=1, means that the group must groups exactly 1 object of that type.
- when **Maximum is empty**, it means **unlimited**. Example: Minimum=1; Maximum=empty, means that the group must group 1 or more object of the requested type.
- the **Notes** column indicates (when the object to be grouped is coming from a pre-requisite test) which is the mentioned test.

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
## Element placement & relative positioning
:construction: under construction :construction:
## Object typing
:construction: under construction :construction:
## Material association
:construction: under construction :construction:
## Assembly (Element decomposition)
:construction: under construction :construction:




## Object grouping

| RULE ID | CRITERIA                                    | VALUE [examples]                                                                                                                                               | ENTITY (if applicable) | CT (if applicable)  |
|---------|---------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------------|
| GROU_00 | Mandatory objects are present in the groups | As per Group Table                                                                                                                                             | na                     | na                  |
| GROU_01 | Circular reference is not allowed           | Circular reference is not allowed, neither direct (if A includes B, B cannot includes A), nor indirect (if A includes B and B includes C, C cannot includes A) | IfcGroup               | Group Assignment    |
| GROU_02 | Only direct inclusion is allowed            | Example: if A includes B and B includes C, A cannot includes C)                                                                                                | IfcGroup               | Group Assignment    |
| GROU_03 | Same-level grouping is not allowed          | If two or more Group are part of the same Group, they cannot include each others. Example: if A groups B and C, B cannot group C and vice versa)               | IfcGroup               | Group Assignment    |
| GROU_04 | Group rooting                               | All Groups that do not have a parent Group must be linked to the IfcProject with an IfcRelDeclares relationship, as per Project Declaration template           | IfcGroup               | Project Declaration |
| GROU_05 | Group typing via ObjectType                 | *All group types shall be expressed using the ObjectType (5th attribute) of each occurrence of IfcGroup                                                        | IfcGroup               | na                  |
| GROU_06 | Allowed entity types for groups             | IfcGroup must be associated (via IfcRelAssignsToGroup) only to IfcProduct or IfcGroup (and subtypes)                                                           | IfcGroup               | Group Assignment    |

*: this is the only method to express group typing, due to the fact that: i) IfcGroup misses the PredefinedType attribute; and ii) object typing by instantiation of IfcTypeObject is discouraged from IFC4 onward.

<details><summary>GROU_00 details</summary>

> **GROU_00: Mandatory objects are present in the groups**:
> - Given a set of groups taken from the "Group Table"
> - Then the Group, and optionally the Group Type, exists
> - And the Group must group at least a number within [Minimum..Maximum] of the requested Object

</details>



## Properties
:construction: under construction :construction:
## Spatial decomposition
:construction: under construction :construction:
## Spatial containment
:construction: under construction :construction:
## Group spatial connectivity
:construction: under construction :construction:
## Spatial interference
:construction: under construction :construction:
