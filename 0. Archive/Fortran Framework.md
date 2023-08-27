# Fortran Framework

## Abstract
Writing an efficient code to numerically solve a problem has many points and complications. Therefore, years of coding experience are necessary to be able to correct the syntax errors of the program and extract the correct numerical results. Our initiative in this article is to present a format that enables a coder to avoid making many frequent errors and obtain the desired answers more easily and accurately.

## Introduction
In the title of this article, coding with Fortran is emphasized. But using this format in other programming languages also opens the way. Because an experienced coder knows that the major part of a code is its algorithm design, and this itself is independent of the language used to write the code. This format is in twelve steps in the form of explanatory lines with a sign! The first line divides the program into separate parts. In this article, we have tried to briefly explain the advantages of each step. It is better to copy these explanatory lines, like boards, in the program and finally write the desired code step by step according to the guide boards. This method has been tested by a number of students who have been at different levels of programming. Finally, the efficiency of this format prompted us to introduce and publish it in order to improve the coding speed and accuracy of other scholars. Those who are interested can get programs written with this format from the author.

## Introduction of program steps
### 1. Registration of program and programmers:
It is appropriate for the coders to introduce themselves at the beginning of each program and register their contact details. This work sometimes creates valuable scientific connections with other researchers and in a way the authors introduce themselves with this method and show their ability to attract the cooperation of others. It is also necessary to write a description of the program, the date of writing and its review for future reference.

```
!******************************************************************************************
! Mostafa Mohammad-Rezaee (MM), Independent researchers
! Mostafa.mohammadrezaee@gmail.com
!
! "General Structure.F90" is a suggested structure to numerical computer programming.
!
! Originally Written: 30-Des-2013 by MM
! Last revised: 22-Jan-2014 by MM
!******************************************************************************************
```

### 2. Definition of variables:
On the surface, coding with Matlab, where there is no need to define variables, seems easier. But defining variables in low-level languages and using the implicit none command - which disables Fortran's defaults - is one of the program's main benefits. The optimal definition of the number of directories of an array in order to prevent insufficient virtual memory forms and also to increase the speed of program execution is one of these advantages.

```
!******************************************************************************************
! Variables Definition
!******************************************************************************************
```

### 3. Assigning an initial value of zero to the variables:
Uninitialized variables can cause a serious problem. Therefore, all variables must be initialized before use, because otherwise, the compiler will report the remaining data from the previous program that occupied the same part of the memory.

```
!******************************************************************************************
! Giving Zero to variables
!******************************************************************************************
```

### 4. Getting input parameters from the user:
Variables that are supposed to have different values in successive executions of the program and the purpose of the program is to check the change of those parameters, it is better to be set by the user.

```
!******************************************************************************************
! Inputs
!******************************************************************************************
```

One technique is to receive each variable in both numerical and character form, so that from its numerical format for calculations, and from the character format of `E` and `freq`, it is a real number, but the `EE` and `freqf` variables are the same values, but in character form, by the compiler.

```
Real E , freq
Character*30 EE, freqf, filename1
write(*,'(/,2x,a,\)') ' Enter the Energy value : '
read(*,*)E
write(*,'(/,2x,a,\)') ' Again : '
read(*,*)EE
write(*,'(/,2x,a,\)') ' Enter the frequency value : '
read(*,*)freq
write(*,'(/,2x,a,\)') ' Again : '
read(*,*)freqf
```

### 5. Assigning file names using input information or problem specifications:
This section has a narrow point that if we use it correctly, firstly, the speed of working with the output files increases, secondly, the output information is well categorized. For this, it is necessary to create the file name from the input information.

```
!******************************************************************************************
! Determination of Filenames and Opening files
!******************************************************************************************
```

In addition, if our outputs are in the form of graphs, it is better to save the file with the extension `plt` _ related to `tecplot` software _. In addition to many features, this software has the advantage that a graph can be drawn just by clicking on the file icon. The `//` operator joins two character expressions together and the `trim()` command removes the unoccupied characters of a character field. (Example: temperature graph in terms of time for specific pulse energy and frequency)

```
filenameTt = 'E'//trim(EE)//' f'//trim(freqf)//' Tt.plt'
open(1,file=filenameTt)
```

### 6. Entering constant values into the program:
It is better to concentrate all the values of the program in this part. They should also be arranged in a meaningful and readable order so that they can be controlled easily.

```
!******************************************************************************************
! Constants
!******************************************************************************************
```

### 7. Determining the number of bins of each dimension of the array optimally using input values and constant values:
The smaller the number of directories in an array, the less likely it is to reduce the program execution time and deal with memory errors. Therefore, it is necessary to allocate the arrays optimally. In general, it is better not to use an array to solve a problem unless it is really needed.

```
!******************************************************************************************
! Arrays Allocation
!******************************************************************************************
```

### 8. Assigning an initial value of zero to all arrays:
Arrays must be initialized like variables. For this, it is better to assign zero value to all directories by the forall command.

```
!******************************************************************************************
! Giving Zero to Arrays
!******************************************************************************************
```

### 9. Print input values and program constant values:
It is necessary for the user to make sure that all the values he feeds the program with are correct before running the main part of the program.
In this regard, it is better to print the names of the variables and their value in front of each other so that the user can easily control them.

```
!******************************************************************************************
! Printing Constants and Inputs
!******************************************************************************************
```

### 10. The main part of the program:
In this section, boundary conditions and problem solving algorithm are written.

```
!******************************************************************************************
! Main Block of the Program
!******************************************************************************************
```

### 11. Print the results:
Although the printing of the results is introduced as a separate section, sometimes it is necessary to save the information directly in the files in the same main section of the program. If the place of receiving the outputs is chosen intelligently in the program, it can prevent the insufficient virtual memory message from appearing in most cases and increase the speed of the program execution sometimes tens of times.

```
!******************************************************************************************
! Printing Results
!******************************************************************************************
```


