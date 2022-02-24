## Variations
The following occurrence variations need to be checked and certified in relation to the targeted entities and concept templates:

- IfcAlignmentHorizontalSegment - *includes LINE, CIRCULARARC and CLOTHOID*
- IfcAlignmentVerticalSegment - *includes CONSTANTGRADIENT and CIRCULARARC*
- IfcAlignmentCantSegment - *includes CONSTANTCANT and LINEARTRANSITION*

## Entity

- IfcProject
- IfcOwnerHistory
- IfcPersonAndOrganization
- IfcPerson
- IfcOrganization
- IfcApplication
- IfcDirection
- IfcCartesianPoint
- IfcAxis2Placement3D
- IfcGeometricRepresentationContext
- IfcSIUnit
- IfcUnitAssignment
- IfcSite
- IfcLocalPlacement
- IfcRelAggregates
- IfcRelContainedInSpatialStructure
- IfcAlignment
- IfcAlignmentHorizontal
- IfcAlignmentVertical
- IfcAlignmentCant
- IfcAlignmentSegment
- IfcAlignmentHorizontalSegment
- IfcAlignmentVerticalSegment
- IfcAlignmentCantSegment
- IfcRelNests
- IfcCompositeCurve
- IfcLine
- IfcCircle
- IfcClothoid
- IfcGradientCurve
- IfcSegmentedReferenceCurve
- IfcCurveSegment
- IfcProductDefinitionShape
- IfcShapeRepresentation
- IfcVector
- IfcAxis2Placement2D

## Model Dataset
This test case utilises the attached dataset documented by the following drawings and data schedule. 


