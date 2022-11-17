% HSH(1)
% Okoronkwo Chinedu Elijah and Okeosisi Miracle Amarachi
% November 2022

# NAME
hsh - simple UNIX command interpreter

# SYNPOSIS
**hsh** [**filename**]

# DESCRIPTION
**hsh** is a sh-compatible command line interpreter that executes commands read from the standard input or from a file.


# ARGUMENTS
If arguments remain after option processing, the first argument is assumed to be the name of a file containing shell commands. hsh reads and executes commands from this file, then exits. hsh exit status is the exit status of the last command executed in the script. If no commands are executed, the exit status is 0. An attempt is first made to open the file in the current directory, and, if no file is found, then the shell searches the directories in PATH for the script.

# COMMAND EXECUTION
After a command has been split into words, if it results in a simple command and an optional list of arguments, the following actions are taken.<br/>
If the command name contains no slashes, the shell attempts to locate it. If there exists a shell function by that name, that function is invoked. If the name does not match a function, the shell searches for it in the list of shell builtins. If a match is found, that builtin is invoked.<br/>
If the name is neither a shell function nor a builtin, and contains no slashes,**hsh** searches each element of the **PATH** for a directory containing an executable file by that name. **hsh** uses a hash table to remember the full pathnames of executable files. A full search of the directories in **PATH** is performed only if the command is not found in the hash table. If the search is unsuccessful, the shell searches for a defined shell function named "command not found". If that function exists, it is invoked with the original command and the original command's arguments as its arguments, and the function's exit status becomes the exit status of the shell. If that function is not defined, the shell prints an error message and returns an exit status of 127.

# ENVIRONMENT
**hsh** takes a copy from **Bash** environment of the parent process where it was executed. The environment is an array of strings containing the variables in the format.

When a program is invoked it is given an array of strings called the environment. This is a list of name-value pairs, of the form name=value.<br/>
The shell provides several ways to manipulate the environment. On invocation, the shell scans its own environment and creates a parameter for each name found, automatically marking it for export to child processes. Executed commands inherit the environment. The export and declare -x commands allow parameters and functions to be added to and deleted from the environment.<br/>
If the search is successful, or if the command name contains one or more slashes, the shell executes the named program in a separate execution environment. Argument 0 is set to the name given, and the remaining arguments to the command are set to the arguments given, if any.

# EXIT STATUS
**hsh** exit status of an executed command is the value returned by the waitpid system call or equivalent function. A command which exits with a zero exit status has succeeded. An exit status of zero indicates success. A non-zero exit status indicates failure.<br/>
If a command is not found, the child process created to execute it returns a status of 127.<br/>
All builtins return zero on success and one or two on incorrect usage (indicated by a corresponding error message).

# BUILTINS
The following builtin commands are supported:
**env**
- Print the current environment
**setenv** [**variable**][**value**]
- Creates a new environment variab;e or modifies an existing one.
**unsetenv** [**variable**]
- Removes an environmental variable.
**exit** [**status**]
- Exit the shell
**cd** [**directory**]
- Changes the current directory of the process to DIRECTORY.  If no argument is given, the command is interpreted as cd $HOME. If the argument - is given, the command is interpreted as cd $OLDPWD. The environment variables PWD and OLDPWD are updated after a change of directory.
**help**
- Print help message of builtin command.

# SEE ALSO
access(2), chdir(2), execve(2), _exit(2), exit(3), fflush(3), fork(2), free(3), isatty(3), getcwd(3), malloc(3), open(2), read(2), sh(1), signal(2), stat(2), wait(2), write(2)


# COPYRIGHT
**hsh** is copyright &copy; 2022 by Okoronkwo Chinedu Elijah and Okeosisi Miracle Amarachi.