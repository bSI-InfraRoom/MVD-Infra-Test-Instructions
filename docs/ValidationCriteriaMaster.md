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

</details>

## General

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  | **CAPABILITY** | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-------------------------------------------------------------------|-----------------------|----------------|----------------------------|----------------------------|
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       | Preconditions  | na                         | na                         |
| GENE_01     | All requested entities (and attributes) exist in file             | As per Entities Table | Project Setup  | na                         | na                         |
| ORIG_01     | Origin of Coordinate System is set as requested                   | [(0., 0., 0.)]        | Project Setup  |                            | Project Global Positioning |
| ORIG_02     | True north is set as requested                                    | [(0., 1., 0.)]        | Project Setup  |                            | Project Global Positioning |
| DIST_01     | Unit of measure for all distances                                 | [meter]               | Project Setup  |                            | Project Units              |
| ANGL_01     | Unit of measure all angles                                        | [radian]              | Project Setup  |                            | Project Units              |
| DIST_02     | Required precision for distances                                  | [0,0001]              | Project Setup  | all alignment segments     | na                         |
| ANGL_02     | Required precision for angles and slope                           | [0,000001]            | Project Setup  |                            | na                         |




## Alignment

| **RULE ID** | **CRITERIA**                                             | **VALUE [examples]**                           | **CAPABILITY** | **ENTITY (if applicable)** | **CT (if applicable)** |
|-------------|----------------------------------------------------------|------------------------------------------------|----------------|----------------------------|------------------------|
| SITE_00     | All IfcAlignment shall always be contained in an IfcSite |                                                | Alignment      |                            | Spatial Containment    |
| ALIG_00     | Alignment layout structure is verified                   | See steps                                      | Alignment      |                            | Alignment Layout       |
| ALIG_01     | Number of alignments contained in file                   | [2]                                            | Alignment      |                            |                        |
| ALIG_02     | Parameters of alignment segments are verified            | As per Alignment Table                         | Alignment      |                            |                        |
| ALIG_03     | Alignment geometric compliance is verified               | As per Alignment geometric compliance document | Alignment      |                            |                        |
| ALIG_04     | Value of the RailHeadDistance along the entire alignment | [1500 mm]                                      | Alignment      | IfcAlignmentCant           |

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
## Group
:construction: under construction :construction:
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
