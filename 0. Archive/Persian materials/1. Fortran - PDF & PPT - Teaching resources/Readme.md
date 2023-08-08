# Variables
Variables in Fortran are divided into four categories: Integer, Real, Character, and Logical.

```
Integer  i
Real*8   p      ,q        ,r
```

# Calculation operations and their precedence
In Fortran, addition, subtraction, multiplication and division operations can be easily done with +, -, * and / symbols.
Note: Power operations are performed with the "**" symbol
The precedence of operations in Fortran is as follows:
1. Calculation of the expression inside the parentheses and library functions
2. Power
3. Multiplication and division
4. Addition and subtraction

# Structure of Fortran programs
A structure called General Structure is suggested for writing programs.
Note: The extension of the old programs written with Fortran was For, but the extension of the new Fortran program is F90

# Data input
1. Data entry by the user
```
Read(*,*) x
```
2. Data entry by the programmer
```
Pi=3.14
```
- Complex numbers are written as ordered pairs:
Z = a + bi
(a,b)
```
Ii=(0.,1.)
```

# Program output
The Write command is used to print information on the screen. "," should be placed between the variables that are to be printed
```
Write(*,*) a,b
```

Note: In order for a phrase to be printed exactly, it must be enclosed in quotation marks.
```
Write(*,*)  ‘Result=‘ ,a 
```

If the goal is to print the output in a specific order, we should write a special type of operator instead of the * sign.

Important operators are also:
X: Blank space
Fw.d: Decimal number output with field length W and decimal value d
L: logical variable output
Ew.d: power number output with field length W and decimal value d
Aw: string output with field length w
Im: Integer output with field length m
' ' : Whatever is placed inside the quotation marks will be printed exactly.
/ : Moves the editor to the next line.
  \: means to keep the cursor on the same line.

```
Write(*, '( operators )' ) outputs
```

`do` command:
The `do` loop is written as follows
do and exit loop:
do & while loop:




























































































