# Think outside of Maya 
Write, upload script out- & in Maya (MEL)


## Open, Close and Write

Part_1 Use your own path (directory)
```
//define the directory
chdir "/users/janis/desktop/";
```
Part_2 Lets open the file and write "Hello World"
```
//return file
$fileID = eval("fopen file.txt w");
fwrite $fileID "Hello World";
fclose $fileID;
```

## Open, Read and Close

```
chdir "/users/janis/desktop";
$fileId = eval("fopen file.txt r");

$input= eval("fread " + $fileId + " \"\"");
print $input;
fclose $fileId;
```
