
# Useful Snippets 2.0





## Number Patterns

Examples
```
for($i=0; $i<20; $i++){
$x = $i/2;
polyCube;
move ($i*2) 0 0;
scale 1 $x 1;
};
//00112233445566778899
```

```
for($i=0; $i<20; $i++){
$x = ($i%4)/3;
polyCube;
move $i 0 0;
scale 1 $x 1;
};
//00010001000100010010
```

```
for($i=0; $i<20; $i++){
$x = $i%2;
polyCube;
move $i 0 0;
scale 1 $x 1;
};
//00110011001100110011
```
![num pattern](assets/num_pattern.png)

## Something

```
int $k = 1;
for ($x=0; $x<10; $x++) {
	for ($y=0; $y<10; $y++){ 
		$name = "MyCube" + $k;
		polyCube -name $name;
		move ($x*2) ($y*2) 0;
		eval("select -r MyCube"+$k+".e[6]") ;
		float $xoff = rand(-.2, .2);
		float $yoff = rand(-.2, .2);
		move -r $xoff $yoff 0;
		eval("select -r MyCube"+$k+".e[7]") ;
		float $xoff = rand(-.2, .2);
		float $yoff = rand(-.2, .2);
		move -r $xoff $yoff 0;
		eval("select -r MyCube"+$k+".e[10]") ;
		float $xoff = rand(-.2, .2);
		float $yoff = rand(-.2, .2);
		move -r $xoff $yoff 0;
		eval("select -r MyCube"+$k+".e[11]") ;
		float $xoff = rand(-.2, .2);
		float $yoff = rand(-.2, .2);
		move -r $xoff $yoff 0;
		$k++;
	}
}
```

![sth](assets/something.png)


## Set Attributes example
```
// setting a value from a set of objects
for($i=0; $i<10; $i++){
	string $s = "MyCube" + $i;
	polyCube -name $s;
	move ($i*2) 0 0 ;
}
setAttr MyCube3.translateZ 4;

int $indx = 3;
eval("setAttr MyCube" + $indx + ".translateZ 7");
```

## Get Attributes example
```
// getting a value from a set of objects
for($i=0; $i<10; $i++){
	string $s = "MyCube" + $i;
	polyCube -name $s;
	move ($i*2) 0 0 ;
}

int $indx = rand(9);

eval("getAttr MyCube" + $indx + ".translateX");
```

## Greate Random Objects 
generate random objects by using a Function. If you want to add an Attribute (Variable) to the function – use the ```string $text``` input.

![](assets/grid.png)

```
string $some_text="hello world";
eval( "createObjects($some_text);" );

proc createObjects(string $text) {
        string $commands[] = { "polyCone", "polyCube", "polySphere", "polyTorus" };
        print($text);

        for( $i=-10; $i<=10; $i+=2 ) {
                for( $j=-10; $j<=10; $j+=2 ) {        
                        // generate a random number to use as an index into the commands array
                        int $index = `rand 4`;
                                
                        // call eval to execute the command
                        eval($commands[$index]);
                        
                        // move the object
                        xform -t $i 0 $j;
                }
        }
}
```


## LOFT

This command computes a skinned (lofted) surface passing through a number of NURBS curves.

![loft](assets/loft.png)

``` 
string $allCircles = "";
for ($t = 1; $t < 80; $t++) {
        $ang = rand(45,360); 
        $rad = rand(0.2,3.8);
        $siz = rand(2,0.2);
        circle -nr 0 0 0 -c 0 0 0 -sw 360 -r $rad;
        move 0 0 ($t * -0.5); 

        select -r ("nurbsCircle" + $t + ".cv[" + (rand(0,2)) + "]");
        move -r 0 (rand(2,0.2)) 0 ;   
        
        $allCircles = $allCircles + (" nurbsCircle" + $t);

}
eval("loft " + $allCircles);
```
