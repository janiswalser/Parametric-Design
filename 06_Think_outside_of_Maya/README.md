# Think outside of Maya 


## Open Close and Write

1.) At first create a file.txt document on your desktop

2.) Use your own path (directory)

//define the directory
chdir "/users/janis/desktop/";

3.) Lets open the file and write "Hello World"

//return file
$fileID = eval("fopen file.txt w");
fwrite $fileID "Hello World";
fclose $fileID;
