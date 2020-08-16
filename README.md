## LUA2C 
converts Lua 5.1 source code to C API call code.

### Description

I forked from [davidm/lua2c](https://github.com/davidm/lua2c) and make it work with `clang`.
Please change this in [clua](https://github.com/thetrung/lua2c/blob/master/clua) script to fit your system.
including the `XCODE_PATH` for C header.

This tool converts *Lua source file >> C source file*
written **in terms of Lua C API calls**. Why I must emphasize this ?
Because it's far from Lua->C, indeed. A lot of work is needed 
to bring it into true meaning of `lua2c`. The compiler is written entirely in Lua, and no build/install is needed. 

### Usage

**- With Script :**

    lua lua2c.lua test/bisect.lua >> your_source.c

which generates a C file to standard output.

**- With `clua` :**
- To generate C source file > compile with `clang` > and run it : 

        ./clua hello.lua
        
- To generate > compile > run your_stuff, but with a given name :

        ./clua factorial.lua fac

- To generate C source file :

        ./clua --source factorial.lua               
        #=> factorial.c

- To compile the generated C source file :

        ./clua --compile factorial.lua
        #=> factorial binary
        
        ./factorial 

**NOTE**
I want to separate compile/source process to test my hack and see
how much the speed may be improved if we can transform lua->C function.
As in recent `fib.lua` test, the speed of executing `fib` as C native 
function could improve speed by ~4.5X compare to LuaJIT and ~50X compare
to Lua51.

### Performance
All I can say is, pretty poor. You may run this on your own to see.
For example, run `fib.lua` in example folder, you will see :

        - LuaJIT  : 28x
        - Lua@5.1 : 2.4x
        - Lua2C.  : 1x

#### Licensing
*(c) 2008 David Manura.  Licensed under the same terms as Lua (MIT
license).  See included LICENSE file for full licensing details.
Please post any patches/improvements.*

*(c) 2020 Trung Nguyen.  Licensed under the same terms as Lua (MIT
license).  See included LICENSE file for full licensing details.
Please post any patches/improvements.*
