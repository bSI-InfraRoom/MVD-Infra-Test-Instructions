# Data tables

## Entities table

| Element**              | **Attribute**   | **Value**                 | **Notes**                                                    |
| ---------------------- | --------------- | ------------------------- | ------------------------------------------------------------ |
| IfcProject             | Name            | A                         |                                                              |
| IfcSite                | Name            | A.a                       |                                                              |
| IfcAlignment           | Name            | A.a.A1                    | Track                                                        |
| IfcAlignmentHorizontal | Name            | A.a.AH1                   |                                                              |
| IfcAlignmentVertical   | Name            | A.a.AV1                   |                                                              |
| IfcAlignment           | Name            | A.a.A2                    | Road                                                         |
| IfcAlignmentHorizontal | Name            | A.a.AH2                   |                                                              |
| IfcAlignmentVertical   | Name            | A.a.AV2                   |                                                              |
| IfcRoad                | Name            | A.a                       |                                                              |
| IfcElementAssembly     | Name            | A.a.SA1                   | See<br />TOI_Boom_barrier_system_329100                      |
|                        | PredefinedType  | SIGNALASSEMBLY            |                                                              |
| IfcDoor                | Name            | A.a.1.SA1.D1              | See<br />TOI_Boom_barrier_system_329100<br />GUID: 2ELpFM9EdDVm00000000$u |
|                        | PredefinedType  | BOOM_BARRIER              |                                                              |
| IfcFooting             | Name            | A.a.1.SA1.F1              | See<br />TOI_Boom_barrier_system_329100<br />GUID: 2ELpFM9EdDVm000000015_ and 2ELpFM9EdDVm00000000$L |
|                        | PredefinedType  | PAD_FOOTING               |                                                              |
| IfcRailing             | Name            | A.a.SA1.R1                | See<br />TOI_Boom_barrier_system_329100<br />GUID: 2ELpFM9EdDVm00000000$$ |
|                        | PredefinedType  | GUARDRAIL                 |                                                              |
| IfcElementAssembly     | Name            | A.a.SA1.SA2               | See<br />TOI_Boom_barrier_system_329100                      |
|                        | PreedefinedType | SIGNALASSEMBLY            |                                                              |
| IfcPost                | Name            | A.a.SA1.SA2.P1            | See<br />TOI_Boom_barrier_system_329100<br />GUID: 2ELpFM9EdDVm000000010n |
|                        | PredefinedType  | MEMBER                    |                                                              |
| IfcSignal              | Name            | A.a.SA1.SA2.SV1           | See<br />TOI_Boom_barrier_system_329100<br />GUID: 2ELpFM9EdDVm00000000$g |
|                        | PredefinedType  | VISUAL                    |                                                              |
| IfcSignal              | Name            | A.a.SA1.SA2.SA1           | See<br />TOI_Boom_barrier_system_329100<br />GUID: 2ELpFM9EdDVm00000000$n |
|                        | PredefinedType  | AUDIO                     |                                                              |
| IfcSign                | Name            | A.a.SA1.SA2.SP1           | See<br />TOI_Boom_barrier_system_329100<br />GUID: 2ELpFM9EdDVm00000000$S |
|                        | PredefinedType  | PICTORAL                  |                                                              |
| IfcFacilityPart        | Name            | A.a.1.1                   |                                                              |
|                        | PredefinedType  | ROADSEGMENT               |                                                              |
| IfcFacilityPart        | Name            | A.a.1.2                   |                                                              |
|                        | PredefinedType  | LEVELCROSSING             |                                                              |
| IfcFacilityPart        | Name            | A.a.1.3                   |                                                              |
|                        | PredefinedType  | ROADSEGMENT               |                                                              |
| IfcRailway             | Name            | A.a.2                     |                                                              |
| IfcFacilityPart        | Name            | A.a.2.1                   |                                                              |
|                        | PredefinedType  | TRACKSTRUCTUREPART        |                                                              |
| IfcFacilityPart        | Name            | A.a.2.2                   |                                                              |
|                        | PredefinedType  | LEVELCROSSING             |                                                              |
| IfcFacilityPart        | Name            | A.a.2.3                   |                                                              |
|                        | PredefinedType  | TRACKSTRUCTUREPART        |                                                              |
| IfcSensor              | Name            | A.a.2.2.WS1               | See<br />TOI_Axle_counter_329161<br />GUID: 0zicwwnhzFqRBHxtsvFBbM |
|                        | PredefinedType  | WHEELSENSOR               |                                                              |
| IfcSensor              | Name            | A.a.2.2.WS2               | See<br />TOI_Axle_counter_329161<br />GUID: 3RbW_mdDb0j91BT3FCeIwe |
|                        | PredefinedType  | WHEELSENSOR               |                                                              |
| IfcJunctionBox         | Name            | A.a.2.2.JB1               | See<br />TOI_Cable_junction_box_329161                       |
|                        | PredefinedType  | DATA                      |                                                              |
| IfcJunctionBox         | Name            | A.a.2.2.JB2               | See<br />TOI_Cable_junction_box_329161                       |
|                        | PredefinedType  | DATA                      |                                                              |
| IfcDiscreteAccessory   | Name            | A.a.2.2.SP1               | Snow plough protection. See<br />TOI_Snow_Plough_Protection_329163<br />GUID: 2GAyD8xa8l0m00000001Fo |
|                        | PredefinedType  | RAIL_MECHANICAL_EQUIPMENT |                                                              |
| IfcDiscreteAccessory   | Name            | A.a.2.2.SP1               | Snow plough protection. See<br />TOI_Snow_Plough_Protection_329163<br />GUID: 2GAyD8xa8l0m00000001Fw |
|                        | PredefinedType  | RAIL_MECHANICAL_EQUIPMENT |                                                              |



