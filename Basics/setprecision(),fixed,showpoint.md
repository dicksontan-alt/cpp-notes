# setprecision(),fixed,showpoint

## setprecision(int n)	

`setprecision(n)` is a manipulator function ( built-in function defined in `<iomanip>` header file ) in C++ which is used to control the **number of significant digits** (n). The following code demonstrates the function:

```cpp
#include <iostream>
#include <iomanip> // to enable setprecision()
using namespace std;

int main(){
    double num = 12.5678;
    cout << setprecision(6) << num << endl; //default is setprecision(6)
    cout << setprecision(5) << num << endl;
    cout << setprecision(4) << num << endl;
    cout << setprecision(3) << num << endl;
    cout << setprecision(2) << num << endl;
    cout << setprecision(1) << num << endl;
    
    return 0;
}
```

Output:

```
12.5678
12.568
12.57
12.6
13
1e+01
```

As we see, it's fine when we set the precision from 6-2. However, when it comes to `setprecision(1)` which the precision of a number is set to a lower value, numbers tend to be printed in scientific notation. In this case, this is where `fixed` comes in handy.

## Using setprecision() with fixed

When `fixed` and `setprecision` manipulators are used together, the value specified by the `setprecision` manipulator will be the **number of digits to appear after the decimal point**, not the number of significant digits. For example, look at the following code:

```cpp
#include <iostream>
#include <iomanip> // to enable setprecision()
using namespace std;

int main(){
    double num = 12.5678;
    cout << fixed //using fixed manipulator
    cout << setprecision(6) << num << endl; 
    cout << setprecision(5) << num << endl;
    cout << setprecision(4) << num << endl;
    cout << setprecision(3) << num << endl;
    cout << setprecision(2) << num << endl;
    cout << setprecision(1) << num << endl;
    
    return 0;
}
```

Output:

```
12.567800
12.56780
12.5678
12.568
12.57
12.6
```

Because the `fixed` manipulator is used, the `setprecision` manipulator will cause the number to be displayed with specified `n` digits after the decimal point.

## showpoint

By default, floating-point numbers are not displayed with trailing zeros. `showpoint` is also a manipulator function which padded the number with trailing zeros. Let's look at the following code:

```cpp
include <iostream>
#include <iomanip>
using namespace std;

int main()
{
    double x = 123.4, y = 456.0;
    cout << "Without showpoint" << endl;
    cout << x << endl;
    cout << y << endl;

    cout << showpoint << endl;
    cout << "With showpoint" << endl;
    cout << x << endl;
    cout << y << endl;

    return 0;
}
```

Output:

```
Without showpoint
123.4
456

With showpoint
123.400
456.000
```

As we can see, `showpoint ` padded the number with trailing zeros.

#### <u>NOTE!</u>

With most compilers, trailing zeros are displayed automatically when the `setprecision` and `fixed` manipulators are used together.

## References

[Starting Out with C++ from Control Structures to Objects by Tony Gaddis (9th edition)](https://www.pearson.com/us/higher-education/program/Gaddis-Starting-Out-with-C-from-Control-Structures-to-Objects-Plus-My-Lab-Programming-with-Pearson-e-Text-Access-Card-Package-9th-Edition/PGM335156.html)