# Write to Files
In order for us to write to files, there are three steps we need to follow:
1. Gain access to work with files
2. Create link between files and file stream object
3. Open the files
4. Write data to files
5. Close the files

## Gain access to work with files
To gain access to work with files, we just need to import both `iostream` and  `fstream` header file using `#include <iostream>` and  `#include <fstream>`. `fstream` is a library that allows us to work with files.

## Create link between files and file stream object
After gaining access to work with files, we have to create link between files and ***file stream object*** before we interact with the files. How can we do it? `ofstream` class is the answer. There are also `ifstream` and `fstream`. However, for writing to files, we will focus on `ofstream` only.
### `ofstream`
`ofstream` is a class included in `fstream` library which used to create and write to files. `ifstream` and `fstream` are also classes from the same library but with different functionality. To create an object from `ofstream`(output file stream class), we use the following syntax:

`ofstream <name of object>`

In this example, we will use **outfile** as the name of object.

## Opening files
To open the file, we need to use the method from the `ofstream` object which is `open()`. The syntax is as following:

`outfile.open("<name/path of file>")`

**REMINDER: The exisiting data in file will be erased/overwritten if specified file exist. If the specified file not exist, a new file will be created.**

## Write data to files
To write/send data to files, the syntax is as simple as following:

`outfile << <data>`

## Close file
Lastly, don't forget to close the files after opening them. This is [why you should close it](https://stackoverflow.com/a/29536383):

>  There are not unlimited available File Descriptors (or in windows, the conceptually similar HANDLES). Every time you access a file ressource, even for reading, you are reducing the number of handles (or FD's) available to other processes. every time you close a handle, you release it and makes it available for other processes.

## Example Code
```cpp
#include <iostream>
#include <fstream>
#include <string>

int main(){
  
  ofstream outfile; //Create output file stream object
  
  string s1, s2; 
  
  // Recieve data from user
  cout << "First text: ";
  cin >> s1;

  cout << "Second text: ";
  cin >> s2;
  
  outfile.open("sample.txt"); //Open file
  
  // Write user data to file
  outfile << s1 << endl;
  outfile << s2 << endl;
  
  outfile.close(); // Close file
  
  return 0;
```
Assume `s1` is "Hello" and `s2` is "World", `sample.txt` will look like this after the code is executed:

```
Hello
World
```
