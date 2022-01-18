# Dataset description

| Documentation Code  | Test Title                           | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|---------------------|--------------------------------------|---------------|-----------|-----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_GL01 | (RFI) Global Positioning RFI dataset | E2a (TRAS)    | GL01      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |

## Model Dataset

This test case utilises the following dataset.

| Filename                               | Type (format) | Description                                               |
|----------------------------------------|---------------|-----------------------------------------------------------|
| [GeographicData](./GeographicData.png) | table (png)   | [Geographic data relevant for the test](#Geographic-Data) |


### Geographic Data

The table below captures the properties or the Geographic Coordinate System (GCS) and Projected Coordinate System (PGC), usefull for the test case mentioned in the header.

<img src="./GeographicData.png" height="500"/>

Note:
- A geographic coordinate system (GCS) is a reference framework that defines the locations of features on a model of the earth. It’s shaped like a globe, so its spherical. Its units are angular and are usually degrees.
- A projected coordinate system (PCS) is flat. It contains a GCS, but it converts that GCS into a flat surface, using math (the projection algorithm) and other parameters. Its units are linear, most commonly meters.
