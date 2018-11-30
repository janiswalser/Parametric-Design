# Create Objects

MEL provide for modeling objects a lot of different attributes. Mostly the Syntax of the attribute commands can be written as Long name (-radius) or short name/flag (-r) and the value you choose.	

## Basic Models (Nurbs)

### Sphere
```
// Create sphere with radius 10
sphere -r 10;

// Create half sphere
sphere -ssw 0 -esw 180
```

### Cylinder
```
cylinder; // create one with default attributes 
cylinder -r 5 -axis 1 1 1 -pivot 0 0 1 -ssw 0deg -esw 90deg; // create one with your own settings
```

### Cone
```
cone; // create one with default attributes 
cone -ch true -radius 10 -hr 3; // create one with your own settings
```

## Basic Models (Polygons)

### polyCube
Flags:
-w (=width)
-h (=height)
-d (=depth)
-n (=name)

```
// 10 units height rectangular box called MyCube
polyCube -w 5 -h 10 -d 5 –n "MyCube";
```

### polySphere
This command creates a sphere, with 10 subdivisions in the X direction, and 15 subdivisions in the Y direction. 
```
polySphere -sx 10 -sy 15 -r 20;
```

### polyCylinder
hint → -subdivisionsX(-sx), -subdivisionsY(-sy), -subdivisionsZ(-sz) 
```
polyCylinder -sx 10 -sy 15 -sz 5 -h 20;
```

![Loop](assets/Loop.png)


# Transform objects

## Move

Flags
-a (=absolute default)

-r (=relative)

-x (=x direction)

-y (=y direction)

-z (=z direction)

-xyz (all directions default)

Example
```
move –r –x 10.;
// move relative from its previous position 10 in x
```

## Rotate

-a (= absolute operation)

-r (= relative to the object's current position

-cp (= pivot be the center of the bounding box of all objects

-ocp (=pivot be the center of the bounding box of each object

-p (= Define the pivot point for the transformation)

Example
```
polyCube –n "MyCube";
rotate -pivot 1 0 0 0 180deg 0 cube1;
// rotate the cube 180 degrees about its local space Y axis
// centered at the rotate pivot point 1 0 0.
```

## Scale

-a (=absolute default)

-r (=relative)

-cp (= pivot be the center of the bounding box of all objects

-ocp (=pivot be the center of the bounding box of each object

-p (= Define the pivot point for the transformation)

Example
```
sphere;
scale -p 1 0 0 3 3 3; //triple the size about p(1,0,0)
```

## Example
```
for ($i=0; $i<10; $i++){
  polyCube -w 0.5 -h 0.5 -d 4; // create a polyCube
  
  move (2*$i) 0 0; // move it 
  float $factor = $i/9.; // make a variable factor to be between 0.1 and 1
  scale -ocp 1 1 $factor; // scale in the z direction
};
```
