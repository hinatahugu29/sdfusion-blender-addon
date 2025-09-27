# How to use
We will introduce the basic flow and the role and function of each button.

My personal favorite panel layouts.

- 3D Viewport
- Outliner
- Properties
- Asset Browser
 ![Image_2](images/スクリーンショット 2025-09-27 213923.png)

## Find SDFusion on N-panel.
Since it can get buried among various add-ons, finding it is the starting point.
 ![Image_2](images/SDFusion8P.png)

## Select the object, then click Reset Booleans & Collections.
![Image_2](images/スクリーンショット 2025-09-27 215101.png)

- Outliner: Several collections added
    - SDFusion Cutters: Storage for Boolean processing objects
    - SDFusion_Working: Storage for objects currently being worked on
    - ADD-x: Storage for objects used for addition
    - SUB-x: Storage for objects used for subtraction
    - SDFusion Pool: Storage for temporarily removing objects from processing

- Properties: Several modifiers are stacked
    - Boolean
    - Remesh
    - weld
    - Bevel
    - Smooth

This add-on primarily uses a workflow based on stacking existing modifiers.

## Trying to Make a Hole in the Cube Adding Objects and Boolean Subtraction
1. Add a cylinder: I have only added items so far and have not performed any other operations.
![Image_2](images/スクリーンショット 2025-09-27 220334.png)

2. Change the Sub button click and display to a wireframe.
![Image_2](images/スクリーンショット 2025-09-27 220528.png)
At this stage, nothing is finalized, so moving the cylindrical wireframe will shift the hole's position.
![Image_2](images/スクリーンショット 2025-09-27 220631.png)

3. Let's add a small cube.: 
    - Add a cube
    - Adjust position and scale
    - Click the Add button in the N-Panel
    - Change the display to wireframe

![Image_2](images/スクリーンショット 2025-09-27 220932.png)
4. Let's change the cube layer from ADD-1 to ADD-2.
![Image_2](images/スクリーンショット 2025-09-27 221026.png)Thus, this add-on aims to display the stack of Boolean modifiers as layers, making it easier to process additions and subtractions hierarchically.<br><br>
5. Alright, let's make some visual adjustments.

From here, you can branch off into several options.




<span style="font-size: 20px;">Next : [Install](installation.md)</span>