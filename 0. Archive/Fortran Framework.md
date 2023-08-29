# Fortran Framework

## Abstract
Crafting an efficient code to solve numerical challenges involves various intricacies. Thus, substantial coding experience is essential to rectify syntax errors and achieve accurate results. This article aims to introduce a format that helps coders mitigate common errors, facilitating the acquisition of accurate and straightforward solutions.

## Introduction
The title of this article highlights coding with Fortran, but it is important to note that this approach is applicable across other programming languages as well. A seasoned coder understands that the crux of any code lies in its algorithm design, which is fundamentally language-agnostic. This approach is organized into twelve steps, each accompanied by explanatory comments marked with an exclamation sign (!). The initial comment demarcates the program into distinct segments. Throughout this article, we succinctly delineate the merits of each step. It is recommended to replicate these explanatory comments, akin to guideboards, within the program and subsequently craft the requisite code step-by-step, adhering to the guidelines provided. This methodology has undergone trials by students at various stages of their programming journey. The proven efficacy of this approach inspired us to share and disseminate it with the aim of augmenting the coding velocity and precision of fellow researchers. Enthusiasts can acquire programs scripted in this format from the author.

## Introduction of program steps
### 1. Registration of program and programmers:
It is essential for programmers to include a brief introduction about themselves and their contact information at the start of each program. This not only fosters valuable connections with fellow researchers and professionals but also serves as a platform for the authors to showcase their capabilities, thereby encouraging collaborative efforts. Additionally, it is crucial to provide a detailed description of the program, along with the date it was written and reviewed, to facilitate easy reference and comprehension in the future. This practice enhances the program's documentation, making it more accessible and user-friendly for others who may work on it or use it as a reference.

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

### 12. Close the opened files and terminate the program:
At first glance, it seems that keeping the files opened at the beginning of the program does not cause a problem, but experience has shown that to prevent problems caused by the interference of the program in repeated executions, it is better to close the files at the end of the work.

```
!******************************************************************************************
! Closing Files and Ending the Program
!******************************************************************************************
```

### Conclusion
In this article, the authors, using their years of experience, have tried to provide a template for writing a program, following which, users - from professionals to beginners - will be able to write optimal codes and avoid many errors. avoid frequent Of course, modular programming also follows some of these goals, but we believe that this format is much easier and more efficient.
