## GDB custom pretty printers

Taken from the default gdb's `libstdcxx` pretty printers, with some modifications.

### Improvements

* Implement end-iterator detection for `StdDebugIteratorPrinter`
* Better output for std::bitset / std::set _(default: `[0]: 1,[1]: 2`, improved: `{1, 2}`, like an array)_
* Remove some `__debug` from output, in debug compilation _(for example `std::__debug::vector` → `std::vector`)_
* Add `std::array` printer _(the default one shows the internal member name `_M_elems` in the output)_
* Hide capacity data for vector

### Installation

Follow the instruction in [c++ - How to pretty-print STL containers in GDB? - Stack Overflow](https://stackoverflow.com/questions/11606048/how-to-pretty-print-stl-containers-in-gdb).

Change [`sys.path`]( https://docs.python.org/3/library/sys.html#sys.path) to point to the correct location. 

### Original source

The original ones can be found somewhere in `/usr/share/gcc-11.1.0/python/libstdcxx/`
(specific path depends on distribution).

Also see [gdb source code](https://github.com/gcc-mirror/gcc/blob/releases/gcc-6.3.0/libstdc%2B%2B-v3/python/libstdcxx/v6/printers.py).

