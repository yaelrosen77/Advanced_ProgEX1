# Simulated Shell Environment

## Description
This repository contains the implementation of a simulated shell environment developed as part of the Systems Programming - 2 course. The project is written in C++ and includes a Makefile for easy compilation and testing.

The simulated shell supports a wide range of functionalities typically found in standard Unix-like shells, along with additional features to enhance user interaction and command execution capabilities.

## Features
The simulated shell environment supports the following features:

- **Redirection to stderr file**: If the specified stderr file does not exist, it will be created. This allows users to redirect error messages to a file for later review.
- **Customized prompt message**: Users can change the shell prompt to a customized message, making the shell experience more personalized.
- **Echo command**: The shell includes an echo command to print text to the standard output.
- **Status of the last executed command**: The shell maintains and displays the status of the last command executed, allowing users to check if the previous command was successful.
- **Change directory command (`cd`)**: Users can change the current working directory within the shell.
- **Repeat last command**: A command is available to rerun the last executed command, providing convenience for repetitive tasks.
- **Quit command**: A command to exit the shell gracefully.
- **Control-C detection without exiting**: The shell can detect Control-C (SIGINT) events without exiting, allowing users to interrupt commands without closing the shell.
- **Pipe redirection**: The shell supports redirection of multiple commands using pipes, enabling complex command sequences and data processing pipelines.
- **Variable management**: Users can add and manage variables within the shell environment.
- **Read command**: A command to read input from the user and store it in a variable.
- **Command history**: The shell maintains a history of the last 21 commands executed, allowing users to recall and rerun previous commands.
- **If-else command support**: The shell supports basic conditional execution using if-else commands.

## Executing the Program 
To run the simulated shell environment, follow these steps:
### Download the files
Clone the repository to your local machine.
```sh
git clone https://github.com/your-username/simulated-shell-environment.git
cd simulated-shell-environment
```
### Compile the program
Use the Makefile to compile the program.
```sh
make
```
### Run the program
Execute the compiled shell program.
```sh 
./myshell
```

## Authors
* [Itamar Kuznitsov](https://github.com/Itamar-Kuznitsov)
* [Yael Rosen](https://github.com/yaelrosen77)

## Running examples : 
```
(base) ➜  task1 ./myshell
hello: date >> myfile
hello: cat myfile
Tue Jun  4 23:17:52 IDT 2024
Tue Jun  4 23:18:14 IDT 2024
Tue Jun  4 23:22:28 IDT 2024
hello: date >> myfile
hello: cat myfile
Tue Jun  4 23:17:52 IDT 2024
Tue Jun  4 23:18:14 IDT 2024
Tue Jun  4 23:22:28 IDT 2024
Tue Jun  4 23:22:41 IDT 2024
hello: wc -l < myfile
wc -l < myfile
       4
hello: prompt = hi:
hi: mkdir mydir
hi: cd mydir
hi: pwd
/Users/itamar/Documents/CS - B.A/Assignments/Third year semester 2/Advance programming/task1/mydir
hi: touch file1 file2 file3
hi: ls
file1
file2
file3
hi: !!
file1
file2
file3
hi: echo abc xyz
abc xyz
hi: ls
file1
file2
file3
hi: echo $?
0
hi: ls no_such_file
ls: no_such_file: No such file or directory
hi: echo $?
0
hi: ls no_such_file 2> file
hi: ^C
You typed Control-C!
hi: cat > colors.txt
blue
black 
red
red
green
blue
green
red
red
blue
hi: cat colors.txt
blue
black
red
red
green
blue
green
red
red
blue
hi: cat colors.txt | cat | cat | cat
blue
black
red
red
green
blue
green
red
red
blue
hi: sort colors.txt | uniq | sort -r | head -3
red
green
blue
hi: quit
quit
(base) ➜  task1
```

## Version
* 0.1
  * Initial release ~ Jun 2024
