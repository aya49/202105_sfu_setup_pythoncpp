# What is programming?

## An example...

You've probably programmed before. When you enter `1+1` on a calculator, you are commanding it to calculate `1+1` for you. 

Now, what if you want your calculator to calculate lots of equations for you over and over in the future? Well, you write those equations out on a text file and feed this text file into your calculator for it to calculate the equations in the text file for you. This way, you can re-feed this text file any time you want the calculator to perform the same calculations in the future i.e. you:
1. "programmed" (wrote) a set of equations or instructions into a "program" (a text file) so that 
2. your "computer" (calculator) could "execute" (do the calculations requested by) your program.

## ...of programming workflow

A computer is just a super powerful calculator... that can only read and execute programs written in binary i.e. 0s and 1s. We call these "binary" program files, "machine executable" files.

Binary program code is almost impossible for us to read, let alone write, so we came up with this workflow:
1. program: you write a program in a human-readable "programming language" to a program text file.
2. compile: you get a "compiler" (translator) to "compile" (translate) your program text file into a machine read-able binary file.
3. execute: you let the computer execute the instructions in this binary.

C++ and Python are two of the most popular **programming languages**. 
- **C++** is more difficult to write, but it is extremely efficient and powerful. Operating systems and lower-level software are primarily written in C++.
- **Python** is much easier to write and is very popular, but it gives you less control. Python is used for high-level applications such as software development, data analysis, and artificial intelligence.

What makes programming so simple today is that people have already written many ready-to-use program codes. These codes are bundled into easy-to-use "functions" and groups of related functions are bundled into "packages" that we can just download and use.

Sometimes, these packages are coupled with easy to use GUI (graphical user interface) such that users don't even need to understand or use the associated programming language to run the code in the package; instead, complicated commands are coupled with visual buttons that users can click to use --- yep, that's basically what software is.

# Text editors and IDEs

Let's start with getting some tools to complete step 1: writing a human-readable program.

