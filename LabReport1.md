`cd`


![Image](cd1.png)

Working directory : `/home`

The `cd` command brings the working directory back to home when there is no argument.

This is not an error. 

![Image](cd2.png)

Working directory: `/home` 

This command moved the working directory into the `/home/lecture1` directory which can be seen with `lecture1` being written after the "~/". This happens since `lecture1` is a directory in home. 

This output is not an error as the `cd` command was used correctly. 

![Image](cd3.png)

Working directory: `/home/lecture1`

README is a file in the `lecture1` directory and not a directory itself. Therefore `cd` cannot be used with `README` as the arguement as it requires a directory.

The output is an error because a file was used as an arguement and not a directory. 

`ls`


![Image](ls1.png)

Working directory : `/home/lecture1`

The `ls` command lists all the files and folders in `lecture1`. It doesn't display the files inside any folders, just the name of the folder. The folder name is also in another format (blue colour in this instant) which makes it easily identifiable as not being a file. 

This is not an error. 

![Image](ls2.png)

Working directory: `/home/lecture1`  

This command listed the name of all the files in messages.  

This output is not an error.

![Image](ls3.png)

Working directory: `/home/lecture1`

Using `ls` command with a file as the path outputs the path of the file name that is passed in as the argument. 

The output is not an error. 


`cat`


![Image](cat1.png)

Working directory : `/home`

When there is no arguement, the `cat` command prompts for user input and outputs the input. It continues to ask for user input until ctrl+c is clicked to exit this. 

This is not an error. 

![Image](cat2.png)

Working directory: `/home`

The output is a message saying that lecture1 is not a directory since `cat` is used to concatonate text. 

This output produces an error since a directory is used as the path and not a file that can be concatonated. 

![Image](cat3.png)

Working directory: `/home/lecture1`

The `cat` command concatonated the text in the Hello.java file and displayed it all together. 

The output is not an error. 
