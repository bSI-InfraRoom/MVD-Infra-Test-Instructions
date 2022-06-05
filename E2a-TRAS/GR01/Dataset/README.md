# Dataset description

| Documentation Code   | Test Title                    | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|-------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_GR01  | (RFI) Group objects           | E2a (TRAS)    | GR01      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |
## Model Dataset

This test case utilises the following dataset.

| Filename                                   | Description                                                                                                  |
|--------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| [GroupingOverview](./GroupingOverview.png) | Diagram describing the expected structure regarding [grouping and spatial relationships](#Grouping-overview) |


## Grouping overview

The image below shows the 12 groups required for this test, the relationships among them, with the contained products, and with the spatial structure elements.

<img src=".//GroupingOverview.png" width="1080"/>

**IMPORTANT**: All subtypes of IfcElement (pink in the figure) must be contained in the corresponding `IfcFacilityPart.TRACKSTRUCTURE` element (either in *Binario IV dispari - Orte Falconara*, or in *Binario V dispari - Orte Falconara*), using the `IfcRelContainedInSpatialStructure` relationship.

**ATTENTION**: Given an `IfcElementAssembly` and its components, only the assembly shall have a `IfcRelContainedInSpatialStructure` relationship with the spatial structure element. As per [Spatial Containment](http://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Connectivity/Spatial_Structure/Spatial_Containment/content.html) concept template