## Horizontal segments table - AH1

| Entity                        | PredefinedType | Name | Start Point X | Start Point Y | Start Direction | Start Radius Of Curvature | End Radius Of Curvature | Segment Length |
| ----------------------------- | -------------- | ---- | ------------- | ------------- | --------------- | ------------------------- | ----------------------- | -------------- |
| IfcAlignmentHorizontalSegment | LINE           | H1   | 1304,078529   | 2487,611348   | 4,207620618     | 0                         | 0                       | 1091,152467    |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H2   | 776,392063    | 1532,540304   | 4,207620618     | 0                         | 1518                    | 80             |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H3   | 738,321388    | 1462,182442   | 4,233696595     | 1518                      | 1518                    | 513,309402     |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H4   | 582,796258    | 975,564171    | 4,572119564     | 1518                      | 0                       | 80             |
| IfcAlignmentHorizontalSegment | LINE           | H5   | 573,004982    | 896,168101    | 4,598470026     | 0                         | 0                       | 154,948149     |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H6   | 555,391605    | 742,224288    | 4,598470026     | 0                         | -1486                   | 90             |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H7   | 544,259467    | 652,919107    | 4,568327586     | -1486                     | -1486                   | 235,958273     |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H8   | 491,993759    | 423,076296    | 4,409399855     | -1486                     | 0                       | 90             |
| IfcAlignmentHorizontalSegment | LINE           | H9   | 463,412608    | 337,73898     | 4,379117218     | 0                         | 0                       | 316,307118     |

## Vertical segments table - AV1

