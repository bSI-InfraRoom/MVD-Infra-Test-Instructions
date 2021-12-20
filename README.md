# MVD Infra Test Instructions

This repository is to submit, review & store Test Cases & Instructions defined for IFC4.3 Alignment Based Reference View Certification, and is developed as part of the IFC Infrastructure MVD Project.

| MVD Code        | IFC Version | MVD Name                      | Exchanges |
|-----------------|-------------|-------------------------------|-----------|
| **IFC4x3_AbRV** | IFC4.3      |Alignment Based Reference View | 13        |

## Contribute
- Use the [template](./docs/test-instruction-template.md) and follow the [instructions](./docs/instructions.md).
    - An example is provided [here](./E2.1-Earthworks-Fill-01).
- [Fork](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/working-with-forks) this repository. 
Develop the test Case/Instruction. 
- Create a [pull request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork) to the main repository.
    - For a brief summary of `git` process, see [here](https://github.com/tumcms/Open-Infra-Platform/blob/development/Documentation/markdown/GitProcess.md). There are also a lot of online tutorials available.

## Structure
The Repository is divided into a set of Information Exchanges numbered Ex . each exchange has a number of test cases within it to forfil and test the needed functionality of each exchange definition. Current identified Exchanges are as follows.
 

| Ex Code | Exchange Name                               | Cases & Info       |
|---------|---------------------------------------------|--------------------|
| E1      | Alignment Reference Exchange                | [ALRF](./E1-ALRF)  |
| E1a     | Alignment Reference Superelevation Exchange | [ARSE](./E1a-ARSE) |
| E1b     | Alignment Reference Cant Exchange           | [ALRC](./E1a-ARCT) |
| E2      | Aggregate Structures Exchange               | [AGST](./E2-AGST)  |
| E2a     | Track Aggregate Structures Exchange         | [TRAS](./E2a-TRAS) |
| E3      | Earthworks Exchange                         | [EWKS](./E3-EWKS)  |
| E4      | Bridge Structural Exchange                  | [BRST](./E4-BRST)  |
| E5      | Signalling Exchange                         | [SIGN](./E5-SIGN)  |
| E6      | Energy Exchange (Railway)                   | [ENGY](./E6-ENGY)  |
| E7      | Geotechnics Exchange                        | [GEOT](./E7-GEOT)  |
| E8      | Telecommunications Exchange                 | [TECO](./E8-TECO)  |
| E9      | Drainage Exchange                           | [DNGE](./E9-DNGE)  |
| E10     | Maritime Elements Exchange                  | [MTME](./E10-MTME) |


## FAQ

See [FAQ](./docs/faq.md).
