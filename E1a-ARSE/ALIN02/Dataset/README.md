## Variations
The Following occurrence variations need to be checked and certified in relation to the targeted entities and concept templates:

- Entity_01 - *decription of variation*
- Entity_02 - *decription of variation*

***=>What other elements occur for roads?***



## Model Dataset
This test case utilises the attached dataset documented by the following drawings and data schedule. 

"Synopsis":

- IfcAlignment => IfcPolyline (Axis,Curve3D)?
  - IfcAlignmentHorizontal => IfcCompositeCurve (Axis,Curve2D)
    - Line
    - Clothoid (to left)
    - Circular arc (left)
    - Clothoid (to straight)
    - Line
    - Clothoid (to right)
    - Circular arc (right)
    - Clothoid  (to straight)
    - Line
  - IfcAlignmentVertical => IfcGradientCurve (Axis,Curve3D)
    - Line (up)
    - Parabolic arc/Circular arc  
    - Line (down)
    - Parabolic arc/Circular arc
    - Line (up)

*This is a later step tha involved the detailed documentation of the certification dataset (model)*


## Drawings (Visualisations)
The following Drawings and visualisations describe the test case dataset to be modelled and certified.


## Supporting files

| Filename                          | Description                               |
|-----------------------------------|-------------------------------------------|
| *filename*                        | *short description*                       |