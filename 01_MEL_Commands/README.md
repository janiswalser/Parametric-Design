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


