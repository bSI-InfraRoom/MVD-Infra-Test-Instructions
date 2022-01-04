# Track Aggregate Structures Exchange

| Exchange Code       | Abbreviation | Exchange Name                       | Test Cases |
|---------------------|--------------|-------------------------------------|------------|
| **IFC4x3_AbRV-E2a** | TRAS         | Track Aggregate Structures Exchange | 9          |

Exchange Lead: TBD

## Summary

TBC

### Scope

TBC

## Test Instructions
The list below represent the scope of the Integration Test that shall be passed to fulfil the Track Aggregate Structures Exchange.

Some tests are just referenced (hence reused entirely) from other Exchanges.

| TI Code                            | Test Instruction Title                 | Reused | Dependencies            |
|------------------------------------|----------------------------------------|:------:|-------------------------|
| [**IFC4x3_AbRV-E??-GLOB**](./GLOB) | (RFI) Global Positioning RFI dataset   | ?      | none                    |
| [**IFC4x3_AbRV-E1b-TWAL**](./TWAL) | (RFI) Two alignments with cant         | X      | GLOB                    |
| [**IFC4x3_AbRV-E1-ALLP**](./ALLP)  | (RFI) Mileage for two alignments       | X      | TWAL                    |
| [**IFC4x3_AbRV-E2a-TKST**](./TKST) | (RFI) Track structure for single track |        | TWAL                    |
| [**IFC4x3_AbRV-E2a-TNTP**](./TNTP) | (RFI) Turnout panel between two tracks |        | TWAL                    |
| [**IFC4x3_AbRV-E2a-OJGR**](./OJGR) | (RFI) Group objects                    |        | TWAL, TKST, TNTP        |
| [**IFC4x3_AbRV-E2a-CLAS**](./CLAS) | (RFI) Classify objects                 |        | TWAL, TKST, TNTP        |
| [**IFC4x3_AbRV-E2a-PROP**](./PROP) | (RFI) Add properties                   |        | TWAL, TKST, TNTP, OJGR  |
| [**IFC4x3_AbRV-E2a-LCSS**](./LCSS) | Level crossing structure               |        | another alignment test? |

