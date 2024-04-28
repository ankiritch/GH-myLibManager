# Create library

Create an object containing your function references: {key: @functionReference}
include the code of this library in your file: Paste it or import_code(pathToMyLibManager)
export the object with myLibManager.export(obj)

example (myCustomLibrary):

import_code("/lib/myLibManager")
myObj = {}
myObj.echo = function(str)
  print(str)
end function

myLibManager.export(myObj)


# Import a library

include the code of this library in your file: Paste it or import_code(pathToMyLibManager)
import the functions from a binary that exports functions using myLibManager and save them to a variable: var = myLibManager.import(pathToLib)

example:

import_code("/lib/myLibManager")
myCustomLibrary = myLibManager.import("/lib/myCustomLibrary")
myCustomLibrary.echo("Hello World")
