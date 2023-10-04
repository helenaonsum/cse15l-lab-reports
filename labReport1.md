# Lab Report 1
## Helena Onsum, CSE 15 L
-----------------------------------------------
# *Using `cd` , `ls` , and `cat`.* 

**An example of using the command with no arguments:**
* `cd` :

![Image](cd no args.png)

When you use `cd` with no arguments the working directory will change to become the home directory.
In this example it will appear that nothing has changed, however, this is not an error as the working directory *was* the home directory prior
to the use of `cd` with no arguments. If the working directory was **lecture1** the use of `cd` with no arguments would result in the working directory changing to be the home directory, in this case **/home**.


* `ls` :
  
![Image](ls no args.png)

When using `ls` with no arguments, the command will list out the contents of the
working directory. This example shows that in the working directory **/home**, the content is **lecture1**. This is correct, and therefore not an error.
* `cat` :
  
![Image](cat no args.png)

When using `cat` with no arguments the terminal continues to run and is essentially waiting for an argument. The function of `cat` is to print out the contents of a file in the terminal, and when no argument is given there is no file for `cat` to read and print from. This causes an error where the terminal is just runnning and running. I used the command `cntrl` + `c` to stop the terminal from running. There was no change to the working directory.

**An example of using the command with a path to a directory as an argument:**
* `cd` :

![Image](cd dir arg.png)

When using `cd` with a path to a directory as an argument, the working directory changes to be the directory provided as the argument. In this case the working directory changes from being **/home** to being **lecture1**. The output shown in the example is not an error.
* `ls` :
  
![Image](ls dir arg.png)

Using the command `ls` with a directory as an argument will cause the terminal to list the contents of the directory provided as the argument, given that said directory is present in the working directory. In this case the working directory is **lecture1** and the directory provided as the argument for `ls` is **messages**. **messages** is present in **lecture1** and therefore `ls messages` correctly lists the contents of the **messages** directory. This is not an error.
* `cat` :
  
![Image](cat dir arg.png)

Using `cat` with a path to a directory as an argument will cause an error. This is because the `cat` commands purpose is for the terminal to read and print the contents of *files* and it cannot do this with a directory. In the example above, the directory **messages** is provided as the argument for `cat` and the terminal correctly throws an error and provides the message "messages: Is a directory".

**An example of using the command with a path to a file as an argument:**
* `cd` :
  
![Image](cd file arg.png)

When using `cd` with a path to a file as an argument you will get an error. This is because `cd` is used to change *directories* and will therefore not work with files. In this case, the argument provided for `cd` is the file **en-us.txt**. The terminal correctly throws an error and provides the message: "en-us.txt: Not a directory". The working directory remains unchanged. 
* `ls` :

![Image](ls file arg.png)

Using `ls` with a file as an argument will cause the terminal to print the filename if the file is present in the working directory. In this case, the working directory is **messages**, and the argument provided to `ls` is the file **en-us.txt**. Because **en-us.txt** is present in **messages**, the terminal prints **en-us.txt**. This is correct, and not an error.
* `cat` :
  
![Image](cat file arg.png)

When using `cat` with a path to a file as an argument, if the file is present in the working directory, the terminal will read the contents of that file and print it to the terminal. In this case, the argument provided to `ls` is the file **en-us.txt**. Because this file is present in **messages** (the working directory), the terminal prints the contents of **en-us.txt**: "Hello World!". This is correct, and not an error. 
