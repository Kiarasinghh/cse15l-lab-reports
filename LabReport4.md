# Lab Report 4 

## Step 1: Log into ieng6

<img width="606" alt="image" src="https://github.com/Kiarasinghh/cse15l-lab-reports/assets/156370071/0f2cd24c-07bc-425f-94de-94c3f34078d4">


To log into ieng6 I typed the command ``ssh k6ingh@iegn6@ucsd.edu`` in the terminal. I did not need to enter my password because I had already set up my SSH keys for easy access and get logged in immedietly. 

## Step 2: Clone fork of repository 
<img width="495" alt="image" src="https://github.com/Kiarasinghh/cse15l-lab-reports/assets/156370071/8291f7b6-0fab-416d-8ea2-0d08ffde61a6">


Keys pressed: ``ctr+c`` to copy the ssh url of the repository and then ``ctr+v`` to paste it after typing  ``git clone`` in the terminal. 

## Step 3: Run the tests

<img width="496" alt="image" src="https://github.com/Kiarasinghh/cse15l-lab-reports/assets/156370071/38d57119-06c5-4a90-8bf2-31cfb62cc43c">


To run the tests I ran `bash test.sh` in the terminal which ran the bash script to compile and run the tests in `ListExamplesTests.java`. 

## Step 4: Edit the code file to fix the failing test

<img width="496" alt="image" src="https://github.com/Kiarasinghh/cse15l-lab-reports/assets/156370071/41ef407f-e568-43ee-a223-32ced8a71549">


Keys pressed: 
1) `vim List<tab>Examples.java` - This opens `ListExamples.java` in the vim editor so that I can fix the error in it. The `<tab>` helped me autocomplete the name of the file. 
2) `14j` - To move down 14 lines as that is where the line with the error was relative to my cursor's current position
3) `e` - To move the cursor to the end of the first word
4) `x` - To delete the `1` in `index1`
5) `i` and then `2`- To enter insert mode and make it  `index2`
7) `esc` - To exit insert mode
8) `:wq` - To save changes and exit the editor 

## Step 5: Run the tests again 

<img width="275" alt="image" src="https://github.com/Kiarasinghh/cse15l-lab-reports/assets/156370071/f6794c50-8987-456c-a8e2-6a5d0925e317">

Keys Pressed: 
`<up><up><up>` `<enter>` - The `bash test.sh` command was 3 up in the search history so I used the up arrow to access it and clicked enter to run it. As showed in the screenshot above, this time the tests passed. 

## Step 6: Commit and push the resulting change to your Github account

<img width="422" alt="image" src="https://github.com/Kiarasinghh/cse15l-lab-reports/assets/156370071/1ec37bb3-e486-41a8-8b33-c9333ed7cb93">

Keys Pressed:
1) `git add .` - adds the files in the working directory to the staging area
2) `git commit -m "The error is now fixed"` - Saves changes to the local repository with a commit message. In this case, it is "the error is now fixed".
3) `git push origin` - Saves the code on github by pushing the current branch to the branch of in the remote repository with the same name. In this case it is my `lab7 `fork on github. 


