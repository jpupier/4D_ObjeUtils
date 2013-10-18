##ObjUtils##

A 4D component that wraps calls to the JSON commands in Miyako's OAuth plugin.  The 4DB file is currently a v12 structure.

You can download Miyako's plugin [here](https://github.com/miyako/4d-plugin-oauth).

Sorry no example on here yet, will get something on here soon.

### Startup and prefs and error handling

* Obj_StartupInit   //gotta call on startup
* Obj_AlertIfErrOn 
* Obj_AlertIfErrOff 
* Obj_ResolveDotsOn 
* Obj_ResolveDotsOff 
* Obj_ErrGetLast   //returns true if there was an error, clears the last error, pass pointer to text to get error name

### JSON commands

* Obj_JsonParseText   //if there is a problem parsing, the returned ref will be ""
* Obj_JsonParseBlob 
* Obj_JsonParseDoc 
* Obj_JsonStringify 
* Obj_JsonBlobify 
* Obj_JsonToPasteboard 

### Objects

* Obj_New 
* Obj_Named   //if doesn't exist create, otherwise just get it
* Obj_Copy 
* Obj_Retain   //if put in another object, it won't get released when that parent object gets released
* Obj_Release 
* Obj_ReleaseAllForProcess 
* Obj_ReleaseAll 
* Obj_NodesInMemory 
* Obj_Exists 

### Object properties

* Obj_PropIsDefined 
* Obj_PropCount 
* Obj_PropNameByPosition 
* Obj_PropValueType 
* Obj_DeleteProp 

### Dot notation
the getters can use dot notation like this:   
Obj_GetText ($Obj;"hey.cool")

cannot access the individual elements of primitive arrays like Text or Long arrays but you can access the elements of arrays of objects or arrays like this (ref is 1 based):   
Obj_GetText ($Obj;"ArrayOfObjects[2].something") //gets the something value in the second object in the array of objects

### Getters

* Obj_GetVar 
* Obj_GetText 
* Obj_GetLong 
* Obj_GetReal 
* Obj_GetBool 
* Obj_GetDate 
* Obj_GetBlob 
* Obj_GetArrayText 
* Obj_GetArrayLong 
* Obj_GetArrayReal 
* Obj_GetArrayBool 
* Obj_GetArrayDate 
* Obj_GetObj 
* Obj_GetArrOfOA 
* Obj_GetValueIsNull 

### Setters

* Obj_SetVar 
* Obj_SetText 
* Obj_SetLong 
* Obj_SetReal 
* Obj_SetBool 
* Obj_SetDate 
* Obj_SetBlob 
* Obj_SetArrayText 
* Obj_SetArrayLong 
* Obj_SetArrayReal 
* Obj_SetArrayBool 
* Obj_SetArrayDate 
* Obj_SetObj 
* Obj_SetArrOfOA 
* Obj_SetNull 

### Array of objects/arrays

note that an object of objects/arrays is easy, just use something like Obj_SetObj or Obj_SetTextArray

* ObjArrOfOA__New 
* ObjArrOfOA_AppendObj 
* ObjArrOfOA_AppendTextArray   //we can't set an array at a specific position in an an array of arrays, can only append
* ObjArrOfOA_AppendLongArray 
* ObjArrOfOA_AppendRealArray 
* ObjArrOfOA_AppendBoolArray 
* ObjArrOfOA_AppendDateArray 
* ObjArrOfOA_AppendArray 
* ObjArrOfOA_GetElemRefs   //if the elem is an object, this is the handle for the object, if array need to use Obj_ArrOf_ElemRefTo_X_Array 
* ObjArrOfOA_GetElemType 
* ObjArrOfOA_ElemRefToTextArray 
* ObjArrOfOA_ElemRefToLongArray 
* ObjArrOfOA_ElemRefToRealArray 
* ObjArrOfOA_ElemRefToBoolArray 
* ObjArrOfOA_ElemRefToDateArray 
* ObjArrOfOA_ElemRefToArray 



Copyright 2013 CoreBits DataWorks LLC  
http//corebitsdw.com  
Released under the MIT license (included in distribution in MIT LICENSE.txt)  
