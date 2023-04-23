# Missing Sem In CS

## Description

This is a proof of what I did in **[Missing Semester of the CS](https://missing.csail.mit.edu/)** thing. I am writing this becasue I want to keep a proof that I did this. It is not much useful to anyone but you can follow the webiste(https://missing.csail.mit.edu/) to get the real thing. Thanks to people at MIT who provide things for free.

<details>
<summary> First Lecture </summary>

## What I did and understand?
- Learned the basis stuff about cd, echo, cat, ls, man, rmdir, rm commands and how rmdir has a fail safe that prevents us from removing a directory with files in it.
- What are absolute paths and what are the relative path.
- How we can change the input and output to a specific commands using > and < and how we can pipe output of certain commands to the input of other commands.
- Learned how we can go into the sys place and then go into the class directory to change a bunch of things like the brightness of the screen. But was not able to do any of those things since I was on Windows Subsystem For Linux.
- Also learned about how to read the various things in the first column when we run the ls -l commands and how we can get the last lines using tail.
- Did the exercises of provided learned about the chmod command and how to make a file a executeable.
- I did not write the things at the time of lecture so do not remember much.
</details>

<details>
<summary> Second Lecture </summary>

## What I understood?
- How to store value in variable and then echo them out like so ``` foo=house ``` and  then echo it out using ``` echo $bar ```. We need to be mindful of the spaces.
- We can use double quotes and single quotes to define string. But double quotes are like the template string in python that is any variable name in the double quotes string will evaluate to its value.
- Then we learn how to make function. In the lecture he already had a mcd function made and it looked liked the code below.
    ```
        mcd () {
            mkdir -p "$1"
            cd "$1"
        }
    ```
- So we then can write this in a file and name it with sh extension and to load this function into the shell we use the source filename command and then we can run then run the function with its name and the arguments
- I learned that **$0** is the name of the script. Ran it with echo $0 it gave me the output -bash. Others numbers are the respective arguments.
- **$_** will give us the last argument of the previous command and we can use the arguments with other commands.
- **!!** this command takes in the last command and the evaluate with the current command. Eg if I run echo hello and enter I get hello on the screen. Then if I run echo !!, this will evaluate to echo echo hello and then I will get the echo hello on the screen. It basically give us the last command.
- **$?** this give us the error string. It tell us error code which tells us if out program ran correctly. If program ran correctly it will give error code 0.
- Another example is if we try to search for foobar string in mcd.sh function using grep ``` grep foobar mcd.sh ``` and then run the ``` echo $? ``` we get error code 1 which means we tried searching for the string but did not get the string in the file.
- **true** has 0 error code and **false** has 1 error code.
- We can use logical operators like **||** and **&&** to combine to commands and they will run accordingly.
```
    >> echo false || echo 'it ran'
    >> false
    >> false && echo "echo it ran"
    >>
```
- We can use semicolon to concatenate commands in the same line.
- We can store the output of a command in a variable like this ``` goo=$(pwd) ```
- There was this process substitution thing that I did not understand. The example in the lecture was cat <(ls) <(ls ..)  [11:13](https://youtu.be/kgII-YWo3Zw?t=673)
- Then saw an example [script](https://youtu.be/kgII-YWo3Zw?t=740). We see new command **$#** which gives the number of arguments the script is running with and **$$** give the process Id of the command running.
- **/dev/null** is a place where we can write anything and it will be discarded.
- In bash we cannot use the normal comparision operator. We have special operators which we can read about in man test pages.
- convet image.png image.jpg can also be done using **image.{png,jpg}**. It is suggested we can use with with copy commnad but right now I don't know how.
- Another example of the above command is touch foo{,2,23,5} which will become touch foo foo2 foo23 foo5.
- We can also do is mv foo{1,2} to rename the file foo1 to foo2.
- We can create multiple file in various directories like this touch {foo,bar}/{a..j}. This will create a to j file in foo and bar directories.
- Then here is the **process substitution** example where we use the diff <(ls foo) <(ls bar) to find the difference between the 2 directories.
- We now see how to interact with shell using lot of different languages [here](https://youtu.be/kgII-YWo3Zw?t=1357). We learn about the shebang line.
- **Shebang** line tell the bash which interpreter to use when running a specific file. We can also give arguments in the shebang line.
- We have command **spellcheck** to find errors in our script file.
- We learned about some external tools we can install to get useful information of the various commands instead of googling about them or reading the man pages.
- Then we saw find command and how to use it to find the files. ``` find . -name src type -d ``` what is command does is find in current directory with name src and type directory. We also see various variation of the command [here](https://youtu.be/kgII-YWo3Zw?t=1920),
- There is also this shorter command fd for find which will use regex to find the file.
- **locate** command builds some kind of index and then it becomes fast to find the files.
- **grep** command to find the words in the file and we can use -R flag to search all the file in the directory. There also a rg command.
- We also saw other commands similar to grep.
- Then we learned how to go through the commands that we have already used. First using up arrow. Then **history** command which print all the commands used.
- We can combine the history command with grep command to find the specifc command.
- There also the ctrl+r key binding to do the backward search where we can type the command to find it in history. We can the keep hitting ctrl+r and then it will go through all the matches.
- In the end some tools in lecture were discussed which were not present on my wsl.
</details>