| Entity                      | PredefinedType   | Name | Start Dist Along | Horizontal Length | Start Height | Start Gradient | End Gradient | RadiusOfCurvature |
| --------------------------- | ---------------- | ---- | ---------------- | ----------------- | ------------ | -------------- | ------------ | ----------------- |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V1   | 0,000407982      | 246,4273892       | 108,082846   | 0,012500014    | 0,012500014  | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V2   | 246,4277972      | 95,01277799       | 111,1631917  | 0,012500014    | 0,002997773  | -10000            |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V3   | 341,4405752      | 85,15793083       | 111,899419   | 0,002997773    | 0,002997773  | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V4   | 426,598506       | 183,6600283       | 112,1547031  | 0,002997773    | 0,013202245  | 18000             |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V5   | 610,2585343      | 701,6062339       | 113,6423122  | 0,013202245    | 0,013202245  | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V6   | 1311,864768      | 34,07192867       | 122,9050894  | 0,013202245    | 0,011498258  | -20000            |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V7   | 1345,936697      | 236,655805        | 123,325886   | 0,011498258    | 0,011498258  | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V8   | 1582,592502      | 353,6059896       | 126,0470154  | 0,011498258    | -0,015704899 | -13000            |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V9   | 1936,198491      | 119,9639637       | 125,3034062  | -0,015704899   | -0,015704899 | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V10  | 2056,162455      | 282,6533323       | 123,4193842  | -0,015704899   | -4,51E-15    | 18000             |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V11  | 2338,815787      | 312,8596206       | 121,2        | 2,38704E-12    | 2,38704E-12  | 0                 |

### 

## Horizontal segments table - AH2

| Entity                        | PredefinedType | Name | Start Point X | Start Point Y | Start Direction | Start Radius Of Curvature | End Radius Of Curvature | Segment Length |
| ----------------------------- | -------------- | ---- | ------------- | ------------- | --------------- | ------------------------- | ----------------------- | -------------- |
| IfcAlignmentHorizontalSegment | LINE           | H21  | 276,867419    | 935,549267    | 0,001724622     | 0                         | 0                       | 229,405681     |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H22  | 506,272759    | 935,944905    | 0,00172463      | -110                      | -110                    | 15,594208      |
| IfcAlignmentHorizontalSegment | LINE           | H23  | 521,816666    | 934,8682      | 6,143144395     | 0                         | 0                       | 91,725737      |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H24  | 612,644434    | 922,064789    | 6,143144399     | -110                      | -110                    | 120,80482      |
| IfcAlignmentHorizontalSegment | LINE           | H25  | 701,264387    | 849,049537    | 5,044918731     | 0                         | 0                       | 25,538554      |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H26  | 709,601071    | 824,909996    | 5,044918761     | 110                       | 110                     | 49,633636      |
| IfcAlignmentHorizontalSegment | LINE           | H27  | 735,66497     | 783,164849    | 5,49613363      | 0                         | 0                       | 83,739856      |

## Vertical segments table - AV2

| Entity                      | PredefinedType   | Name | Start Dist Along | Horizontal Length | Start Height | Start Gradient | End Gradient | RadiusOfCurvature |
| --------------------------- | ---------------- | ---- | ---------------- | ----------------- | ------------ | -------------- | ------------ | ----------------- |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V21  | 135,557          | 10,84246946       | 125,687614   | 0,03416131     | 0,03416131   | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V22  | 146,3994695      | 18,11228261       | 126,058007   | 0,03416131     | 0,020212997  | -1300             |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V23  | 164,5117521      | 40,83305808       | 126,5504044  | 0,020212997    | 0,020212997  | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V24  | 205,3448102      | 39,03368133       | 127,3757629  | 0,020212997    | -0,009817512 | -1300             |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V25  | 244,3784915      | 50,17607352       | 127,5786042  | -0,009817512   | -0,009817512 | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V26  | 294,554565       | 11,522986         | 127,086      | 0              | 0            | 0                 |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V27  | 306,077551       | 192,5126892       | 127,086      | -0,003529811   | -0,003529811 | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V28  | 498,5902402      | 15,27528964       | 126,4064666  | -0,003529811   | -0,006584989 | -5000             |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V29  | 513,8655298      | 78,35926585       | 126,3292136  | -0,006584989   | -0,006584989 | 0                 |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V210 | 592,2247957      | 10,41034226       | 125,8132186  | -0,006584989   | 0,00142311   | 1300              |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V211 | 602,6351379      | 13,80735508       | 125,7863506  | 0,00142311     | 0,00142311   | 0                 |

