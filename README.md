CGF is a pure python control flow graph builder. It works by building the CFG from the abstract syntax tree generated by [Clang], and accessing it
through its [python bindings]to libclang.
 

### What is a CFG?
In a few words and quoting wikipedia, 
> A control flow graph (CFG) in computer science is a representation, using graph notation, of all 
paths that might be traversed through a program during its execution.

### What are libclang and the python bindings?Libclang: The C Interface to Clang provides a relatively small API that exposes facilities for parsing source code into an abstract syntax 
tree (AST), loading already-parsed ASTs, traversing the AST, associating physical source locations with elements within the AST, and other facilities that support Clang-based development tools.


And the python bindings, This module provides an interface to the Clang indexing library. It is a low-level interface to the indexing library which attempts to match the Clang API 
directly while also being "pythonic".


# Installation
: The installation is relatively simple and the only step that can lead to complications is locating libclang.
```
apt-get install clang
pip install -r requirements.txt
```

At this point you must locate libclang and perform a symbolic link as it appears in the lower capture. so
```
After this, you only have to indicate to the python bindings where the new 
symbolic link to libclang is located, to do this, you must open the **utils.py** file and modify the following line by entering the path where you have created the symbolic link:

```
Config.set_library_path('/usr/lib/llvm-4.0/lib') 
```