Your program code is essentially a text file, so you can edit it in any text editor. There are two types of text editing software you can use to write your program:
- **text editors** are light-weight text editors that may have a few additional functionalities such as syntax (grammar) highlighting.
  - [Sublime text](https://www.sublimetext.com/) and [Notepad++](https://notepad-plus-plus.org/) are extremely light-weight and fast text editors.
  - [Vim](https://www.vim.org/) is probably the most advanced text editor and most un-user-friendly text editor on the list. It has a steep learning curve, but when you get used to it, you will be able to edit code right out of a terminal (which will get useful if you are working out of a computer without a screen)!
  - [Visual studio code](https://code.visualstudio.com/) and [Atom](https://atom.io/) are powerful and extendable text editors that, depending on how many extensions you install, can be comparable to an IDE. In exchange, they can be resource-intensive.
- **IDEs** (integrated development environment) are heavy-weight text editors plus all the other tools you will need during the programming process. These tools are usually language-specific.
  - [Visual Studio](https://visualstudio.microsoft.com/) and [Eclipse](http://www.eclipse.org/) are general purpose IDEs with an in-built terminal and options for extensions for when you want additional functionality.
  - [Code::blocks](http://www.codeblocks.org/) is an old-school easy to use IDEs for C++.
  - [PyCharm](https://www.jetbrains.com/pycharm/) and [Spyder](https://github.com/spyder-ide/spyder) are popular Python IDEs used for general-purpose coding and data science respecitvely.

Note: different instructors will use different tools/IDE's, so go with whatever you are required to use in class.

# Set up your computer for programming with a terminal (C++ and Python)

The easiest way to work with C++ and Python is via a Unix terminal. In this section, we will go set up this "terminal" on your system.

## Windows

On Windows 10+, your OS comes with a Windows subsystem for Linux (WSL) which allows you to interface with your OS via a Unix terminal.

If you don't have it installed already, let's enable WSL and install a Linux distribution:
- open PowerShell as administrator: "start" > search for "PowerShell" > right-click "Windows PowerShell" and select "Run as administrator".
- paste the following command into the PowerShell and press the `enter` key:
```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```
- restart your computer on prompt.
- now that you have WSL enabled, let's install the Ubuntu distribution [here](https://www.microsoft.com/store/p/ubuntu/9nblggh4msv6)!
- after you've installed Ubuntu, open it up! If this is the first time you're opening it up, it should say it's installing. After that is finished, give yourself a username and password.

Now that you have a terminal (like the one you would have on Ubuntu), you will need to install:
- a C++ compiler `g++` by installing the GNU compiler tools and the GDB debugger (`sudo` means to run as admin, `whereis` verifies successful installation),
```
$ sudo apt-get update
$ sudo apt-get install build-essential gdb
$ whereis g++
```
- and Python 3.
```
$ sudo apt update && upgrade
$ sudo apt install python3 python3-pip ipython3
```

Now you're all set up to use your terminal in Windows to work with C++ and Python :)!


## Linux & Mac 

If your OS is a Linux or a Mac, Python and C++ are pre-installed and set up on your machine! It's just a matter of opening up the terminal and using them.

For Linux computers, this guide assumes you are using a Gnome-based desktop environment (e.g. Ubuntu) that interfaces between you and Linux.

Let's open up your terminal: application menu (Linux) / launchpad (macOS) > search for "terminal" and select it.


## Using your terminal

The terminal is an interface where you can type commands for your OS to execute.

Think of your terminal as a _**dumbed-down Siri**_ who only takes super specific commandstyped out commands; but as long as you know what the commands are, your terminal can do almost anything! Including executing your C++ or Python program.

If you have Firefox on your computer, you can let your terminal open it up for you; try typing the following command and pressing `enter`:

```
$ firefox
```

Pro tip: select your terminal window to do anything in the terminal.

Pro tip: press `ctrl-c` inside the terminal to terminate or stop any command, .

You can even navigate your files! Here are a few basic commands:
- `$ ls`: list the contents in your current directory.
- `$ cd [directory]`: "change directory" i.e. go to the `[directory]` or the folder (that you saw when you `ls`-ed);
  - `$ cd /`: go to the root directory in your Linux & macOS.
  - `$ cd /mnt/c`: go to the C drive on your Windows.
  - `$ cd ..`: go to the parent directory.
  - On a macOS, an easy way to go to your current directory is by typing `$ cd `, and then dragging a file from your desired directory in the file explorer into your terminal; you will see that the complete "path" or series of directories leading to your file is copied into your terminal. Don't forget to delete the file name from the path because you're "changing directories" not files (e.g. `/home/users/yourname/yourfile.txt` > `/home/users/yourname/`).
- `$ mkdir [directory]`: make a new directory.
- `$ rm [file]` / `$ rm -rf [directory]`: remove (delete) a file / directory (`-rf` means to "recursively" remove the directory and everything inside of it without requiring confirmation).
- `$ cp [file1] [file2]` / `$ cp -r [directory1] [directory2]`: copy and paste `[file1]` as `[file2]` / `[directory1]` as `[directory2]`.
- `$ cat [file]`: show contents of a `[file]`.

### Working with C++

1. Program: let's assume you have written C++ code in some text editor and saved it to file `main.cpp` (`.cpp` is the extension for C++ code).
2. Compile: now let's compile `main.cpp` into a machine read-able binary file `program` using the built-in C++ compiler `g++` by running the following command in your terminal (make sure your terminal is located in the directory where you have saved `main.cpp`):
```
$ g++ -o program main.cpp
```
3. Execute: `g++` has created a new file in your directory called `program` containing the binary translation of your C++ code `main.cpp`; running and executing the program is as easy as:
```
$ ./program
```

Congratulations! You have successfully compiled and executed your C++ code!

#### `Makefile`s

**Testing**: Usually, you write `main.cpp`, save it, compile it, run it, see if it works as you intended and if it doesn't, you edit `main.cpp` and do the previous steps all over again. Rarely do programs work perfectly on the first try.

To avoid writing `g++ ...` over and over again, you can create a text file called `Makefile` in your current directory and put the command into it:

```
program: main.cpp
    g++ -o $@ main.cpp
```
- `program` is the name of your command, 
- the files listed after it tells your compiler in what order the compiler should compile the files (in this case it doesn't matter because there is just one file),
- the command(s) on the second line starts with a tab, and
- `$@` refers to `program` so you don't have to type it over again i.e. the command on the second line is exactly the same as the command you wrote earlier.

Now, instead of typing the `g++ ...` command over and over again,
```
$ g++ -o program main.cpp
$ ./program
```

you can make the terminal refer to your `Makefile`:
```
$ make program
$ ./program
```

`Makefile`s are a lot more convenient if you are compiling lots of files and have large programs.

### Working with Python

Instead of us having to manually compile our program, Python works with an interpreter. While compilers translate entire programs at a time, the interpreter translates a single line of code at a time, does not create a binary file but rather directly runes the translated line of code at the request of the user. Interpreters are therefore slower, require less memory (since it's just one line at a time), and can feel a lot more automatic as it seamlessly directly run user-written code.

1. Program: let's assume you have written Python 3 code in some text editor and saved it to file `main.py` (`.py` is the extension for Python code).
2. Execute: you don't need to compile the code manually, just use the Python interpreter and it will automatically execute your code for you!
```
$ python main.py
```

## Remote accessing SFU computers

If you ever need access to computers or software at SFU, you can!
1. Click [here](https://www.sfu.ca/information-systems/services/mfa.html) to set up MFA (multi-factor authentication), you will need to do this before you start remote accessing any SFU computers.
2. Click [here](https://www.lib.sfu.ca/about/remote-access-library-lab-computers) for instructions on how to access the Burnaby or Surrey library lab computers and software from off-campus.

If you are a CMPT student, you will also have access to CSIL (computing science instructional labs).
1. Click [here](https://www.sfu.ca/information-systems/services/mfa.html) to set up MFA (multi-factor authentication).
2. Click [here](https://www.sfu.ca/computing/about/support/csil/remote-access.html) for instructions on how to access CSIL via SSH.


## Need software?

Check out the software made available to you as SFU students [here](https://www.sfu.ca/information-systems/services/software/list-of-software-at-sfu.html) and as SFU CMPT students [here](http://www.sfu.ca/computing/about/support/csil/windows/how-to-get-software.html#current-offers)!

# Programming

Syntax summary for C++ and Python: https://docs.google.com/presentation/d/1_-CSKhyVEnDMs1ed4VRiFOK9LWhagrLNZHx4OJCmUYw/edit?usp=sharing

## C++

### Variables

A **variable** is a defined value that holds data.
```C++
int i = 0;
```
Each variable can be defined by its:

1. **data type**; the data type determines how much space in memory C should allocate for your variable. You can also get the size of a variable via `sizeof(i);`. Below we list some common data types.

| Data type | Example | Range | Data size (bytes = 8 bits) |
|-----------|---------|-----------|------------------------|
| `char`    | `'a'`   | `0 - 255` (each character is associated with a specific integer) | 1                      |
| `int`     | `0`     | `-2147483648` to `2147483647` | 4  |
| `unsigned int` | `0` | `0` to `4294967295` | 4           |
| `float`   | `1.2`   | `-3.4E38` to `3.4E38` | 4          |
| `double`  | `1.2`   | `-1.7E308` to `1.7E308` | 8        |

2. **variable name**; the name you give to the variable.
3. **value**; a variable is "passed" as its value by default i.e. the variable name is synonymous to its value.
4. **pointer**; an address to the space C++ allocated for your variable value in the computer memory.

An **array** is a static (meaning it cannot change in length) list of values of the same data type; unlike variables, an array is "passed" as its pointer by default i.e. the variable name of an array is synonymous to its pointer.

The index of an array starts at `0` and can be accessed with `[...]`

```C++
int ia[3] = {6,3,1};
ia[0]; // 6
ia[1]; // 3
ia[2]; // 1
```

A **vector** is an array with inbuilt functions that allow you to change its size (remember to `#include <vector>`):

```C++
#include <vector>
#include <iostream>

int main() {
    // declare a vector
    std::vector <int> iv(3);

    // fill in the vector with values
    for (int i = 0; i<3; i++)
        iv[i] = i;
    
    // print the values in the vector to standard output
    for (int x: iv)
        std::cout << x << std::endl;

    return 0;
}
```

Strings are just special `char` arrays that you can initialize by doing:

```C++
std::string str = "Hello World!";
```

The notion of value vs pointer is what confuses most people, make sure you know it by heart:

| Declaration | Value | Pointer |
| ----------- | ----- | ------- |
| `int i`     | `i`   | `&i`    |
| `int* i`    | `*i`  | `i`     |
| `int ia[3]` | `*ia` (first element value only) | `ia` (first element value only) |

### Arithmetic operators

Arithmetic operators help you manipulate numerics: 
- operators: 
    - `+`, `-`, `*`, `/`, `%` (modulus/remainder); e.g. `int i = 4 + 5;`
- shorthands: 
    - `++`, `--`; e.g. `i++;` is the same as `i = i + 1;`
    - `+=`, `-=`, `*=`, `/=`; e.g. `i += 1;` is the same as `i = i + 1;`

### `if`/`else` statements

`if` statements help add decision-making to your program; its syntax works like this: `if (some statement)` is true, execute the code in `{...}`. You can also optionally add `else if` and `else` statements if you want to embed more decision-making options.

```C++
if (i > 2) {
    // code you want C++ to run if (...) is true
}

if (i > 2) {
    // code you want C++ to run if (...) is true
} else if (i == 2) {
    // code you want C++ to run if (...) is true
} else { // i < 2
    // code you want C++ to run otherwise
}
```

The following are logical operators you can use in conditional statements `(...)` to help you with your decision making:

| name                     | syntax       |
| ------------------------ | ------------ |
| equal to                 | `==`         |
| not equal to             | `!=`         |
| less than                | `<`          |
| greater than             | `>`          |
| less than or equal to    | `<=`         |
| greater than or equal to | `>=`         |
| not                      | `!`          |

### Loops

If you have a list of values you want to loop through, repeating the same piece of code for each value, you can repeat that piece of code over and over again (not a good idea):

```C++
int i = 0;
std::cout << i;

i = 1;
std::cout << i;

i = 2;
std::cout << i;

i = 3;
std::cout << i;

i = 4;
std::cout << i;
```

OR use any one of the following loops that do the same thing.

`while` loop: `while` my condition `(...)` is true, execute the code in `{...}`.
```C++
int i = 0;
while (i < 5) {
    std::cout << i++;
}
```

`do`/`while`: `do` execute the code in `{...}`; `while` my condition `(...)` is true, repeat; this guarantees that the code in `{...}` executes at least once.

```C++
int i = 0;
do {
    std::cout << i++;
} while (i < 5);
```

`for`: initialize variable `i` to `0`; `for` as long as `i < 5`, execute the code in `{...}` and `i++` at the end of each execution.

Recall: you can use `for (int x: iv)` to loop through each element `x` of vector `iv`, convenient huh.

```C++
for (int i = 0; i < 5; i++) {
    std::cout << i;
}
```

### Functions

When your code gets long, 

```C++
int main () {
    int a = 5;
    int b = 6;
    int mn1 = (a + b) / 2;

    a = 2;
    b = 3;
    int mn2 = (a + b) / 2;

    a = 1;
    b = 7;
    int mn3 = (a + b) / 2;

    return 0;
}
```

it's useful to **encapsulate** repeating code into a **function**: `int` is the `return` type, `mean` is the function name, `(int a, int b)` are its two input arguments.

Jargon: when we use a function and give it some input, we say we "call" a function and "pass" arguments into the function.

Recall: when we pass a variable into a function, we pass its value; when we pass an array into a function, we pass its pointer.

```C++
int mean(int a, int b) {
    int mn = (a + b) / 2;
    return mn;
}

int main () {
    int mn1 = mean(5, 6);
    int mn2 = mean(2, 3);
    int mn3 = mean(1, 7);

    return 0;
}
```

## Python

You can pull up documentation about a certain, e.g. function, in the Python interpreter (which you can bring up using `python` in your terminal) using `help`
```
$ python 
>> help(str)
```

### Variables

A **variable** is a defined value that holds data and is defined by its:
1. **variable name**; the name you give to the variable.
2. **value**; a variable is "passed" as its value by default i.e. the variable name is synonymous to its value.

```Python
i = 0
```

The data type and pointer are all implicit; you don't have to worry about how much memory your variable value takes up!

You can convert a variable to a certain data type using functions:

| Data type | Output |
|-----------|---------|
| `str(i)`    | `'0'`   |
| `int(i)`     | `0`     |
| `float(i)`   | `0.0`   |
| `bool(i)`  | `False` (in boolean, `0 == False`, everything else is `True`)  |

In Python, each data type has a specific set of **methods**, function-like things, that you can apply to variables of that data type.

Methods for strings `str` include:

```Python
s = 'Hello World!'
s[4]               # 'o'; indexing characters
s[3:5]             # 'lo'; in/ex-cludes the first/last index
s.upper()          # 'HELLO WORLD!'; converts to upper case
s.lower()          # 'hello world!'; converts to lower case
s.count('l')       # 3; counts number of times 'l' occurs
s.replace('e','p') # 'hpllo world!'; replaces a 'e' with 'p'
s.strip()          # 'hplloworld!'; strips whitespaces
```

A **list** is a dynamic (meaning it can change in length) list of values not necessarily of the same data type; lists are also nestable.

The index of a list starts at `0` and can be accessed with `[...]`.

```Python
l1 = ['Hello', 1]
l1[0] # 'Hello'
l1[1] # 1

l2 = [['Hello', 1], ['World!', 0.5]]
l2[0][0] # 'Hello'
l2[0][1] # 1
l2[1][0] # 'World!'
l2[1][1] # 0.5

# list operators
l3 = [9, 8] * 3    # [9, 8, 9, 8, 9, 8]
l1 + l3            # [2, 'Hi', 1, 9, 8, 9, 8, 9, 8]

# list methods
l1.index('Hello')  # 0; get the index of 'Hello'
l1.append(2)       # ['Hello', 1, 2]; append to list
l1.remove('Hello') # [1, 2]; remove a list element
l1.reverse()       # [2, 1]; reverse order of list
l1.sort()          # [1, 2]; sort the order of list
l1.insert('Hi', 1) # [2, 'Hi', 1] insert a value at index
```

Python **dictionaries** are another way to store a list of values, but for each value, its index can be given a **unique key**.

```Python
dict = {
    "brand": "Honda",
    "colours": ["red", "blue"],
    "year": 2020
}

dict["brand"]            # "Honda"; key="brand", value="Honda"

# dictionary methods
len(dict)                # 3; length of dictionary
dict.keys()              # dict_keys(["brand", "colours", "year"]); show keys
dict.values()            # dict_values(["Honda", ["red", "blue"], 2020]); show values
del dict["colours"]      # {"brand": "Honda", "year": 2020}; delete a key&value
dict["colour"] = "white" # {"brand": "Honda", "year": 2020, "colour": "white"}; add/replace a value


```

### Installing and using Python packages

A **NumPy array** is an array data structure that contains a list of values of the same data type; arrays are also nestable. This data structure is provided to you in the NumPy package.

To install a new package NumPy, in your terminal, use `pip`:
```
$ pip install numpy
```

Now you import and use NumPy functions and data structure, including NumPy arrays! Nested arrays are called nD arrays, most commonly, you would use a 2D array, which is analogous to a matrix. The indexing of a 2D  array is as intuitive as indexing in a matrix.

```Python
import numpy as np

na1 = np.array([1, 2, 3]) # array([1, 2, 3]) convert a list into a numpy array
na2 = np.array([[1, 2, 3], [4, 5, 6]]) # 2D array

# indexing
na1[0]               # array([1])
na1[:2]              # array([1, 2])
na1[1:]              # array([2, 3])
na2[0,2]             # 3

# array operators
na1 + na1            # array([2, 4, 6])
na1 * 2              # array([1, 4, 9])
n1 > 2               # array([False, False, True])

# array methods
na1.shape            # 3; size of the array
na1.append(np.array([4, 5])) # array([1, 2, 3, 4, 5]); append elements to an array
np.insert(na1, 0, 1) # array([1, 0, 2, 3, 4, 5]); insert an element
np.delete(na2, 0)    # array([1, 2, 3]); delete first row
np.mean(na1)         # 2; mean of array
np.median(na1)       # 2; median of the array
```


### Arithmetic operators

Arithmetic operators help you manipulate numerics: 
- operators: 
    - `+`, `-`, `*`, `/`, `%` (modulus/remainder); e.g. `i = 4 + 5;`
- shorthands: 
    - `+=`, `-=`, `*=`, `/=`; e.g. `i += 1;` is the same as `i = i + 1;`

### `if`/`else` statements

`if` statements help add decision-making to your program; its syntax works like this: `if (some statement)` is true, execute the code **indented** below it. You can also add optional `elif` and `else` statements if you want to embed more decision-making options.

Hint: indentation is super important in Python, it does not use braces!

```Python
if i > 2:
    # code you want Python to run if statement is true

if i > 2:
    # code you want Python to run if statement is true
elif i == 2:
    # code you want Python to run if statement is true
else: # i < 2
    # code you want Python to run otherwise

```

The following are logical operators you can use in conditional statements `(...)` to help you with your decision making:

| name                     | syntax       |
| ------------------------ | ------------ |
| equal to                 | `==`         |
| not equal to             | `!=`         |
| less than                | `<`          |
| greater than             | `>`          |
| less than or equal to    | `<=`         |
| greater than or equal to | `>=`         |
| not                      | `!`          |

### Loops

If you have a list of values you want to loop through, repeating the same piece of code for each value, you can repeat that piece of code over and over again (not a good idea):

```Python
i = 0
print(i)

i = 1
print(i)

i = 2
print(i)

i = 3
print(i)

i = 4
print(i)
```

OR use one of any of the following loops that do the same thing.

`while` loop: `while` my condition is true `:`, execute the code indented below.
```Python
i = 0;
while i < 5:
    print(i)
    i += 1
```

`for`: `for` each element in some list, run the indented code.

```Python
fruits = ['apple', 'banana', 'orange']
for fruit in fruits:
    print(fruit)
```

### Functions

When your code gets long, 

```C++
a = 5
b = 6
mn1 = (a + b) / 2

a = 2
b = 3
mn2 = (a + b) / 2

a = 1
b = 7
mn3 = (a + b) / 2
```

it's useful to **encapsulate** repeating code into a **function**: `def` starts your function definition, `mean` is the function name, `(a, b)` are its two input arguments.

Jargon: when we use a function and give it some input, we say we "call" a function and "pass" arguments into the function.

Recall: when we pass a variable into a function, we pass its value; when we pass an array into a function, we pass its pointer.

```Python
def mean(a, b):
    mn = (a + b) / 2
    return mn

mn1 = mean(5, 6)
mn2 = mean(2, 3)
mn3 = mean(1, 7)
```