## Spatial (De)Composition table

| **Parent Element** | **Parent Element Type** | **Parent Element Name** | **MinSize** | **MaxSize** | **Child Element** | **Child Element Type** | **Child Element Name** |
| ------------------ | ----------------------- | ----------------------- | ----------- | ----------- | ----------------- | ---------------------- | ---------------------- |
| IfcProject         |                         | A                       | 1           | 1           | IfcSite           |                        | A.a                    |
| IfcSite            |                         | A.a                     | 1           | 1           | IfcRoad           |                        | A.a.1                  |
| IfcSite            |                         | A.a                     | 1           | 1           | IfcRailway        |                        | A.a.2                  |
| IfcRoad            |                         | A.a.1                   | 1           | 1           | IfcFacilityPart   | ROADSEGMENT            | A.a.1.1                |
| IfcRoad            |                         | A.a.1                   | 1           | 1           | IfcFacilityPart   | ROADSEGMENT            | A.a.1.3                |
| IfcRoad            |                         | A.a.1                   | 1           | 1           | IfcFacilityPart   | LEVELCROSSING          | A.a.1.2                |
| IfcRailway         |                         | A.a.2                   | 1           | 1           | IfcFacilityPart   | TRACKSTRUCTUREPART     | A.a.2.1                |
| IfcRailway         |                         | A.a.2                   | 1           | 1           | IfcFacilityPart   | TRACKSTRUCTUREPART     | A.a.2.3                |
| IfcRailway         |                         | A.a.2                   | 1           | 1           | IfcFacilityPart   | LEVELCROSSING          | A.a.2.2                |

**NOTE**:

- when **MinSize** and **MaxSize** have the same value, it means exactly. Example: MinSize=MaxSize=1, means that the Parent Element must aggregates exactly 1 Child Element with that Type (and Name).

# Spatial Containment table

| Spatial Element** | **Spatial Element Type** | **Spatial Element Name** | **MinSize** | **MaxSize** | **Element**          | **Element Type**          | **Element Name** |
| ----------------- | ------------------------ | ------------------------ | ----------- | ----------- | -------------------- | ------------------------- | ---------------- |
| IfcSite           |                          | A                        | 1           | 1           | IfcAlignment         |                           | A.a.A1           |
| IfcSite           |                          | A                        | 1           | 1           | IfcAlignment         |                           | A.a.A2           |
| IfcRoad           |                          | A.a.1                    | 1           | 1           | IfcElementAssembly   | SIGNALASSEMBLY            | A.a.1.SA1        |
| IfcFacilityPart   | LEVELCROSSING            | A.a.2.2                  | 1           | 1           | IfcSensor            | WHEELSENSOR               | A.a.2.2.WS1      |
| fcFacilityPart    | LEVELCROSSING            | A.a.2.2                  | 1           | 1           | IfcSensor            | WHEELSENSOR               | A.a.2.2.WS2      |
| IfcFacilityPart   | LEVELCROSSING            | A.a.2.2                  | 1           | 1           | IfcJunctionBox       | DATA                      | A.a.2.2.JB1      |
| IfcFacilityPart   | LEVELCROSSING            | A.a.2.2                  | 1           | 1           | IfcJunctionBox       | DATA                      | A.a.2.2.JB2      |
| IfcFacilityPart   | LEVELCROSSING            | A.a.2.2                  | 1           | 1           | IfcDiscreteAccessory | RAIL_MECHANICAL_EQUIPMENT | A.a.2.2.SP1      |
| IfcFacilityPart   | LEVELCROSSING            | A.a.2.2                  | 1           | 1           | IfcDiscreteAccessory | RAIL_MECHANICAL_EQUIPMENT | A.a.2.2.SP2      |

**NOTE**:

