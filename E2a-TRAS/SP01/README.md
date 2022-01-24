# Test instructions

| Documentation Code   | Test Title                             | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|----------------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_SP01  | (RFI) Track structure for single track | E2a (TRAS)    | SP01      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |











## Model Dataset

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename              | Type (format) | Description                                                        |
|-----------------------|---------------|--------------------------------------------------------------------|
| TrackCrossSection     | drawing (png) | Track cross section to be used as example                          |
| SleeperPlacement      | figure (png)  | Information on how to position sleepers along the alignment        |



































# Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section**, and **the ones of pre-required tests** shall be verified, with no exception. :zap:

### General

- All the concept templates must be correctly implemented as presented in the validation criteria
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file
- All validation criteria of the pre-required tests shall apply here too

| **ID**  | **CRITERIA**                                      | **VALUE** | **COMMENT** |
|---------|---------------------------------------------------|-----------|-------------|
| ENAT_01 | Requested entities (and attributes) exist in file | See below |             |

<details><summary>Entities and attributes</summary>

`IfcBlaBla`




</details>


### Object typing

> **Acceptance criteria**: For the **Object typing** capability, the validation procedure must verify that an IFC entity type with the given Name is typing (via `IfcRelDefinesByType`) exactly a given number of objects of the requested Name, no more and no less.
>
> If present, all criteria listed in [Usages, Constraints & Logic](#Usages,-Constraints-&-Logic), and in the same section of precondition tests, shall be verified too.

| Entity Type     | Entity Type Name                    | Minimum | Maximum | IfcObject       | IfcObject Name                      |
|-----------------|-------------------------------------|---------|---------|-----------------|-------------------------------------|
| IfcCourseType   | Segmento di massicciata             | 1       | 1       | IfcCourse       | Segmento di massicciata M01         |
| IfcCourseType   | Segmento di massicciata             | 1       | 1       | IfcCourse       | Segmento di massicciata M02         |


NOTE:
- when **Minimum** and **Maximum** have the same value, it means exactly. Example: Minimum=Maximum=1, means that the entity type must type exactly 1 object with that Name.

</details>