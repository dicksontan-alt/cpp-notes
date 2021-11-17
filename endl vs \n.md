# endl vs \n 

Examine the following codes:

```cpp
#include <iostream>
using namespace std;

int main(){
    cout<<"I am"<<endl;
    cout<<"using endl";
    
    return 0;
}
```

```cpp
#include <iostream>
using namespace std;

int main(){
    cout<<"I am \n"<<endl;
    cout<<"using \\n"; //escape special characters using \
    
    return 0;
}
```

Both of the codes have the same function - they **insert a new line**. If so what are the differences using `endl` and `\n`?

## Differences

The key differences between `endl` and `\n` is `endl` ***causes a flushing of the output buffer*** every time it is called while `\n` **doesn't**. It will ***flush only once*** at the end of the program.

## Buffer flush

In simple words, buffer flush is the **transfer of computer data from a temporary storage area to computer permanent memory**. As an example, if we make any changes in a file, the changes we see on one computer screen are stored temporarily in a buffer. When we save the file, the changes will be flushed from the buffer into permanent storage (eg: hard disk)

## Which one should I use?

This is the answer I found on [StackOverflow](https://stackoverflow.com/questions/213907/stdendl-vs-n):

> The only difference is that [`std::endl`](http://en.cppreference.com/w/cpp/io/manip/endl) flushes the output buffer, and `'\n'` doesn't. If you don't want the buffer flushed frequently, use `'\n'`. If you do (for example, if you want to get all the output, and the program is unstable), use `std::endl`.

In conclusion, using which one is based on your needs and also your preferences. 

## References

[What is the difference between endl and \n in C++?](https://www.educative.io/edpresso/what-is-the-difference-between-endl-and-n-in-cpp)

[What does buffer flush means in C++ ?](https://www.geeksforgeeks.org/buffer-flush-means-c/)