- when **MaxSize is empty**, it means **unlimited**. Example: MinSize=1; MaxSize=empty, means that the Spatial Element must contain 1 or more elements of the requested type.
- when **MinSize** and **MaxSize** have the same value, it means exactly. Example: MinSize=MaxSize=1, means that the Spatial Element must contain exactly 1 Element with that Type (and Name).

## Element (De)Composition table

| **Assembly Element** | **Assembly Type** | **Assembly Name** | **MinSize** | **MaxSize** | **Element**        | **Element Type** | **Element Name**  |
| -------------------- | ----------------- | ----------------- | ----------- | ----------- | ------------------ | ---------------- | ----------------- |
| IfcElementAssembly   | SIGNALASSEMBLY    | A.a.SA1           | 1           | 1           | IfcDoor            | BOOM_BARRIER     | A.a.1.SA1.D1      |
| IfcElementAssembly   | SIGNALASSEMBLY    | A.a.SA1           | 1           | 1           | IfcFooting         | PAD_FOOTING      | A.a.1.SA1.F1      |
| IfcElementAssembly   | SIGNALASSEMBLY    | A.a.SA1           | 1           | 1           | IfcRailing         | GUARDRAIL        | A.a.1.SA1.R1      |
| IfcElementAssembly   | SIGNALASSEMBLY    | A.a.SA1           | 1           | 1           | IfcElementAssembly | SIGNALASSEMBLY   | A.a.1.SA1.SA2     |
| IfcElementAssembly   | SIGNALASSEMBLY    | A.a.SA1.SA2       | 1           | 1           | IfcPost            | MEMBER           | A.a.1.SA1.SA2.P1  |
| IfcElementAssembly   | SIGNALASSEMBLY    | A.a.SA1.SA2       | 1           | 1           | IfcSignal          | VISUAL           | A.a.1.SA1.SA2.SV1 |
| IfcElementAssembly   | SIGNALASSEMBLY    | A.a.SA1.SA2       | 1           | 1           | IfcSignal          | AUDIO            | A.a.1.SA1.SA2.SA1 |
| IfcElementAssembly   | SIGNALASSEMBLY    | A.a.SA1.SA2       | 1           | 1           | IfcSign            | PICTORAL         | A.a.1.SA1.SA2.SP1 |

**NOTE**:

- when **MinSize** and **MaxSize** have the same value, it means exactly. Example: MinSize=MaxSize=1, means that the Assembly must aggregates exactly 1 Element with that Type (and Name).

## Spatial Interference table

| Spatial Element** | **Spatial Element Type** | Spatial Element Name | Related Spatial Element | Related Spatial Element Type | Related Spatial Element Name | InterferenceType |
| ----------------- | ------------------------ | -------------------- | ----------------------- | ---------------------------- | ---------------------------- | ---------------- |
| IfcFacilityPart   | LEVELCROSSING            | A.a.1.2              | IfcFacilityPart         | LEVELCROSSING                | A.a.2.2                      | Crosses          |

## Product Relative Positioning table

| **Product**          | **Product Type**          | **Product Name** | **Size** | **Positioning Element** | **Positioning Element Type** | **Element Name** |
| -------------------- | ------------------------- | ---------------- | -------- | ----------------------- | ---------------------------- | ---------------- |
| IfcElementAssembly   | SIGNALASSEMBLY            | A.a.1.SA1        | 1        | IfcAlignment            | na                           | A2               |
| IfcSensor            | WHEELSENSOR               | A.a.2.2.WS1      | 1        | IfcAlignment            | na                           | A1               |
| IfcSensor            | WHEELSENSOR               | A.a.2.2.WS2      | 1        | IfcAlignment            | na                           | A1               |
| IfcJunctionBox       | DATA                      | A.a.2.2.JB1      | 1        | IfcAlignment            | na                           | A1               |
| IfcJunctionBox       | DATA                      | A.a.2.2.JB2      | 1        | IfcAlignment            | na                           | A1               |
| IfcDiscreteAccessory | RAIL_MECHANICAL_EQUIPMENT | A.a.2.2.SP1      | 1        | IfcAlignment            | na                           | A1               |
| IfcDiscreteAccessory | RAIL_MECHANICAL_EQUIPMENT | A.a.2.2.SP1      | 1        | IfcAlignment            | na                           | A1               |

