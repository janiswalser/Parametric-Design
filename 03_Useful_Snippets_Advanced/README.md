
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
