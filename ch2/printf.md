## printf
It is a shell built-in, similar to the printf() function in C/C++, Java, PHP, and other programming languages. The command allows you to print formatted text and variables in standard output.

```bash
printf [-v var] format [arguments]
```

The format string can contain ordinary characters, escape sequences, and format specifiers. Ordinary characters are printed unchanged to the standard output. Escape sequences are converted to the characters they represent. Format specifiers are replaced with arguments from the command line.

### Escape sequences
Escape sequences are single letters preceded by a backslash:
- `\a`: Alert (bell)
- `\b`: Backspace
- `\e`: Escape character
- `\f`: Form feed
- `\n`: Newline
- `\r`: Carriage return
- `\t`: Horizontal tab
- `\v`: Vertical tab
- `\\`: Backslash
- `\nnn`: A character specified by one to three octal digits
- `\xHH`: A character specified by one or two hexadecimal digits

The backslashes must be protected from the shell by quotes or another backslash:

### Format specifiers
The format specifiers are letters preceded by a percent sign. Optional modifiers may be placed between the two characters. The specifiers are replaced by the corresponding argument.

When there are more arguments than specifiers, the format string is reused until all the arguments have been consumed.

#### Common specifiers
- The `%s` specifier prints the literal characters in the argument.

- `%b` is like `%s` except that escape sequences in the arguments are translated.

- Integers are printed with `%d`. The integer may be specified as a decimal, octal (using a leading `0`), or hexadecimal (preceding the hex number with `0x`) number. If the number is not a valid integer, printf prints an error message.

- For decimal fractions or floating-point numbers, use `%f`. By default they will be printed with six decimal places.

- Floating-point numbers can be presented in scientific notation using `%e`.

- Integers can be printed in hexadecimal using `%x` for lowercase letters or `%X` for uppercase letters.

### Width specification
You can modify the formats by following the percent sign with a width specification. The argument will be printed flush right in a field of that width or will be flush left if the number is negative:

```bash
printf "%8s %-15s:\n" first second third fourth fifth sixth
```

If the width specification is preceded by a `0`, the numbers are padded with leading zeroes to fill the width:

```bash
printf "%04d\n" 12 23 56 123 255
```

A width specifier with a decimal fraction specifies the precision of a floating-point number or the maximum width of a string:

```bash
printf "%12.4s %9.2f\n" John 2 Jackson 4.579 Walter 2.9
```

### Printing to a variable
The optional `-v` flag assigns the output of the command to a variable instead of printing it to the standard output.

```bash
printf -v num "%04d" 4
printf "%s\n" "$num"
```