## Product Geometric Representation table

| **Product**            | **Product Type**          | **Product Name**  | **Representation Identifier** | **Representation Type** | **Items**                                                    |
| ---------------------- | ------------------------- | ----------------- | ----------------------------- | ----------------------- | ------------------------------------------------------------ |
| IfcAlignment           | na                        | A1                | Axis                          | Curve3D                 | 1 IfcGradientCurve                                           |
| IfcAlignment           | na                        | A2                | Axis                          | Curve3D                 | 1 IfcGradientCurve                                           |
| IfcAlignmentHorizontal | na                        | AH1               | Axis                          | Curve2D                 | 1 IfcCompositeCurve                                          |
| IfcAlignmentHorizontal | na                        | AH2               | Axis                          | Curve2D                 | 1 IfcCompositeCurve                                          |
| IfcAlignmentVertical   | na                        | AH1               | Axis                          | Curve2D                 | 1 IfcGradientCurve                                           |
| IfcAlignmentVertical   | na                        | AH1               | Axis                          | Curve2D                 | 1 IfcGradientCurve                                           |
| IfcDoor                | BOOM_BARRIER              | A.a.1.SA1.D1      | Body                          | MappedRepresentation    | See<br />TOI_Boom_barrier_system_329100<br />GUID: 2ELpFM9EdDVm00000000$u |
| IfcFooting             | PAD_FOOTING               | A.a.1.SA1.F1      | Body                          | MappedRepresentation    | See<br />TOI_Boom_barrier_system_329100<br />GUID: 2ELpFM9EdDVm000000015_ and 2ELpFM9EdDVm00000000$L |
| IfcRailing             | GUARDRAIL                 | A.a.1.SA1.R1      | Body                          | MappedRepresentation    | See<br />TOI_Boom_barrier_system_329100<br />GUID: 2ELpFM9EdDVm00000000$$ |
| IfcPost                | MEMBER                    | A.a.1.SA1.SA2.P1  | Body                          | MeppedRepresentation    | See<br />TOI_Boom_barrier_system_329100<br />GUID: 2ELpFM9EdDVm000000010n |
| IfcSignal              | VISUAL                    | A.a.1.SA1.SA2.SV1 | Body                          | MappedRepresentation    | See<br />TOI_Boom_barrier_system_329100<br />GUID: 2ELpFM9EdDVm00000000$g |
| IfcSignal              | AUDIO                     | A.a.1.SA1.SA2.SA1 | Body                          | MappedRepresentation    | See<br />TOI_Boom_barrier_system_329100<br />GUID: 2ELpFM9EdDVm00000000$n |
| IfcSign                | PICTORAL                  | A.a.1.SA1.SA2.SP1 | Body                          | MappedRepresentation    | See<br />TOI_Boom_barrier_system_329100<br />GUID: 2ELpFM9EdDVm00000000$S |
| IfcSensor              | WHEELSENSOR               | A.a.2.2.WS1       | Body                          | MappedRepresentation    | See<br />TOI_Axle_counter_329161<br />GUID: 0zicwwnhzFqRBHxtsvFBbM |
| IfcSensor              | WHEELSENSOR               | A.a.2.2.WS2       | Body                          | MappedRepresentation    | See<br />TOI_Axle_counter_329161<br />GUID: 3RbW_mdDb0j91BT3FCeIwe |
| IfcJunctionBox         | DATA                      | A.a.2.2.JB1       | Body                          | MappedRepresentation    | See<br />TOI_Cable_junction_box_329161                       |
| IfcJunctionBox         | DATA                      | A.a.2.2.JB2       | Body                          | MappedRepresentation    | See<br />TOI_Cable_junction_box_329161                       |
| IfcDiscreteAccessory   | RAIL_MECHANICAL_EQUIPMENT | A.a.2.2.SP1       | Body                          | MappedRepresentation    | See<br />TOI_Snow_Plough_Protection_329163<br />GUID: 2GAyD8xa8l0m00000001Fo |
| IfcDiscreteAccessory   | RAIL_MECHANICAL_EQUIPMENT | A.a.2.2.SP1       | Body                          | MappedRepresentation    | See<br />TOI_Snow_Plough_Protection_329163<br />GUID: 2GAyD8xa8l0m00000001Fw |

