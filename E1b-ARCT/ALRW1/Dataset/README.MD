## Variations

The testcase ALRW1 consists of 8 variations. Each variation starts in a local carthesian coordinate system at x/y-coordinates 0/0 and heads into the direction of the positive x-axis.

| Parameter | Value | IFC Parameter |
| ----------------------------- | --------------------------------------------- | --------------------------------------------- |
| tested horizontal transition | BLOSSCURVE | IfcAlignmentHorizontalSegment.PredefinedType |
| tested cant transition | BLOSSCURVE | IfcAlignmentCantSegment.PredefinedType |
| start direction [rad] | 0 | IfcAlignmentHorizontalSegment.StartDirection |
| horizontal segmentlength [m] for all variations: |   100.0000 | IfcAlignmentHorizontalSegment.SegmentLength  |
| cant segmentlength [m] for all variations: |   100.0000 | IfcAlignmentCantSegment.HorizontalLength  |

Please note: horizontal start station and cant start station are identical. Horizontal length and the cant length are identical too.

| Variation    | Segmentlength | StartRadiusOfCurvature  | EndRadiusOfCurvature    | StartCantLeft | EndCantLeft  | StartCantRight | EndCantRight | Railhead Distance |
| -------------|--------------:|------------------------:|------------------------:|--------------:|-------------:|---------------:|--------------:|------------------:|
| [**ALRW1_01**](./ALRW1_01) | 100.0 | straight line | 300 (left leaning) | 0 | 0 | 0 | 0.1 | 1.5 | TOBEDONE | TOBEDONE | TOBEDONE | TOBEDONE |
| [**ALRW1_02**](./ALRW1_02) | 100.0 | straight line | -300 (right leaning) | 0 | 0.1 | 0 | 0 | 1.5 | TOBEDONE | TOBEDONE | TOBEDONE | TOBEDONE |
| [**ALRW1_03**](./ALRW1_03) | 100.0 | 300 (left leaning) | straight line | 0 | 0 | 0.1 | 0 | 1.5 | TOBEDONE | TOBEDONE | TOBEDONE | TOBEDONE |
| [**ALRW1_04**](./ALRW1_04) | 100.0 | -300 (right leaning) | straight line | 0.1 | 0 | 0 | 0 | 1.5 | TOBEDONE | TOBEDONE | TOBEDONE | TOBEDONE |
| [**ALRW1_05**](./ALRW1_05) | 100.0 | 1000 (left leaning) | 300 (left leaning) | 0 | 0 | 0.03 | 0.1 | 1.5 | TOBEDONE | TOBEDONE | TOBEDONE | TOBEDONE |
| [**ALRW1_06**](./ALRW1_06) | 100.0 | -1000 (right leaning) | -300 (right leaning) | 0.03 | 0.1 | 0 | 0 | 1.5 | TOBEDONE | TOBEDONE | TOBEDONE | TOBEDONE |
| [**ALRW1_07**](./ALRW1_07) | 100.0 | 300 (left leaning) | 1000 (left leaning) | 0 | 0 | 0.1 | 0.03 | 1.5 | TOBEDONE | TOBEDONE | TOBEDONE | TOBEDONE |
| [**ALRW1_08**](./ALRW1_08) | 100.0 | -300 (right leaning) | -1000 (right leaning) | 0.1 | 0.03 | 0 | 0 | 1.5 | TOBEDONE | TOBEDONE | TOBEDONE | TOBEDONE |


## Model Dataset

Each variation has a folder of its own.

The parameters are shown in the README.MD document for the folder.

The IFC-reference file named "*Variationname*.ifc" contains all entities carrying the relevant railway domain specific parameters.

The second IFC-reference file named "*Variationname*"_geometry.ifc" is enriched with the entites defining the 3D geometry of the segment.

Each variation contains an EXCEL-document consting of three sheets:
* Overview / Header
* point lists with x/y coordinates, horizontal curvature, applied cant and cant angle
* Documentation

The EXCEL file contains a pointslist for the given segment obtained directly from the railway domain specific parameters.

The Textfile named "*Variationname*_geometry_pointlist.txt" contains pointlists for the given segments obtained directly from the IFC-geometry. 



## Drawings (Visualisations)

Each testcase contains one png-file showing:

 * x/y-plot
 * curvature-plot
 * cant-plot




## Supporting files

Not applicable
