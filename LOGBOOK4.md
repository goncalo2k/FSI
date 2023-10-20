# SEED Labs – Environment Variable and Set-UID Program Lab

# Environment Variable and Set-UID Program Lab

### Task 1
> Prompt command printenv gives the information of all the environment variables of the system

 ### Task 2
> In the following task there were two processes child and parent that use the function printenv. By commenting each process and seeing their differences (diff env1 env2) the result is null. This implies that the environment is the same, as the environment variables are passed from parent process to child. 

### Task 3
> By compiling and running the program, in this task we conclude that by looking at the code, that the third argument passed to the "execve()" call is NULL, this implies that the function in pointing to NULL, which outputs NULL because the information is not allocate anywhere. 


### Task 4
> In the definition of the "system()" this call asks the shell if it can use an certain command {"/bin/sh -c command"}
<br>
> So instead of mantain the process execution and the same variables, as in "execve()" function, the system function mantais the environment variables passing it into a new process. The "execve()" function, only mantains de environment variables if they are passed as an argument.

### Task 5
> - Set-UID is a mechanism in the Unix's file permission system  that allows users to execute a file as its owner and have the owner's permissions.<br>
> - We developed a program that displays the current proccess' environmental variables. <br>
> - Defined 'root' as the program owner and transformed it into a SET-UID program, using the following commands:  <br>
> `bash
> $ sudo chown root setUID 
> $ sudo chmod 4755 setUID 
> `
> - In order to test correctly, there were some changes to the environmental variables:<br>
> `bash
> $ export PATH=$PATH:/home/seed/Desktop
> $ export LD_LIBRARY_PATH=/home/seed/myScripts/
> $ export COURSE_NAME=FSI
> `
> - After that, we executed the program again and we could verify that the previously defined environmental variables were in the program's list of environmental variables except for LD_LIBRARY_PATH. That's due to the fact that LD_LIBRARY_PATH enables the definition of a path to where the program gets its shared dynamic libraries, which enables execution of a malicious scriptby switching one of the shared libraries.<br>

### Task 6
- A Set-UID program was generated, incorporating the following code, which invokes the Linux `ls` command:
```c
system("ls");
```

- A 'malicious' program named `ls` was crafted within the directory `/home/seed/Desktop/fakeLs`.

- The PATH environment variable was modified to point to the directory containing the 'malicious' program:
```bash
$ export PATH=/home/seed/Desktop/fakeLs
```

- It was confirmed that the executed `ls` function was the malicious one and not the one from the operating system.