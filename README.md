# Create library

- create an object containing your functions
- include the code of this library in your file: Paste it or import_code(pathToMyLibManager)
- export the object with myLibManager.export(obj)

example (myCustomLibrary):
```
import_code("/lib/myLibManager")
myObj = {}
myObj.echo = function(str)
  print(str)
end function

myLibManager.export(myObj)
```

# Import a library

- include the code of this library in your file: Paste it or import_code(pathToMyLibManager)
- import the functions from a binary that exports functions using myLibManager and save them to a variable: var = myLibManager.import(pathToLib)

example:
```
import_code("/lib/myLibManager")
myCustomLibrary = myLibManager.import("/lib/myCustomLibrary")
myCustomLibrary.echo("Hello World")
```

# Restricted scope execution

WARNING!: restriction of built-in objects is an experimental feature, do not rely on it

Execute a function while restricting program variable access
use:
```
myLibManager.rsExecute(<reference:function>, <(optional) list:arguments>, <(optional) map:global variables>, <(optional) list:disabled built-in objects>, <(optional) bool:remove created files>, <(optional) str:path for created files>)
```

example:
```
import_code("/lib/myLibManager")

globalVar = "Hello World"

echo = function(str, otherStr)
  print(str)
  print(globalVar)
  return otherStr
end function

a = myLibManager.rsExecute(@echo, ["toPrint", "toReturn"], {"globalVar": globalVar})
print(a)
```

example output
```
toPrint
Hello World
toReturn
```
