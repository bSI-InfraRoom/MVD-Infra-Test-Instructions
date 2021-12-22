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

| TI Code                            | Test Instruction Title   | Reused | Dependencies           |
|------------------------------------|--------------------------|:------:|------------------------|
| [**IFC4x3_AbRV-E2a-GLOB**](./GLOB) | Global Positioning       | ?      | none                   |
| [**IFC4x3_AbRV-E1b-TWAL**](./TWAL) | Create two alignment     | X      | GLOB                   |
| [**IFC4x3_AbRV-E1-ALLP**](./ALLP)  | Add alignment mileage    | X      | TWAL                   |
| [**IFC4x3_AbRV-E2a-TKST**](./TKST) | Create track structure   |        | TWAL                   |
| [**IFC4x3_AbRV-E2a-TNTP**](./TNTP) | Add turnout panel        |        | TWAL                   |
| [**IFC4x3_AbRV-E2a-OJGR**](./OJGR) | Group objects            |        | TWAL, TKST, TNTP       |
| [**IFC4x3_AbRV-E2a-CLAS**](./CLAS) | Classify objects         |        | TWAL, TKST, TNTP       |
| [**IFC4x3_AbRV-E2a-PROP**](./PROP) | Add properties           |        | TWAL, TKST, TNTP, OJGR |
| [**IFC4x3_AbRV-E2a-LCSS**](./LCSS) | Level crossing structure |        | another alignment test?|
