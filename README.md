#Riack
Is a C client library for Riak.

##Precompiled
The easiest thing to do is just use the precompiled libraries you can download them from here http://kaspar.mobi/files/riack-binaries/
They where placed in git before but it turns out git is not the best for binaries that get updated often.

##Examples
I wan't this library to be as easy as possible to use, so all you need to get started is the shared library file and 2 headers!
To se examples of this look in the examples directory.
Remember you need to compile the library or download the precompiled files before the examples will run.

##Compilation
###Dependencies

####protobuf-c
Pure C bindings for google protocol buffers.
Download at http://code.google.com/p/protobuf-c/

to compile protobuf-c you first need to install Protocol Buffers find it here
http://code.google.com/p/protobuf/

On linux and Mac just do a 
```
./configure
make
sudo make install
```
On both protobuf libraries.

On Windows
Protocol Buffers follow the vsprojects/readme.txt in the downloaded the package.
protobuf-c I recommend using cmake however at the time of writing this there is a bug
which will give you a compile error if this is still the case visit 
http://code.google.com/p/protobuf-c/issues/list to find a solution.

####cmake
Riack uses cmake build system which means it can be compiled on most systems.
Make sure you have installed cmake if not find it here http://www.cmake.org/ or
if your fortunate enough to be an OS with a package manager just install it with that.

###Ready
Get a prompt and move to Riack top folder and do
```
cmake src/
```
This will generate make files, and you can run a make afterwards, unless your on windows
in which case I recommend generating a visual studio project this is done like this:

```
cmake src/ -G "Visual Studio 10"
```
Note on windows you might need to tell cmake where to find the Protobuf-C files
You can do this by passing some options to cmake which is hard to remember ;) I recommend 
to just edit src\cmake\Modules\FindProtoBufC.cmake lines 19 & 20.

##Tests
To run the test first input an ip/port in src/CMakeLists.txt line 4 & 5 and rerun cmake
When ready you can simply do a make test.
(on windows just choose the correct build target in Visual Studio)

##Disclamer
This is a sparetime project, so if you so a silly bug don't blame my employer, instead 
make a pull request ;)