#### Horizontal Segments
| start_point_x | start_point_y | start_direction | start_radius_of_curvature | end_radius_of_curvature | segment_length | gravity_center_line_height | predefined_type |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| 1213636.85116 | 2723135.63807 | 3.098579537773168 | 0 | 0 | 18.11881 | None | LINE |
| 1213618.74911 | 2723136.41718 | 3.0985826793658218 | 30000.0 | 30000.0 | 10.43075 | None | CIRCULARARC |
| 1213608.32793 | 2723136.86385 | 3.098930296592942 | 0 | 0 | 488.5896 | None | LINE |
| 1213120.1829 | 2723157.70188 | 3.098930296592942 | 0.0 | -467.0 | 72.0 | None | CLOTHOID |
| 1213048.37002 | 2723162.61845 | 3.021842524377686 | -467.0 | -467.0 | 157.77472 | None | CIRCULARARC |
| 1212897.84194 | 2723207.32062 | 2.6839951791717414 | -467.0 | 0.0 | 72.0 | None | CLOTHOID |
| 1212834.98549 | 2723242.39667 | 2.6069074069564864 | 0 | 0 | 191.97447 | None | LINE |
| 1212669.80508 | 2723340.22115 | 2.6069074069564864 | 0.0 | -472.0 | 68.0 | None | CLOTHOID |
| 1212612.15796 | 2723376.25831 | 2.5348735148430603 | -472.0 | -472.0 | 67.74031 | None | CIRCULARARC |
| 1212559.46542 | 2723418.73625 | 2.3913558234898526 | -472.0 | 0.0 | 68.0 | None | CLOTHOID |
| 1212512.01552 | 2723467.42275 | 2.319321931376427 | 0.0 | 467.0 | 65.0 | None | CLOTHOID |
| 1212466.69618 | 2723513.99891 | 2.3889151201572787 | 467.0 | 467.0 | 46.06931 | None | CIRCULARARC |
| 1212431.57438 | 2723543.78346 | 2.487564585231917 | 467.0 | 904.0 | 39.0 | None | CLOTHOID |
| 1212399.81582 | 2723566.40828 | 2.5508912391466536 | 904.0 | 904.0 | 44.63924 | None | CIRCULARARC |
| 1212362.14205 | 2723590.34453 | 2.6002709495554104 | 904.0 | 470.0 | 39.0 | None | CLOTHOID |
| 1212328.17009 | 2723609.48607 | 2.6633311964131225 | 470.0 | 470.0 | 91.20524 | None | CIRCULARARC |
| 1212243.64561 | 2723643.36729 | 2.8573848613512407 | 470.0 | 0.0 | 66.0 | None | CLOTHOID |
| 1212179.51076 | 2723658.88542 | 2.9275975722033807 | 0.0 | -462.0 | 66.0 | None | CLOTHOID |
| 1212115.38269 | 2723674.42942 | 2.856169064994302 | -462.0 | -462.0 | 93.4246 | None | CIRCULARARC |
| 1212028.99815 | 2723709.58855 | 2.653951343227299 | -462.0 | 0.0 | 87.0 | None | CLOTHOID |
| 1211954.87657 | 2723755.07513 | 2.5597954552047226 | 0 | 0 | 254.74363 | None | LINE |
| 1211742.04429 | 2723895.06347 | 2.5597954552047226 | 0.0 | 870.0 | 81.0 | None | CLOTHOID |
| 1211673.69477 | 2723938.51551 | 2.606347103906718 | 870.0 | 870.0 | 182.71801 | None | CIRCULARARC |
| 1211507.93331 | 2724014.58438 | 2.8163679135067072 | 870.0 | 0.0 | 74.0 | None | CLOTHOID |
| 1211437.17604 | 2724036.2299 | 2.858896595736148 | 0 | 0 | 33.63773 | None | LINE |
#### Vertical Segments
| start_dist_along | horizontal_length | start_height | start_gradient | end_gradient | radius_of_curvature | predefined_type |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| 0.0 | 61.67186 | 459.1209 | 0.00665013 | 0.00665013 | 0.0 | CONSTANTGRADIENT |
| 61.67185 | 0.75008 | 459.531 | 0.006650120000000001 | 0.0058999956436960755 | 1000.0 | CIRCULARARC |
| 62.42194 | 462.76333 | 459.5357 | 0.005900000000000001 | 0.005900000000000001 | 0.0 | CONSTANTGRADIENT |
| 525.18527 | 0.59997 | 462.266 | 0.005900000000000001 | 0.005500000498816251 | 1500.0 | CIRCULARARC |
| 525.78524 | 107.84169 | 462.2694 | 0.0055 | 0.0055 | 0.0 | CONSTANTGRADIENT |
| 633.62692 | 0.64997 | 462.8626 | 0.0055 | 0.006150003115452429 | -1000.0 | CIRCULARARC |
| 634.27689 | 159.04448 | 462.8663 | 0.00615 | 0.00615 | 0.0 | CONSTANTGRADIENT |
| 793.32136 | 0.59997 | 463.8445 | 0.00615 | 0.0058499987972931424 | 2000.0 | CIRCULARARC |
| 793.92134 | 413.39066 | 463.8481 | 0.005849999999999999 | 0.005849999999999999 | 0.0 | CONSTANTGRADIENT |
| 1207.31201 | 0.73497 | 466.2664 | 0.005849999999999999 | 0.004799998053876806 | 700.0 | CIRCULARARC |
| 1208.04695 | 380.96596 | 466.2703 | 0.0048 | 0.0048 | 0.0 | CONSTANTGRADIENT |
| 1589.01293 | 0.65998 | 468.099 | 0.0048 | 0.004249999753908035 | 1200.0 | CIRCULARARC |
| 1589.6729 | 97.23633 | 468.1019 | 0.00425 | 0.00425 | 0.0 | CONSTANTGRADIENT |
| 1686.90923 | 0.62999 | 468.5152 | 0.00425 | 0.0035499950979519745 | 900.0 | CIRCULARARC |
| 1687.5392 | 334.36918 | 468.5177 | 0.0035499999999999998 | 0.0035499999999999998 | 0.0 | CONSTANTGRADIENT |
| 2021.9084 | 0.69999 | 469.7047 | 0.0035499999999999998 | 0.003449999590967274 | 7000.0 | CIRCULARARC |
| 2022.60838 | 361.601 | 469.7071 | 0.0034500000000000004 | 0.0034500000000000004 | 0.0 | CONSTANTGRADIENT |
| 2384.20938 | 0.65999 | 470.9546 | 0.0034500000000000004 | 0.002899999996127151 | 1200.0 | CIRCULARARC |
| 2384.86938 | 92.80174 | 470.9567 | 0.0029 | 0.0029 | 0.0 | CONSTANTGRADIENT |
| 2477.67111 | 0.3953 | 471.2258 | 0.0029 | 0.00369061293954551 | -500.0 | CIRCULARARC |
#### Cant Segments
| start_dist_along | horizontal_length | start_cant_left | end_cant_left | start_cant_right | end_cant_right | predefined_type |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| 0.0 | 0.00263 | 0.0 | 0.0 | -0.0 | -0.0 | CONSTANTCANT |
| 0.00262 | 517.13653 | 0.0 | 0.0 | -0.0 | -0.0 | CONSTANTCANT |
| 517.13915 | 72.0 | 0.0 | -0.063 | -0.0 | 0.063 | LINEARTRANSITION |
| 589.13915 | 157.77472 | -0.063 | -0.063 | 0.063 | 0.063 | CONSTANTCANT |
| 746.91387 | 72.0 | -0.063 | 0.0 | 0.063 | -0.0 | CONSTANTCANT |
| 818.91387 | 191.97447 | 0.0 | 0.0 | -0.0 | -0.0 | CONSTANTCANT |
| 1010.88834 | 68.0 | 0.0 | -0.063 | -0.0 | 0.063 | LINEARTRANSITION |
| 1078.88834 | 67.74031 | -0.063 | -0.063 | 0.063 | 0.063 | CONSTANTCANT |
| 1146.62865 | 68.0 | -0.063 | 0.0 | 0.063 | -0.0 | CONSTANTCANT |
| 1214.62866 | 65.0 | 0.0 | 0.062 | -0.0 | -0.062 | CONSTANTCANT |
| 1279.62866 | 46.06931 | 0.062 | 0.062 | -0.062 | -0.062 | CONSTANTCANT |
| 1325.69796 | 39.0 | 0.062 | 0.0325 | -0.062 | -0.0325 | LINEARTRANSITION |
| 1364.69797 | 44.63924 | 0.0325 | 0.0325 | -0.0325 | -0.0325 | CONSTANTCANT |
| 1409.33721 | 39.0 | 0.0325 | 0.063 | -0.0325 | -0.063 | CONSTANTCANT |
| 1448.33721 | 91.20524 | 0.063 | 0.063 | -0.063 | -0.063 | CONSTANTCANT |
| 1539.54245 | 66.0 | 0.063 | 0.0 | -0.063 | -0.0 | LINEARTRANSITION |
| 1605.54245 | 66.0 | 0.0 | -0.063 | -0.0 | 0.063 | LINEARTRANSITION |
| 1671.54245 | 93.4246 | -0.063 | -0.063 | 0.063 | 0.063 | CONSTANTCANT |
| 1764.96705 | 87.0 | -0.063 | 0.0 | 0.063 | -0.0 | CONSTANTCANT |
| 1851.96705 | 254.74363 | 0.0 | 0.0 | -0.0 | -0.0 | CONSTANTCANT |
| 2106.71067 | 81.0 | 0.0 | 0.0375 | -0.0 | -0.0375 | CONSTANTCANT |
| 2187.71067 | 182.71801 | 0.0375 | 0.0375 | -0.0375 | -0.0375 | CONSTANTCANT |
| 2370.42869 | 74.0 | 0.0375 | 0.0 | -0.0375 | -0.0 | LINEARTRANSITION |
| 2444.42869 | 33.63773 | 0.0 | 0.0 | -0.0 | -0.0 | CONSTANTCANT |

*This is a later step that involved the detailed documentation of the certification dataset (model)*


## Drawings (Visualisations)
The following Drawings and visualisations describe the test case dataset to be modelled and certified.


## Supporting files

| Filename                          | Description                               |
|-----------------------------------|-------------------------------------------|
| *filename*                        | *short description*                       |
