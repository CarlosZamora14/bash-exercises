## Parameter and variables
> A parameter is an entity that stores values.

There are three types of parameters: positional parameters, special parameters, and variables.

The value of a parameter is accessed by preceding its name, number, or character with a dollar sign, as in `$3`, `$#`, or `$HOME`. The name may be surrounded by braces, as in `${10}`, `${PWD}`, or `${USER}`.

### Positional parameters
Positional parameters are arguments present on the command line, and they are referenced by a number.
The first argument is `$1`, the second is `$2`, and so on. To access positional parameters greater than 9, the number must be enclosed in braces: `${15}`.

### Special parameters (*@#0$?_!-)
They are set by the shell to store information about aspects of its current state, such as the number of arguments and the exit code of the last command. Their names are nonalphanumeric characters.

- `$*` will expand to all of the positional parameters into one ‘super parameter’.
- `$@` will expand all positional parameters, but treats them as an array.
- `$#` expands to the number of positional parameters.
- `$0` contains the path to the currently running script or to
the shell itself if no script is being executed.
- `$$` contains the process identification number (PID) of the current process.
- `$?` is set to the exit code of the last-executed command.
- `$_` is set to the last argument of that command.
- `$!` contains the PID of the last command executed in the background.
- `$-` is set to the option flags currently in effect.

### Variables
A variable is a parameter denoted by a name. A name is a word containing only letters, numbers, or underscores and beginning with a letter or an underscore. Values can be assigned to variables in the following form: `name=VALUE` (if there are spaces around the `=`, the command would not work).

