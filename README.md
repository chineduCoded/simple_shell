# Okoronkwo Chinedu Elijah<br/>
## Description<br/>
A simple UNIX command interpreter that replicates functionalities of the simple shell (sh). Additional functions are also included. This program was written entirely in C as a milestone project for ALX Africa Software Engineering.<br/><br/>
## Installation<br/>
Clone this repository into your working directory. For best results, files should be compiled with GCC and the following flags: -Wall -Wextra -Werror -pedantic -std=gnu89<br/><br/>
## Usage<br/>
After compilation, the resulting program can run stand-alone, either in interactive or non-interactive mode.<br/><br/>
### Interactive Mode<br/>
In interactive mode, simply run the program and wait for the prompt to appear. From there, you can type commands freely, exiting with either the "exit" command or ctrl-D.<br/><br/>
### Non-Interactive Mode<br/>
In non-interactive mode, echo your desired command and pipe it into the program like this:<br/>
```shell
echo "ls" | ./shell
```
<br/>
In non-interactive mode, the program will exit after finishing your desired command(s).<br/>
### Included Built-Ins<br/>
Our shell has support for the following built-in commands:<br/>

| Command | Definition |
| --- | --- |
| exit[n] | Exit the shell, with an optional exit status, n. |
| env | Print the environment. |
| setenv [var][value] | Set an environment variable and value. If the variable exists, the value will be updated. |
| unsetenv [var] | Remove an environment variable. |
| cd [dir] | change the directory. |
| help [built-in] | Read documentation for built-in. |

## Credits<br/>
All code written by [Okoronkwo Chinedu Elijah](https://github.com/chineduCoded) and [Miracle Amarachi Okeosisi](https://github.com/Miracool45)
