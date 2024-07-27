<h1 align="center"><a href="https://github.com/f-corvaro/FT_PRINTF"><img src="https://github.com/f-corvaro/FT_PRINTF/blob/main/.extra/ft_printf.png"></a></h1>

<p align="center">
	<b><i>"Custom printf implementation"</i></b><br>
</p>
<p align="center" style="text-decoration: none;">
    <a href="https://github.com/f-corvaro/FT_PRINTF"><img alt="GitHub code size in bytes" src="https://img.shields.io/github/languages/code-size/f-corvaro/FT_PRINTF?color=blueviolet" /></a>
    <a href="https://github.com/f-corvaro/FT_PRINTF"><img alt="Code language count" src="https://img.shields.io/github/languages/count/f-corvaro/FT_PRINTF?color=yellow" /></a>
    <a href="https://github.com/f-corvaro/FT_PRINTF"><img alt="GitHub top language" src="https://img.shields.io/github/languages/top/f-corvaro/FT_PRINTF?color=blueviolet" /></a>
    <a href="https://github.com/f-corvaro/FT_PRINTF"><img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/f-corvaro/FT_PRINTF?color=yellow" /></a>
</p>

<div align="center">

v9 | v10
:-------------------------:|:-------------------------:
[![subject-old](https://img.shields.io/badge/subject-ft_printf_v09-blueviolet)](https://github.com/f-corvaro/FT_PRINTF/blob/main/.extra/en.subject.pdf) | [![subject-new](https://img.shields.io/badge/subject-ft_printf_v10-blueviolet)](https://github.com/f-corvaro/FT_PRINTF/blob/main/.extra/en.subject(new).pdf)

</div>

<div align="center">
<table><tr><td>This guide is for subject v10. There are no differences between the two subjects.</td></tr></table>

</div>

<p align="center">

**WARNING:** *Before pushing, ensure you know where the moulinette will be executed. The length and information printed by `printf` can differ between macOS and Ubuntu systems. If you choose `ft_printf_100`, verify where the moulinette runs. For `ft_printf_125`, there are two macro conditions that will validate your project on both systems.*

</p>
<br>

<h3 align="center">Index</h3>

<p align="center">
 <a href="#introduction">Introduction</a><br>
 <a href="#overview">Overview</a><br>
 <a href="#folder-structure">Folder Structure</a><br>
 <a href="#project-requirements---mandatory-part">Project Requirements - Mandatory Part</a><br>
 <a href="#important-guidelines">Important Guidelines</a><br>
 <a href="#project-requirements">Project Requirements</a><br>
 <a href="#library-name">Library Name</a><br>
 <a href="#submission-files">Submission Files</a><br>
 <a href="#required-makefile-rules">Required Makefile Rules</a><br>
 <a href="#allowed-external-functions">Allowed External Functions</a><br>
 <a href="#ft_printf-prototype">`ft_printf()` Prototype</a><br>
 <a href="#project-requirements---bonus-part">Project Requirements - Bonus Part</a><br>
 <a href="#bonus-list">Bonus List</a><br>
 <a href="#theoretical-background">Theoretical Background</a><br>
 <a href="#understanding-printf-in-c">Understanding `printf` in C</a><br>
 <a href="#return-value">Return Value</a><br>
 <a href="#flags-and-witdth-modifiers">Flags and Width Modifiers</a><br>
 <a href="#variadic-functions">Variadic Functions</a><br>
 <a href="#static-libraries">Static Libraries</a><br>
 <a href="#makefile-cross-platform-compatibility-integration-with-other-projects">Makefile: Cross-Platform Compatibility, Integration with Other Projects</a><br>
 <a href="#executing-tests">Executing Tests</a><br>
 <a href="#testing-the-mandatory-part">Testing the Mandatory Part</a><br>
 <a href="#tester">Tester</a><br>
 <a href="#memory-leak-detection-with-valgrind">Memory Leak Detection with Valgrind</a><br>
 <a href="#installation">Installation</a><br>
 <a href="#usage">Usage</a><br>
 <a href="#evaluation-process">Evaluation Process</a><br>
 <a href="#correction-sheet">Correction Sheet</a><br>
 <a href="#moulinette-feedback">Moulinette Feedback</a><br>
 <a href="#developed-skills">Developed Skills</a><br>
 <a href="#references">References</a><br>
 <a href="#support-and-contributions">Support and Contributions</a><br>
 <a href="#author">Author</a><br>
</p>
<br>

## Introduction

<p align="justify">

The ft_printf project is a part of the curriculum at 42 school, aimed at teaching students the intricacies of implementing their own version of the printf function. The project involves creating a library, that includes libft, which mimics the functionality of the original printf function from the C standard library.  

</p>

### Overview

<p align="justify">

Students are required to handle various format specifiers, such as %c, %s, %d, %i, %u, %x, %X, and %%, as well as manage flags and field width options. The project also introduces students to the concept of variadic functions and the use of the va_start, va_arg, va_copy, and va_end macros. 

By completing this project, students gain a deeper understanding of string formatting and the inner workings of printf-like functions.

</p>
</br>

## Folder Structure

```
.
├── 01-ft_printf
│   ├── ft_printf
│   │   ├── ft_printf_100
│   │   │   ├── ft_printf_macOS
│   │   │   │   ├── ft_printf
│   │   │   │   │   ├── ft_hexadecimal.c
│   │   │   │   │   ├── ft_pointer.c
│   │   │   │   │   ├── ft_printf.c
│   │   │   │   │   ├── ft_printf.h
│   │   │   │   │   ├── ft_unsigned.c
│   │   │   │   │   └── ft_utils.c
│   │   │   │   ├── libft
│   │   │   └── ft_printf_ubuntu
│   │   │       ├── ft_printf
│   │   │       │   ├── ft_hexadecimal.c
│   │   │       │   ├── ft_pointer.c
│   │   │       │   ├── ft_printf.c
│   │   │       │   ├── ft_printf.h
│   │   │       │   ├── ft_unsigned.c
│   │   │       │   └── ft_utils.c
│   │   │       ├── libft
│   │   │       └── Makefile
│   │   └── ft_printf_125
│   │       ├── include
│   │       │   └── ft_printf.h
│   │       ├── libft
│   │       │   ├── include
│   │       │   ├── srcs
│   │       │   └── Makefile
│   │       ├── srcs
│   │       │   ├── ft_format.c
│   │       │   ├── ft_parse_and_handle_funcs.c
│   │       │   ├── ft_printf_funcs.c
│   │       │   ├── ft_printf.c
│   │       │   ├── ft_ptr.c
│   │       │   └── ft_utility_funcs.c
│   │       └── Makefile
│   ├── main.c
│   └── README.md
```

</br>

## Project Requirements - Mandatory Part

### Important Guidelines:

<p align="justify">

- This project must be written in C.
- Must adhere to the Norm.
- The function should not quit unexpectedly (segmentation fault, bus error, double free, etc.) except for undefined behaviors.
- All heap-allocated memory must be properly freed when necessary. No memory leaks allowed.
- The Makefile to submit must compile the source files with the flags `-Wall -Werror -Wextra` using the `cc` compiler. The Makefile must not relink.
- The `libft` is allowed in this project. You must copy its sources and its associated Makefile into a `libft` folder.

<p>
<br>

### Project Requirements: 

<p align="justify">

- Do not implement the buffer management of the original `printf()`.
- Your function must handle the following conversions: `cspdiuxX%`.
- Your function will be compared against the original `printf()`.
- You must use the `ar` command to create your library. Using the `libtool` command is forbidden.
- Your `libftprintf.a` must be created at the root of your repository.

You have to implement the following conversions:

| Format specifier | Data type |
| ---------------- | --------- |
| `%c` | single character |
| `%s` | string |
| `%p` | The `void *` pointer argument must be printed in hexadecimal format |
| `%d` | decimal (base 10) number |
| `%i` | integer in base 10 |
| `%u` | unsigned decimal (base 10) number |
| `%x` | number in hexadecimal (base 16) lowercase format |
| `%X` | number in hexadecimal (base 16) uppercase format |
| `%%` | Percent sign |

</p>
<br>

### Library Name: 

`libftprintf.a`

### Submission Files:

`Makefile, *.h, */*.h, *.c, */*.c`

 <p align="justify">

 You can create your own directory with any name you prefer. The same applies to the `.h` and `.c` files, which can be stored in any directory.

 </p>

### Required Makefile Rules:

`NAME, all, clean, fclean, re`

</p>

### Allowed External Functions: 

`malloc, free, write, va_start, va_arg, va_copy, va_end`

</p>

### `ft_printf()` Prototype: 

`int	ft_printf(const char *, ...);`

<p align="justify">

Basically, how does it work? `ft_printf()` takes two arguments: The first is a string that specifies how the output should be formatted. The second is a variable number of arguments, which are the values that will be formatted and printed (similar to how the real `printf()` function works).

</p>
<br>

## Project Requirements - Bonus Part

<p align="justify">

You don't have to complete all the bonuses. You can choose from the following options:

### Bonus List:

<p align="justify">

- Handle any combination of the following flags: `-0.` and the field minimum width for all conversions.
  
 | Flag | Description |
 | ---- | ----------- |
 | `%0` | When the 'width' option is specified, prepends zeros for numeric types (default prepends spaces). For example, `printf("%4X", 3)` produces `   3`, while `printf("%04X", 3)` produces `0003`. |
 | `%-` | Left-aligns the output of this placeholder (default is right-aligned). |
 | `%.` | Specifies precision for numeric types. |

- Handle all the following flags: `# +` (Note: one of them is a space).

 | Flag | Description |
 | ---- | ----------- |
 | `% (space)` | Prepends a space for positive signed-numeric types. Positive = ` `, Negative = `-`. Ignored if the `+` flag is present (default doesn't prepend anything for positive numbers). |
 | `%#` | For `g` and `G` types, trailing zeros are not removed. For `f`, `F`, `e`, `E`, `g`, `G` types, the output always contains a decimal point. For `o`, `x`, `X` types, `0`, `0x`, `0X` respectively are prepended to non-zero numbers. |
 | `%+` | Always shows the sign of the number (default hides the sign for positive numbers). |

</p>
<br>

## Theoretical Background

### Understanding `printf` in C

<p align="justify">

The `printf()` function in C is a widely used function for displaying formatted output on the console. It provides developers with a flexible and convenient way to print various types of data. By using format specifiers such as `%c`, `%s`, `%p`, `%d`, `%i`, `%u`, `%x`, `%X`, and `%%`, programmers can control the formatting of the output and make it more readable. With the `printf()` function, developers can create well-formatted and visually appealing console displays.

</p>

#### Return Value

<p align="justify">

`printf` returns an integer value that represents the total number of characters successfully printed to the standard output. If there is an error during the printing process, a negative value is returned. You can test it with the following example:

```c
int	main(void)
{
	#include <stdio.h>

	int	i;

	i = 0;
	i = printf("%s\n", "try");
	printf ("%d\n", i);


	return(0);
}
```

#### Flags and Witdth Modifiers

**Syntax:**

 ```%[flags][width][.precision][length]specifier```

1. **%**: Used before the specifier.
2. **Specifier**: Character that denotes the type of data.
3. **Width**: Minimum number of characters to be printed. If the number of characters is less than the specified width, white space will fill the remaining places. If the number of characters exceeds the specified width, all characters will be printed without truncation.
4. **Precision**: Varies by format specifier. For integral data (`d`, `i`, `u`, `o`, `x`, `X`), it specifies the minimum number of digits, adding leading zeroes if necessary. For floating-point data (`f`, `e`, `a`, `A`), it specifies the number of digits after the decimal point. For strings (`s`), it specifies the maximum length of the string to be printed.
5. **Length**: Specifies the length of the data type in memory, used with data type modifiers.

Length sub-specifiers:
- **h**: Short int and unsigned short int
- **l**: Long int and unsigned long int
- **L**: Long double

Flags and width modifiers are essential features of the `printf()` function in C, allowing developers to control output formatting. Flags modify the behavior of the conversion specifier, while width modifiers specify the minimum field width for the output.

Common flags include:
- **`-`**: Left-aligns the output.
- **`0`**: Pads the output with zeros instead of spaces.
- **`#`**: Adds special formatting to certain specifiers.

Width modifiers set the minimum field width. For example, if the width is 5 and the output is 3 characters long, it will be padded with spaces or zeros to meet the width requirement.

</p>
<br>

### Variadic Functions

<p align="justify">

Variadic functions are functions in C that can accept a variable number of arguments. They are useful when the number of arguments or their types are not known in advance. In the context of the ft_printf project for the 42 curriculum, variadic functions are used to handle the variable arguments passed to the ft_printf function. The key functions used to work with variadic arguments are va_start, va_arg, va_copy, and va_end. 

- `va_start` is used to initialize the argument list. It takes two arguments: the first is the va_list object that will hold the variable arguments, and the second is the last named parameter before the variable arguments.

- `va_arg` is used to retrieve the next argument from the va_list. It takes two arguments: the first is the va_list object, and the second is the type of the argument to retrieve.

- `va_copy` is used to make a copy of the va_list object. It takes two arguments: the first is the destination va_list object, and the second is the source va_list object.

- `va_end` is used to clean up the va_list object. It takes one argument: the va_list object to be cleaned up.

By using these variadic functions, the ft_printf function can handle different format specifiers and their corresponding arguments, allowing for flexible and dynamic formatting of the output. Variadic functions are a powerful tool in C programming, enabling the implementation of functions that can adapt to different input requirements.

</p>
<br>

### Static Libraries

<p align="justify">

Static libraries play a crucial role in organizing and managing the codebase. A static library, denoted by the `.a` extension, is a collection of precompiled object files that can be linked with other programs at compile time. By creating a static library for ft_printf, we can encapsulate the implementation details of the printf function and provide a clean and modular interface for other programs to use. This allows for code reuse and simplifies the process of incorporating ft_printf into different projects. Additionally, static libraries offer the advantage of faster compilation times, as the library code is already compiled and can be linked directly into the final executable. Overall, static libraries are an essential tool in the development of ft_printf, enabling code organization, reusability, and improved compilation efficiency.

</p>
<br>

### Makefile: Cross-Platform Compatibility, Integration with Other Projects

<p align="justify">

The Makefile is an essential component in the ft_printf project. It serves as a build automation tool, providing instructions on how to compile and link the source code into the final executable or library. By correctly utilizing the Makefile, developers can easily manage dependencies, compile only the necessary files, and ensure consistent and efficient builds. In the context of ft_printf, the Makefile can be integrated with the existing libft library, allowing for seamless usage of its functions. Additionally, the Makefile ensures cross-platform compatibility, enabling the project to be built and executed on different operating systems. The .PHONY rule in the Makefile is used to define false targets, which represent groups of commands or actions that are not associated with actual files. This allows developers to execute specific tasks without worrying about conflicting file names or dependencies. Overall, the Makefile plays a crucial role in the successful development and deployment of the projects.

</p>
<br>

## Executing Tests

### Testing the Mandatory Part

<p align="justify">

To test this project, you need to create a `main.c` file. You can find an example [here](https://github.com/f-corvaro/FT_PRINTF/blob/main/main.c). The example focuses on a specific specifier due to encountered issues, but you can implement additional tests as needed. After creating `main.c`, run `make all`, and then compile the code:

- **macOS:** Use `gcc main.c libftprintf.a` to compile. Then, execute the `a.out` file. The expected output is:

```shell
e4r4p2% ./a.out
 0x0 0x0 real: 9
 0x0 0x0 fake: 9
```

- **Ubuntu:** First, compile with gcc -c main.c, then link with gcc main.o libftprintf.a. The expected output is:

```bash
e4r4p2% ./a.out
(nil) (nil) real: 13
(nil) (nil) fake: 13
```

</p>

### Tester

<p align="justify">

I have used the [printfTester](https://github.com/Tripouille/printfTester) by [Tripouille](https://github.com/Tripouille). It is crucial to test the project on both Ubuntu and macOS, as the tester may yield different results on each platform.

</p>

### Memory Leak Detection with Valgrind

To find memory leaks and errors, I used `Valgrind`. Below are the steps for installation and usage:

#### Installation

Depending on your Linux distribution, use one of the following commands to install Valgrind:

```shell
sudo apt install valgrind  # Ubuntu, Debian, etc.
sudo yum install valgrind  # RHEL, CentOS, Fedora, etc.
sudo pacman -Syu valgrind  # Arch, Manjaro, Garuda, etc.
sudo pkg ins valgrind      # FreeBSD
```

#### Usage

To check for memory leaks and errors, use the following Valgrind command:

```shell
valgrind --leak-check=full --show-leak-kinds=all --track-origins=yes -s ./a.out
```

- `--leak-check=full`: Perform a detailed memory leak check.
- `--show-leak-kinds=all`: Show all kinds of leaks, including definitely lost, indirectly lost, possibly lost, and still reachable.
- `--track-origins=yes`: Track the origins of uninitialized values.
- `-s`: Provide a summary of the leak check.
- ADDITIONAL `--log-file`: Directs Valgrind's output to a specified file. This is useful for preserving extensive output that exceeds terminal capacity, allowing for easier review and analysis.

</p>
<br>

## Evaluation Process

### Correction Sheet

<p align="center">
<a href="https://github.com/f-corvaro/FT_PRINTF/tree/main"><img width="650" src="https://github.com/f-corvaro/FT_PRINTF/blob/main/.extra/eval_10-2023.png">
</p>
<p align="center"><
<a href="https://github.com/f-corvaro/FT_PRINTF/tree/main"><img width="650" src="https://github.com/f-corvaro/FT_PRINTF/blob/main/.extra/eval_10-2023(2).png">
</p>
<br>

### Moulinette Feedback

<p align="justify">

I completed this project three times. The first time, I failed because I only did the mandatory part and worked on an Ubuntu system, which caused an issue with the void pointer condition. The second time, I fixed the problem and received a score of 100.

<a href="https://projects.intra.42.fr/projects/42cursus-ft_printf/projects_users/3069521"><img align="center" src="https://github.com/f-corvaro/FT_PRINTF/blob/main/.extra/moulinette.png">

The third time, I completed the bonus part and achieved a score of 125.

</p>
<br>

## Developed Skills

<p align="center">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=git,c,vim,vscode" />
  </a>
</p><br>

## References

- [IBM Documentation on Variadic Functions](https://www.ibm.com/docs/en/i/7.3?topic=lf-va-arg-va-copy-va-end-va-start-handle-variable-argument-list) - Comprehensive guide on handling variable argument lists in C.
- [GeeksforGeeks: Variadic Functions](https://www.geeksforgeeks.org/variadic-functions-in-c/) - Tutorial on variadic functions with examples.
- [Medium: Variadic Functions Explained](https://onepunchcoder.medium.com/variadic-functions-explained-fd3b4ab6fd84) - In-depth explanation of variadic functions.
- [GNU Make Manual](https://www.gnu.org/software/make/manual/make.html#Rule-Introduction) - Official documentation for writing Makefiles.
- [Wikipedia: printf](https://en.wikipedia.org/wiki/Printf) - Overview and history of the `printf` function.
- [GeeksforGeeks: printf in C](https://www.geeksforgeeks.org/printf-in-c/) - Detailed guide on using `printf` in C.
- [Dev.to: Static Libraries in C](https://dev.to/iamkhalil42/all-you-need-to-know-about-c-static-libraries-1o0b) - All you need to know about creating and using static libraries in C.
  
<br>

## Support and Contributions

<p align="center">
If you find this repository helpful, please consider starring it to show your support. Your support is greatly appreciated!</p>

<p align="center">
<a href="https://ko-fi.com/fcorvaro"><img width="180" img align="center" src="https://github.com/f-corvaro/42.common_core/blob/main/.extra/support-me-ko-fi.svg"><alt=""></a>
<a href="https://github.com/sponsors/f-corvaro"><img width="180" img align="center" src="https://github.com/f-corvaro/42.common_core/blob/main/.extra/support-me-github.svg"><alt=""></a>

<br>

## Author

<p align="center"><a href="https://profile.intra.42.fr/users/fcorvaro"><img style="height:auto;" src="https://avatars.githubusercontent.com/u/102758065?v=4" width="100" height="100"alt=""></a>
<p align="center">
<a href="mailto:fcorvaro@student.42roma.it"><kbd>Email</kbd><alt=""></a>
<a href="https://github.com/f-corvaro"><kbd>Github</kbd><alt=""></a>
<a href="https://www.linkedin.com/in/f-corvaro/"><kbd>Linkedin</kbd><alt=""></a>
<a href="https://42born2code.slack.com/team/U050L8XAFLK"><kbd>Slack</kbd><alt=""></a>

<hr/>
