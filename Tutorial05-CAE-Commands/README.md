
# CAE Scripting Repository

This directory serves as the hub for CAE related scripting involving cross functional software and CAE disciplines.

## MAC Commands

This is a MATLAB script for exporting modal shapes from ANSYS to MATLAB.

**To use it:**

1. Copy and paste the script into a new MATLAB file and save it with a .m extension.
2. Open ANSYS and load the modal analysis results that you want to export.
3. In MATLAB, run the script.

**The script will:**

1. Prompt you to enter the following information:
    * The path where you want to save the exported data.
    * The name of the exported file.
    * The name of the named selection containing the nodes that you want to export.
2. Export the modal shapes to a text file in the specified location.
3. Export additional information about the nodes and modes to a separate text file.

**The exported data can then be used in MATLAB for further analysis or visualization.**

**Here is a breakdown of the script:**

**Lines 1-3:** Define the file format and encoding.

**Lines 5-7:** Define the variables that will be used in the script.

**Lines 9-13:** Get the number of nodes and modes from ANSYS.

**Lines 15-17:** Prompt the user to enter the path and name of the exported files.

**Lines 19-21:** Get the name of the named selection containing the nodes that the user wants to export.

**Lines 23-25:** Select the nodes in the named selection.

**Lines 27-32:** Create a matrix to store the modal shapes.

**Lines 34-44:** Loop over the modes and nodes:
    * Get the nodal coordinates and modal amplitudes from ANSYS.
    * Write the nodal coordinates and modal amplitudes to the matrix.

**Lines 46-48:** Write the modal shape matrix to a text file.

**Lines 50-54:** Create an array to store information about the nodes and modes.

**Lines 56-58:** Write the information array to a text file.

**Lines 60-62:** Close the ANSYS database.

**Lines 64-67:** Prompt the user to open the exported files in MATLAB.

**Note:** The script is currently configured to export modal shapes for frequencies up to 2000Hz. To export modal shapes for higher frequencies, change the value of `F5` in the line `(F5.0,E16.8)`.


## Front_schraubverbindung_add.dat

The PERMAS DAT file is a finite element analysis (FEA) input file for the PERMAS software. It is used to model a bolted connection with pre-tensioned bolts.

The input file contains the following sections:

* **$STRUCTURE:** This section defines the nodes and elements of the structure.
* **$SYSTEM:** This section defines the system type (modal in this case).
* **$CONSTRAINTS:** This section defines the boundary conditions.
* **$LOADING:** This section defines the loads that are applied to the structure.

To use the input file, you would first need to import it into the PERMAS software. Once the input file is imported, you can solve the model to obtain the results.

Here is a brief explanation of the different sections of the input file:

**$STRUCTURE:**

The `$STRUCTURE` section defines the nodes and elements of the structure. In this case, the structure is a bolted connection with four pre-tensioned bolts.

The `$PRELOAD THREAD` command is used to pre-tension the bolts. The `SURFACE to SURFNODE` option specifies that the pre-tension is applied between a surface and a node. The `PREDIR` option specifies the pre-tension direction in the global coordinate system. The `ALPHA` option specifies the angle of the pre-tension direction relative to the surface normal. The `CIRCUM` option specifies that the pre-tension is applied circumferentially around the bolt.

**$SYSTEM:**

The `$SYSTEM` section defines the system type. In this case, the system type is modal, which stands for modal analysis.

**$CONSTRAINTS:**

The `$CONSTRAINTS` section defines the boundary conditions. In this case, there are no boundary conditions.

**$LOADING:**

The `$LOADING` section defines the loads that are applied to the structure. In this case, the only load is the pre-tension load.

The `$PRELOAD` command is used to apply the pre-tension load. The `LPAT` option specifies the load pattern. The `PREDIR` option specifies the pre-tension direction in the global coordinate system.

**$EXIT COMPONENT:**

The `$EXIT COMPONENT` command is used to exit the component definition.

**$FIN:**

The `$FIN` command is used to end the PERMAS input deck.

## LoadHistory.dat

This LoadHistory.dat PERMAS DAT file is for modeling a bolted connection with pre-tensioned bolts and contact between surfaces. It contains the following sections:

* **$STRUCTURE:** This section defines the nodes and elements of the structure.
* **$SYSTEM:** This section defines the system type (modal in this case).
* **$LOADING:** This section defines the loads that are applied to the structure, including the pre-tension load and contact loads.

**$STRUCTURE:**

The `$STRUCTURE` section defines the nodes and elements of the structure. In this case, the structure is a bolted connection with four pre-tensioned bolts and contact between surfaces.

The `$PRETENSION THREAD` command is used to pre-tension the bolts. The `SURFACE to SURFNODE` option specifies that the pre-tension is applied between a surface and a node. The `PREDIR` option specifies the pre-tension direction in the global coordinate system. The `ALPHA` option specifies the angle of the pre-tension direction relative to the surface normal. The `CIRCUM` option specifies that the pre-tension is applied circumferentially around the bolt.

**$SYSTEM:**

The `$SYSTEM` section defines the system type. In this case, the system type is modal, which stands for modal analysis.

**$LOADING:**

The `$LOADING` section defines the loads that are applied to the structure, including the pre-tension load and contact loads.

The `$PRETENSION LOAD` command is used to apply the pre-tension load. The `LPAT` option specifies the load pattern. The `PREDIR` option specifies the pre-tension direction in the global coordinate system.

The `$CONTACT LOAD` command is used to apply contact loads. The `LPAT` option specifies the load pattern. The `GAPWIDTH` option specifies the gap width between the surfaces. The `FRICTION` option specifies the friction coefficient between the surfaces.

**$NLLOAD:**

The `$NLLOAD` command is used to define a nonlinear load table. In this case, the load table specifies that the pre-tension load and contact loads are ramped up linearly over four load steps.

**$EXIT COMPONENT:**

The `$EXIT COMPONENT` command is used to exit the component definition.

**$ENTER MATERIAL:**

The `$ENTER MATERIAL` command is used to enter the material definition section.

**$EXIT MATERIAL:**

The `$EXIT MATERIAL` command is used to exit the material definition section.

**$FIN:**

The `$FIN` command is used to end the PERMAS input deck.

**Notes:**

* The contact loads in this input file are defined using the `$CONTACT LOAD` command with the `FRICTION` option set to `COULOMB`. This means that the contact loads are calculated using Coulomb friction.
* The nonlinear load table in this input file is defined using the `$NLLOAD` command with the `DOFTYPE` option set to `DISP`. This means that the pre-tension load and contact loads are ramped up linearly over four load steps in terms of displacements.
* The material definitions for the structure are not included in the input file. The user must define the material properties in the PERMAS software before solving the model.