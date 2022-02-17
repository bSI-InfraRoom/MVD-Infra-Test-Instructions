# Alignment Reference Super Elevation Exchange

| Exhange Code        | Abbreviation | Exchange Name                                | Test Cases |
|---------------------|--------------|----------------------------------------------|------------|
| **IFC4x3_AbRV-E1a** | ARSE         | Alignment Reference Super Elevation Exchange | 2          |

Exchange Lead: @larswik

## Summary

TBC

...The Alignment Reference Super Elevation Exchange is an extension *superset* of the Alignment Reference Exchange ([IFC4x3_AbRV-E1](../E1-ALRF)). 

### Scope

The Alignment Reference Super Elevation Exchange is an extension *superset* of the Alignment Reference Exchange ([IFC4x3_AbRV-E1](../E1-ALRF)). Therefore the scope of this exchange includes the scope and tests outlined by the Alignment Reference Exchange.

TBC

## Test Instructions

| TI Code                                | Test Instruction Title                                       |
| -------------------------------------- | ------------------------------------------------------------ |
| [**IFC4x3_AbRV-E1a-ALIN01**](./ALIN01) | Alignment layout <br/>Horizontal: Line, Circular arc, Clothoid<br/>Vertical: Line, Circular arc (including "S") |
| [**IFC4x3_AbRV-E1a-ALIN02**](./ALIN02) | Alignment layout <br/>Horizontal: Line, Circular arc, Clothoid<br/>Vertical: Line, Parabolic arc (including "S") |
| [**IFC4x3_AbRV-E1a-ALIN03**](./ALIN03) | Alignment layout<br/>Horizontal: Line, Circular Arc<br/>Vertical: Line, Circular Arc<br/>Geometry: IfcPolyline (2d) |
| [**IFC4x3_AbRV-E1a-ALIN04**](./ALIN04) | Alignment layout : See ALIN01<br/>Geometry: IfcCompositeCurve, IfcGradientCurve |
| [**IFC4x3_AbRV-E1a-ALIN05**](./ALIN05) | Alignment layout: See ALIN02<br/>Geometry: IfcCompositeCurve, IfcGradientCurve |
| [**IFC4x3_AbRV-E1a-ALIN06**](./ALIN06) | Alignment layout: See ALIN03<br/>Geometry: IfcCompositeCurve, IfcGradientCurve |
| [**IFC4x3_AbRV-E1a-ALSE01**](./ALSE01) | Alignment Superelevation<br />Alignment: See ALIN06          |
| [**IFC4x3_AbRV-E1a-ALSE02**](./ALSE02) | Alignment Superelevation plus Width<br />Alignment: See ALIN06 |