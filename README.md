# Foxit Quick PDF Library
## Python interface
### Introduction
Foxit Quick PDF Library is a popular SDK for working with PDF documents, it is available from www.debenu.com

The files in this repository contain classes that make it as easy as possible to control Quick PDF Library using the Python programming language. Interface classes are provided for Windows (DLL), macOS (Dylib) and Linux (.so shared library).

### Setup
Simply import the Python file and then create an instance of the class.

The class will dynamically connect to the QPL binary, so it will need to kknow the binary location. The easiest is to simply put the binary in the same directory as your Python script and create the class without any parameters. Alternatively a directory path can be provided, or the actual path to the QPL binary.

```python
# On Windows use FoxitQPLDLL1611, on macOS use FoxitQPLmacOS1611 and on Linux use FoxitQPLLinux1611
import FoxitQPLDLL1611 as FoxitQuick

# Create an instance of the class
# No parameter is supplied so the script will look for the QPL binary in the same directory
qp = FoxitQuick.PDFLibrary()
```

### Using the library
The first step is to enable the software, so you'll need a license key to unlock the library. Pass this license key to the UnlockKey function and make sure the result is 1, indicating success. Once the library has been unlocked you can use any of the QPL functions, see the Function Reference and Developer Guide included with the software distribution.

```python
licenseKey = "..."
if qp.UnlockKey(licenseKey) == 1:
  qp.DrawText(100, 700, "Hello world")
  qp.SaveToFile("test_output.pdf")
```
