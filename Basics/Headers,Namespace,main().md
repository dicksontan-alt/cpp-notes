# Basic Components

## Simple Program

The following is a simple program. However, most people didn't really understand how each line of code in the following program works especially in the headers part.

```cpp
#include <iostream>
using namespace std;

int main(){
    cout<<"Hello World!";
    
    return 0;
}
```

### `#include <iostream>` 

`#include <iostream>` can be seen in almost all C++ programs and it is normally written at the beginning of any C/C++ program. To explain the usage/function of this line of code, we can separate this code into two different parts: `#include` and `<iostream>` .

#### `#include`

#include is a way of including a standard or user-defined file in the program. This directive is read by the **preprocessor** and orders it to insert the content of a ***user-defined*** or ***system header file*** into the following program. This type of preprocessor directive tells the compiler to include a file in the source code program. The process of importing such files is known as **File Inclusion**. Explaining in a simple way, #include is similar to **import** in other languages.

#### `<iostream>`

`<iostream>` is a header file that defines the standard input/output stream objects (such as `cin`, `cout`). Header files (aka Standard files) is a file which contains C/C++ function declarations and macro definitions to be shared between several source files.

### `using namespace std;`

`using namespace std` means using a namespace named `std` (stands for standard). What this does is tell the compiler that symbol names defined in the `std` namespace (the common ones are `cout`,`cin`,`endl`) are to be brought into your program's scope, so you can omit the namespace qualifier while writing the code. **All the files in the C++ standard library** declare all of its entities within the `std` namespace. That is why we have generally included the using namespace `std`. If we don't want to include this line, we can use the things inside the namespace like this: `std::cout`, `std::cin`. However, it is considered as a bad practice to use `namespace std`. [See here](https://stackoverflow.com/questions/1452721/why-is-using-namespace-std-considered-bad-practice)

### `int main(){...}`

`int main()` is used as the entry point of the program. main() is the function from where the program will start to execute. Everything inside the { }(code block) will be executed. `int main()` denote/initiate a function with the name main() and return a value with `int`(integer) data type. (that's why there are `return 0 ` in the end of code block.)

### `cout<<`

`cout` (standard output stream) is used together with `<<` (insertion operator) to output data/values to output device (mainly screen). The << operator inserts the data that follows it into the stream that precedes it. Easy explanation, `cout<<` is similar as `print()` or `printf()` in other languages.

## References

[Namespaces - C++ Tutorials](https://www.cplusplus.com/doc/oldtutorial/namespaces/)

[Structure of a program -  C++ Tutorials](https://www.cplusplus.com/doc/tutorial/program_structure/) 

[< iostream > - C++ Reference](https://www.cplusplus.com/reference/iostream/)
