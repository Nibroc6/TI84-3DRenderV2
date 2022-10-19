# TI84_3DRenderV2
A simple 3D wireframe render engine for the TI 84+


# Installation
To use this code, you will need either a TI 84 of some sort or a TI 84 simulator such as Wabbitemu (http://wabbitemu.org/)
If you have a phisical TI 84, you will need the TI connect app and cord to send files to your calculator.
Step 1: Download and unzip files from repo. (click "Code" icon near upper right hand corner of this page and download zip)
Step 2: Send files to calculator. If you don't know how to do this, try this guide: https://www.dummies.com/article/technology/electronics/graphing-calculators/how-to-transfer-files-between-the-ti-84-plus-and-pcs-160735/

# Initialization
To set your calculator's graphing settings to optimaly diplay models, as well as loading a wireframe into memory, run the "LOADM" program. (prgm > [use arrow keys to scroll to LOADM] > enter) When prompted for model id, press 1, then press enter, unless you have loaded your own model, in which case you may want to enter its model id. At the next prompt (RUN? (1=Y)), enter 1 to immediately render the model after initialization is compleat or 0 if you don't want to. The XY SPEED prompt sets the x/y movement speed of the model. (Reccomended value: 2) ROTATION SPEED sets the interval by which the model will be rotated by the controls. (Recomended value: 15)

# Running the Render Engine
To run the render engine after initialization, run the "TDR" program. (prgm > [use arrow keys to scroll to TDR] > enter) The MODE prompt sets viewing style. (0 = regular, 1 = orthagonal [no FOV warping])

# Rotation and Movment Control
To move the model, use the arrow keys. 7 and 9 control roll, 8 and 2 control pitch, and 4 and 6 control yaw. To exit the program, press 5.


# Model Format
To display a model with this engine, it needs to be in the following format:


{Edge1 X1, Edge2 X1, ...} -> list

{Edge1 Y1, Edge2 Y1, ...} -> list

{Edge1 Z1, Edge2 Z1, ...} -> list

{Edge1 X2, Edge2 X2, ...} -> list

{Edge1 Y2, Edge2 Y2, ...} -> list

{Edge1 Z2, Edge2 Z2, ...} -> list


You will also have to change the code in LOADM. Add the following to this line:
Disp "ID: NAME:","1   HI","[id - some number]   [Name of your model]"
Then, add the following lines right before "If P":


If A=[id that you put in earlier]

Then

	[first list]->L1
	
	[second list]->L2
	
	[third list]->L3
	
	[fourth list]->L4
	
	[fifth list]->L5
	
	[sixth]->L6
	
End
