![](assets/curves.png)

![](assets/pattern.png)
![](assets/nums.png)

# Curves & Patterns
Generative created curves with ```%```

```
$MyCurve1 = `curve -d 1 -p 0 0 0 -p 0 0 0 -name "MyCurve1" `;
$MyCurve2 = `curve -d 1 -p 0 0 0 -p 0 0 0 -name "MyCurve2" `;
$MyCurve3 = `curve -d 1 -p 0 0 0 -p 0 0 0 -name "MyCurve3" `;
$MyCurve4 = `curve -d 1 -p 0 0 0 -p 0 0 0 -name "MyCurve4" `;
$MyCurve5 = `curve -d 1 -p 0 0 0 -p 0 0 0 -name "MyCurve5" `;
$MyCurve6 = `curve -d 1 -p 0 0 0 -p 0 0 0 -name "MyCurve6" `;
$MyCurve7 = `curve -d 1 -p 0 0 0 -p 0 0 0 -name "MyCurve7" `;
$MyCurve8 = `curve -d 1 -p 0 0 0 -p 0 0 0 -name "MyCurve8" `;


for($i=2; $i<27; $i++) {
	//MyCurve1
	$x = 2*(($i)/2) - 3*(($i)/6) -2;	
	$y = 2 - (($i+3)/2)%3;
	print $x;
	$z = 0;
	curve -a -p $x $y $z MyCurve1;
}


for($i=0; $i<25; $i++) {
	//MyCurve2
	$x = $i/2;
	$y = (($i+5)/2)%2 + (($i+5)%8)/6   -3;
	$z = 0;
	curve -a -p $x $y $z MyCurve2;
}	

for($i=0; $i<17; $i++) {
	//MyCurve3
	$x = ($i/2) + (($i + 2)/4);
	$y = (($i + 1)/2)%2 * 2      -6;
	$z = 0;
	curve -a -p $x $y $z MyCurve3;
}

for($i=0; $i<25; $i++) {
	//MyCurve4
	$x = ($i/2);
	$y = ( (((($i+1)/2) % 4) - (((($i+1)%8)/6) * 2)) )   -9;
	$z = 0;
	curve -a -p $x $y $z MyCurve4;
}

for($i=0; $i<25; $i++) {
	//MyCurve5
	$x = ($i/2); 
	$y = ((($i+1)/2))%3    -12 ;
	$z = 0;
	curve -a -p $x $y $z MyCurve5;
}

for($i=-1; $i<25; $i++) {
	//MyCurve6
	$x = (($i)/4) * 2 + (($i+2)/2)%2;
	$y = ((($i+1)/2) % 4) - (((($i+1)%8)/6) * 2)   -15;
	$z = 0;
	curve -a -p $x $y $z MyCurve6;
}

for($i=-1; $i<26; $i++) {
	//MyCurve7
	$x = ($i/2);
	$y = ((($i+1)/2)%2)*2   -18;
	$z = 0;
	$z = 0;
	curve -a -p $x $y $z MyCurve7;
}
```
# Simple Curve
The curve command creates a new curve from a list of control vertices (CVs).

-d/-degree The degree of the new curve. Default is 3.

-a/-append Appends point(s) to the end of an existing curve.

-p/-point dist dist dist The x, y, z position of a point.

```curve –d 1 -p 0 0 0 -p 0 1 0 -p 1 1 0 -p 1 0 0 –name "MyCurve1";``` 

```curve -d 2 -p 0 0 0 -p 1 0 0 -p 1 1 0 -p 0 1 0 -n “MyCurve1";``` // -d 2 → rounded curve

``` 
curve –a –p 0 0 0 MyCurve1;
closeCurve MyCurve1;
``` 
→ closed curve


# Extrude along a curve
![extrude](assets/extrude.png)

```
$MyCurve1 = `curve -d 1 -p 0 0 0 -p 0 0 0 -name "MyCurve1" `;


for($i=2; $i<27; $i++) {
	//MyCurve1
	$x = 2*(($i)/2) - 3*(($i)/6) -2;	
	$y = 2 - (($i+3)/2)%3;
	print $x;
	$z = 0;
	curve -a -p $x $y $z MyCurve1;
}


$circleName1 = "MyCircle1";
circle -name $circleName1;
scale .3 .3 .3;
rotate 90 0 0 ;

eval("extrude -rn false -po 0 -et 2 -ucp 1 -fpt 1 -upn 1 -rotation 0 -scale 1 -rsp 1 " +
$circleName1 + " " + $MyCurve1);
```