## Product Placement table

| **Product**          | **Product Type**          | **Product Name**  | **Object Placement**                                         | Relative Placement Product | Relative Placement Product Type | Relative Placement Product Name |
| -------------------- | ------------------------- | ----------------- | ------------------------------------------------------------ | -------------------------- | ------------------------------- | ------------------------------- |
| IfcSite              |                           | A.a               | IfcLocalPlacement                                            |                            |                                 |                                 |
| IfcAlignment         |                           | A.a.A1            | IfcLocalPlacement                                            | IfcSite                    |                                 | A.a                             |
| IfcAlignment         |                           | A.a.A2            | IfcLocalPlacement                                            | IfcSite                    |                                 | A.a                             |
| IfcElementAssembly   | SIGNALASSEMBLY            | A.a.1.SA1         | IfcLinearPlacement<br />(A.a.A2.IfcGradientCurve, DistanceAlong=293, No offsets) | IfcAlignment               |                                 | A.a.A2                          |
| IfcDoor              | BOOM_BARRIER              | A.a.1.SA1.D1      | IfcLocalPlacement                                            | IfcElementAssembly         | SIGNALASSEMBLY                  | A.a.1.SA1                       |
| IfcFooting           | PAD_FOOTING               | A.a.1.SA1.F1      | IfcLocalPlacement                                            | IfcElementAssembly         | SIGNALASSEMBLY                  | A.a.1.SA1                       |
| IfcRailing           | GUARDRAIL                 | A.a.1.SA1.R1      | IfcLocalPlacement                                            | IfcElementAssembly         | SIGNALASSEMBLY                  | A.a.1.SA1                       |
| IfcElementAssembly   | SIGNALASSEMBLY            | A.a.1.SA1.SA2     | IfcLocalPlacement                                            | IfcElementAssembly         | SIGNALASSEMBLY                  | A.a.1.SA1                       |
| IfcPost              | MEMBER                    | A.a.1.SA1.SA2.P1  | IfcLocalPlacement                                            | IfcElementAssembly         | SIGNALASSEMBLY                  | A.a.1.SA1.SA2                   |
| IfcSignal            | VISUAL                    | A.a.1.SA1.SA2.SV1 | IfcLocalPlacement                                            | IfcElementAssembly         | SIGNALASSEMBLY                  | A.a.1.SA1.SA2                   |
| IfcSignal            | AUDIO                     | A.a.1.SA1.SA2.SA1 | IfcLocalPlacement                                            | IfcElementAssembly         | SIGNALASSEMBLY                  | A.a.1.SA1.SA2                   |
| IfcSign              | PICTORAL                  | A.a.1.SA1.SA2.SP1 | IfcLocalPlacement                                            | IfcElementAssembly         | SIGNALASSEMBLY                  | A.a.1.SA1.SA2                   |
| IfcSensor            | WHEELSENSOR               | A.a.2.2.WS1       | IfcLinearPlacement<br />(A.a.A1.IfcGradientCurve, DistanceAlong=1746, OffsetLateral=-0.35, OffsetVertical=-0.221) | IfcAlignment               |                                 | A.a.A1                          |
| IfcSensor            | WHEELSENSOR               | A.a.2.2.WS2       | IfcLinearPlacement<br />(A.a.A1.IfcGradientCurve, DistanceAlong=1715, OffsetLateral=-0.35, OffsetVertical=-0.221) | IfcAlignment               |                                 | A.a.A1                          |
| IfcJunctionBox       | DATA                      | A.a.2.2.JB1       | IfcLinearPlacement<br />(A.a.A1.IfcGradientCurve, DistanceAlong=1746, OffsetLateral=-0.95, OffsetVertical=-0.221) | IfcAlignment               |                                 | A.a.A1                          |
| IfcJunctionBox       | DATA                      | A.a.2.2.JB2       | IfcLinearPlacement<br />(A.a.A1.IfcGradientCurve, DistanceAlong=1715, OffsetLateral=-0.95, OffsetVertical=-0.221) | IfcAlignment               |                                 | A.a.A1                          |
| IfcDiscreteAccessory | RAIL_MECHANICAL_EQUIPMENT | A.a.2.2.SP1       | IfcLinearPlacement<br />(A.a.A1.IfcGradientCurve, DistanceAlong=1746, OffsetLateral=0, OffsetVertical=-0.221) | IfcAlignment               |                                 | A.a.A1                          |
| IfcDiscreteAccessory | RAIL_MECHANICAL_EQUIPMENT | A.a.2.2.SP2       | IfcLinearPlacement<br />(A.a.A1.IfcGradientCurve, DistanceAlong=1715, OffsetLateral=0, OffsetVertical=-0.221) | IfcAlignment               |                                 | A.a.A1                          |

