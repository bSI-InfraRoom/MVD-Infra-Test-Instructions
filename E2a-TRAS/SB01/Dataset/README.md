# Dataset description

| Documentation Code   | Test Title                                 | Exchange Code | Test Code | Author          | Data Owner | Version | Date       |
|----------------------|--------------------------------------------|---------------|-----------| ----------------|------------|---------|------------|
| IFC4.3AbRV_E2a_SB01  | (RFI) Track sub-structure for single track | E2a (TRAS)    | SB01      | Evandro Alfieri | RFI        | 1.0     | DD.MM.YYYY |

## Model Dataset

This test case utilises the following dataset.

| Filename                                     | Type (format) | Description                                                       |
|----------------------------------------------|---------------|-------------------------------------------------------------------|
| [TrackCrossSection](./TrackCrossSection.png) | drawing (png) | [Track cross section](#Track-Cross-Section) to be used as example |



## Track Cross Section

The image below shows the different layers of the track sub-structure (red in picture) to be represented. (For the track super-structure part, green in picture below, refer to test case **IFC4.3AbRV_E2a_SP01**.)

The *Top soil* covering can be ignored for this test, so the only elements to be represented are (from bottom up):

- the earthwork fill (thickness not further specified, as long as the complete sub-structure has a slope of 3/2, as showed in figure)
- the foundation course (thickness: 30 cm)
- the junction layer (thickness: 12 cm)

Note that layers are NOT flat, but have a 3% slope starting from the central axis of the section (dotted line), going outward  

<img src="./TrackCrossSection_snippet.png" height="300"/>


### Straight and curved parts
The sub-structure part (red) is not influenced by cant. So, it is expected to have the same representation both in straight parts and in curves. The test **IFC4.3AbRV_E2a_SP01**, dealing with super-structure (green), will show the changing behaviour of ballast and sleeper in curve.


<img src="./TrackCrossSection.png" height="500"/>