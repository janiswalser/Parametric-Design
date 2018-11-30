<p align="center">
  <img width="460"  src="https://media1.giphy.com/media/vQqeT3AYg8S5O/giphy.gif?cid=3640f6095c015c1e6a78644873027c2a">
</p>


# Usefull Snippets

As a lazy designer, I really like to collect and keep a library of useful code snippets that allow me to save a lot of time. Today, I have compiled a list of the some interesting snippets to boost up your process and creativity.

First of all, while I was running and executing scripts in MEL I felt crazy because every time I executed a new script – the before created stuff was still in the canvas. 

Lets put this snippets alwas on top of every other line of code!

## Select & Delete

```
select -all;
delete;
```
## Get Attributes
Returns the value of an attribute.
Example:
```
polyCube -name "MyCube";
getAttr MyCube.translateX; // Result is 0
```

## Set Attributes
Changes the value of an attribute.
Example:
```
polyCube -name "MyCube";
setAttr MyCube.translateX 4;
eval("setAttr MyCube.translateX 30");
```

## Eval
This statement is designed to allow execution of a command which is not known until
runtime. It requires at least one argument, the first, which is the command to be executed.
```
print(5); //will print 5
eval(" print(5); "); //will execute the command “print 5”
```

 other example:
```
$command = "polyCube";
eval($command);
```

## Naming
Name each object you create so that you can call it up again later.
```
$command = "polyCube";
$name = "MyCube";
eval($command + " -name " + $name);
```


## String Substring
You need just a part of your String – Lets cut it!
```
$s = "Apple";
print (substring($s,2,4)) //pple

```


## String Compare
Compares its 2 string arguments and returns an integer less than, equal to, or greater than 0, based upon whether the first argument is lexicographically less than, equal to, or greater than the second argument.

```
  $s1 = "Apple";
  $s2 = "Bannan";
  
  print (strcmp($s1 , $s2))

```

## Groups
Just add the elemnts you want to group!

```
group -name MyGroup pCube1 pCube2 pCube3 pCube4 pCube5 pCube6;
```

Create 20 Cubes and add them to a group.
```
string $s = "";

for($i=1; $i<=20; $i++){
	$s = $s + " pCube" + $i;
};
eval( "group -name MyGroup " + $s);
```

## Functions/Procedures
```
string $some_text="hello world";
eval( "MyFunction($some_text);" );

proc MyFunction(string $text) {
        print($text);
}
```

## Listing Scene Nodes
Within mel we can use the mel function ls to list objects in the maya scene. You may well be suprised by how many there are just in a new scene file!

```
// the nodes in the scene
$nodes = `ls`;

// loop through the array and print each value [for in loop notes]
for( $node in $nodes ) {
    //print the node name
    print( $node + "\n" );
}
```

## Use Arrays
```
		int $int_array[] = {10,9,8,7,6,5,4,3,2,1,0};
		
		// number of elements
		int $size = size($int_array);
		
		// loop through the array and print each value 
		for($i=0;$i<$size;++$i) {
		
			// access the value by providing an index into
			// the array, where the first index is 0. 
			$value = $int_array[ $i ];
		
			// print the value
			print( $value + "\n" );
		}
```

