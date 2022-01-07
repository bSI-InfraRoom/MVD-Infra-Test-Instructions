# Track Aggregate Structures Exchange

| Exchange Code       | Abbreviation | Exchange Name                       | Test Cases |
|---------------------|--------------|-------------------------------------|------------|
| **IFC4x3_AbRV-E2a** | TRAS         | Track Aggregate Structures Exchange | 9          |

Exchange Lead: @AlexBrad1eyCT

## Summary

TBC

...The Track Structures Exchange is an extension *superset* of the Aggregate Structures Exchange ([IFC4x3_AbRV-E2a](../E2-AGST))...

### Scope

The Track Structures Exchange is an extension *superset* of the Aggregate Structures Exchange ([IFC4x3_AbRV-E2a](../E2-AGST)). Therefore the scope of this exchange includes the scope and tests outlined by the Aggregate Structures Exchange.

TBC

## Test Instructions
The list below represent the scope of the Integration Test that shall be passed to fulfil the Track Aggregate Structures Exchange.

Some tests are just referenced (hence reused entirely) from other Exchanges.

| TI Code                            | Test Instruction Title                 | Reused | Dependencies            |
|------------------------------------|----------------------------------------|:------:|-------------------------|
| [**IFC4x3_AbRV-E??-PJSU**](./PJSU) | Project Setup (general)                | ?      | none                    |
| [**IFC4x3_AbRV-E??-GLOB**](./GLOB) | (RFI) Global Positioning RFI dataset   | ?      | PJSU                    |
| [**IFC4x3_AbRV-E1-TANC**](./TANC)  | (RFI) Two alignments without cant      | X      | GLOB                    |
| [**IFC4x3_AbRV-E1b-TWAL**](./TWAL) | (RFI) Two alignments with cant         | X      | GLOB, TANC              |
| [**IFC4x3_AbRV-E1-ALLP**](./ALLP)  | (RFI) Mileage for two alignments       | X      | TWAL                    |
| [**IFC4x3_AbRV-E2a-TKST**](./TKST) | (RFI) Track structure for single track |        | TWAL                    |
| [**IFC4x3_AbRV-E2a-TNTP**](./TNTP) | (RFI) Turnout panel between two tracks |        | TWAL                    |
| [**IFC4x3_AbRV-E2a-OJGR**](./OJGR) | (RFI) Group objects                    |        | TWAL, TKST, TNTP        |
| [**IFC4x3_AbRV-E2a-CLAS**](./CLAS) | (RFI) Classify objects                 |        | TWAL, TKST, TNTP        |
| [**IFC4x3_AbRV-E2a-PROP**](./PROP) | (RFI) Add properties                   |        | TWAL, TKST, TNTP, OJGR  |
| [**IFC4x3_AbRV-E2a-LCSS**](./LCSS) | Level crossing structure               |        | another alignment test? |