# Drawings (Visualisations)

The following Drawings and visualisations describe the test case dataset to be modelled and certified.

![](https://github.com/IFCRail/MVD-Infra-Test-Instructions/blob/Test_Instruction_Track_Structures_Level_Crossing/E2a-TRST/TSLC/Dataset/Figure%201%20-%20situation.png)


# Supporting files

| Filename                                                     | Description                                 |
| ------------------------------------------------------------ | ------------------------------------------- |
| [HorizontalAlignmentParameters](./HorizontalAlignmentParameters.csv) | Parameters for horizontal alignment - track |
| [VerticalAlignmentParameters](./VerticalAlignmentParameters.csv) | Parameters for vertical alignment - track   |
| [RoadHorizontalAlignmentParameters](./RoadHorizontalAlignmentParameters.csv) | Parameters for horizontal alignment - road  |
| [RoadVerticalAlignmentParameters](./RoadVerticalAlignmentParameters.csv) | Parameters for vertical alignment - road    |
| [LandXML - track](./SIIRTO_ORIVESI-HAAPAMAKI_270-273_GK24_KAANNETTY.XML) | LandXML file track alignment                |
| [LandXML - road](./TOI_M14334_0000A.XML)                     | LandXML file road alignment                 |
| [TOI_Axle_counter_329161.dwg](TOI_Axle_counter_329161.dwg)<br />[TOI_Axle_counter_329161.ifc](TOI_Axle_counter_329161.ifc) | dwg and IFC2x3 - axle counters              |
| [TOI_Boom_barrier_system_329100.dwg](TOI_Boom_barrier_system_329100.dwg)<br />[TOI_Boom_barrier_system_329100.ifc](TOI_Boom_barrier_system_329100.ifc) | dwg and IFC2x3 - Boom barrier assembly      |
| [TOI_Cable_junction_box_329161.dwg](TOI_Cable_junction_box_329161.dwg)<br />[TOI_Cable_junction_box_329161.ifc](TOI_Cable_junction_box_329161.ifc) | dwg and IFC2x3 - Junction boxes             |
| [TOI_Snow_Plough_Protection_329163.dwg](TOI_Snow_Plough_Protection_329163.dwg)<br />[TOI_Snow_Plough_Protection_329163.ifc](TOI_Snow_Plough_Protection_329163.ifc) | dwg and IFC2x3 - Snow plough protection     |
