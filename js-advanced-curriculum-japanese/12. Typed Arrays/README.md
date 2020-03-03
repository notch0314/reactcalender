# **Introduction**

Typed Arrays are a relatively recent addition to browsers, born out of the need to have an efficient way to handle 
binary data in WebGL. A Typed Array is a slab of memory with a typed view into it, much like how arrays work in C.
Because a Typed Array is backed by raw memory, the JavaScript Engine can pass the memory directly to native libraries
without having to painstakingly convert the data to a native representation. And as a result, Typed Arrays perform
a lot better.

Typed Arrays Views act like single-type arrays to a segment of an ArrayBuffer. There are views for all the usual
numeric types, with self-descriptive names like Float32Array, Float64Array, Int32Array and others. There is also
a special View which has replaced the pixel array type in Canvas's ImageData: Uint8ClampedArray.

DataView is the second type of view and it is meant for handling heterogeneous data. Instead of having an array-like API, 
the DataView object provides you a get/set API to read and write arbitrary data types at arbitrary byte offsets. 
DataView works great for reading and writing file headers and other such struct-like data.
