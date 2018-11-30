![](assets/gui.png)

# GUI

You can create your own tools! Create a window and input fields, to boost your process 

```
// delete window when it exists
if ( `window -exists MyWindow` ) {
    deleteUI MyWindow; 
}

// Create a window 
window -t "Create Cubes" MyWindow;
 
//Define Layout
columnLayout MyMainCol;
intFieldGrp -l "Number" numberOfCubes;
button -l "Create" -command "createCubeButtonAction()";
 
showWindow MyWindow;
 
 
global proc createCubeButtonAction() {
  // read the control for the number of cubes to be created
  int $num = `intFieldGrp -q -v1 numberOfCubes`;
  for ($i=0;$i<$num;$i++ ) {
      polyCube;
      move (2*$i) 0 0;
  }
}
```
