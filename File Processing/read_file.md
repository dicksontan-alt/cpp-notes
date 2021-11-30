# Read From Files
**REMINDER: Some of the concepts and explanation of code components has been covered in write file part. [Click here](https://github.com/dicksontan2618/cpp-notes/blob/main/File%20Processing/write_file.md) to navigate to have detailed explanations.**
In order to read from files, there are five steps to follow:
1. Gain access to work with files
2. Create link between files and file stream object
3. Open the files
4. Read data from files
5. Close the files

## Gain access to work with files
To gain access to work with files, we just need to import both `iostream` and `fstream` header file using `#include <iostream>` and `#include <fstream>`

## Create link between files and file stream object
To create link between files and file stream object, we will using the `ifstream` class (input file stream class). The syntax is as following:

`ifstream <name of object>`

In this example, we will name the file stream object as **infile**.

### `ifstream`
`ifstream` is a class included in `fstream` library which used to read data from files.

## Opening files
To open the file, we need to use the method from the `ifstream` object which is open(). The syntax is as following:

`infile.open("<name/path of file>")`

**REMINDER: The data inside the file will not be erased or overwritten if the specified file exists. No new file will be created if the specified file doesn't exists. This is different compared to `ofstream` object.**

## Read data from files
Normally, we read data from files by initialize a ***variable*** and copy the data from the file to the variable using `>>` operator. The syntax is as following:

`infile >> <variable name>`

**By default, C++ reads the file line by line. We can show this by the following example:**

Assume that there is a text file named `test.txt` which contains the following data inside the file:
```
12
3
5
```
By executing the following code:
```cpp
#include <iostream>
#include <fstream>
#include <string>

using namespace std;

int main(){
  
  ifstream infile; //Create input file stream object
  
  int num1, num2;
  
  infile.open("test.txt"); // Open file
 
  // Read data from file (line to line) 
  infile >> num1;
  cout << num1 << endl;
  
  infile >> num2;
  cout << num2 << endl;
  
  infile.close();// Close the file
  
  return 0;
}
```
The result will be as following:
```
12
3
```

## Closing Files
Lastly, close the file by using `close()` method. The syntax is as following:

`infile.close()`

## Additional Info
### Detect existence of file
To detect if the file opened exists or not, there are two ways:
1. `<object name>` (boolean approach)
2. `<object name>.fail()` method

##### `<object name>` (boolean approach)
When the file opened doesn't exist, the object name will be assigned with `false` value and vise versa.

##### `<object name>.fail()` method
When the file opened doesn't exist, the `<object name>.fail()` method will return a `true` value and vise versa.


Both ways are useful to indicate existence of file and throw an error if the file dosn't exists.

### Detect end of file
In `infile >> <variable name>`, the `>>` operator will return a `true` value if value is successfully read from the line and vise versa. By combining it with a `while` loop, the values in file will be read continously until the end of the file which `false` will be returned as there are no value at the end of file and the loop will be terminated.

