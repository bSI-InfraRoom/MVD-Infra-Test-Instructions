## Variations
The following occurrence variations need to be checked and certified in relation to the targeted entities and concept templates:

- IfcRail.RAIL - *requires Body AdvancedSweptSolid Geometry*
- IfcTrackElement.SLEEPER - *requires Mapped Geometry with Type Body Tessallated Geometry*
- IfcRail.CHECKRAIL - *requies Body Tessallation Geometry*
- IfcRail.BLADE - *requires Body Tessallation Geometry*
- IfcTrackElement.FROG - *requies Body Tessallation Geometry*
- IfcMechanicalFastener.RAILFASTENING - *requires Mapped Geometry with Type Body Tessallated Geometry*
- IfcMechanicalFastener.RAILJOINT - *requires Mapped Geometry with Type Body Tessallated Geometry*

## Model Dataset
This test case utilises the attached dataset documented by the following drawings and data schedule. 

*This is a later step that involved the detailed documentation of the certification dataset (model)*

A track turnout panel is modelled as an instance of IfcElementAssembly with PredefinedType set to TURNOUTPANEL.
It is decomposed by elements including IfcRail.RAIL, IfcTrackElement.SLEEPER, IfcRail.CHECKRAIL, IfcRail.BLADE, IfcTrackElement.FROG, IfcMechnicalFastener.RAILFASTENING, IfcMechnicalFastener.RAILJOINT.
All the placement of these elements should be based on the placement of the turnout panel, and the turnout panel as an assembly is placed based on the alignment.
It is required to exchange start and end stationing of the turnout panel in the IFC file using IfcReferent.
The detailed structure of placement is specified as follows.

![alt text](Turnout_Placement.png)
*Fig. 1 Placement of track turnout panel*
![alt text](Turnout_Element_Placement.png)
*Fig. 2 Placement of elements in track turnout panel*

It is required to define Product Type Geometry for IfcTrackElement.SLEEPER, IfcMechnicalFastener.RAILFASTENING and IfcMechnicalFastener.RAILJOINT.
- The geometry of IfcMechnicalFastener.RAILFASTENING and IfcMechnicalFastener.RAILJOINT as boxes that are placed according to the drawing.
- The geometry of IfcTrackElement.SLEEPER can be simplified and placed according to the drawing in Fig. 6.



## Drawings (Visualisations)
The following Drawings and visualisations describe the test case dataset to be modelled and certified.
Elements in the turnout panel should be classifed as shown in Fig. 4. 

![alt text](trackturnout_schematic.png)
*Fig. 3 Alignment of turnout panel*
![alt text](trackturnout.png)
*Fig. 4 Turnout panel drawing and element types*

The profile of rail (IfcRail.RAIL) should use the following drawing as reference.
![alt text](RailProfile60UIC.jpg)
*Fig. 5 Rail profile*

The sleeper and its simplified version
![alt text](Sleeper.png)
*Fig. 6 Sleeper and its relation to rails and the simplified version*

## Supporting files

| Filename                          | Description                               |
|-----------------------------------|-------------------------------------------|
| *FS60UNI_R.250_TG.0.092.svg*                        | *Drawing of track turnout panel*                       |
