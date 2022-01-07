## Variations
The Following occurence variations need to be checked and certified in relation to the targeted entities and concept templates:

- (Entity_01) IfcAnnotation/SUPERELEVATIONEVENT - *Pset_SuperElevation needs all variants of Side and TransitionSuperelevation tested. Furthermore, values for Superelevation shall include both positive and negative values*

- (Entity_02) IfcAnnotation/WIDTHEVENT - *Pset_Width needs all variants of Side and TransitionWidth tested.*

## Model Dataset
This test case utilises the attached dataset documented by the following drawings and data schedule.

"Synopsis" (unique entities for this test in **bold**):

- IfcProject

  - IfcGeometricRepresentationContext

    - IfcMapConversion
      - IfcProjectedCRS

  - IfcSite

    - IfcAlignment
      - Should have straights, clothoid/circular arc to the left and to the right
      - Vertical is not really needed but is probably part of the included E1-ALRF

    - IfcRoad
      - IfcFacilityPart/ROADSEGMENT
        - **IfcFacilityPart/CARRIAGEWAY**
          - **IfcAnnotation/SUPERELEVATIONEVENT (one for every start of alignment element)**
            - **Pset_Superelevation (left side)**
            - **IfcLinearPlacement**
          - **IfcAnnotation/SUPERELEVATIONEVENT (one for every start of alignment element)**
            - **Pset_Superelevation (right side)**
            - **IfcLinearPlacement**
          - **IfcAnnotation/WIDTHEVENT (one at start, add a narrowing of the road somewhere along the alignment)**
            - **Pset_Width (both)**
            - **IfcLinearPlacement**

*This is a later step tha involved the detailed documentation of the certification dataset (model)*


## Drawings (Visualisations)
The following Drawings and visualisations describe the test case dataset to be modelled and certified.


## Supporting files

| Filename                          | Description                               |
|-----------------------------------|-------------------------------------------|
| *filename*                        | *short description*                       |