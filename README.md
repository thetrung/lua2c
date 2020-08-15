## LUA2C 
converts Lua 5.1 source code to C API call code.

### Description

I forked from `davidm/lua2c` and make it work with `clang`.
Please change this in `clua` script to fit your system.
including the `XCODE_PATH` for C header.

This tool converts *Lua source file >> C source file*
written **in terms of Lua C API calls**. Why I must emphasize this ?
Because it's far from Lua->C, indeed. A lot of work is needed 
to bring it into true meaning of `lua2c`.

The compiler is written entirely in Lua, and no build/install is needed. 

Original work was from [davidm/lua2c](https://github.com/davidm/lua2c)
please visit for any related information or License.

### Usage

**- With Script :**

    lua lua2c.lua test/bisect.lua >> your_source.c

which generates a C file to standard output.

**- With `clua` :**
- To generate C source file > compile with `clang` > and run it : 

        ./clua -C test/bisect.lua

- To generate C source file > compile with `clang` :

        ./clua -c lua2c.lua               # compile lua2c binary
        ./lua2c examples-lua/bisect.lua   # test

- To generate only C source file :

        ./clua -C lua2c.lua lua2cc.c

- To generate > compile > run your_stuff, but with a given name :

        ./clua examples-lua/factorial.lua factorial


#### Licensing
*(c) 2008 David Manura.  Licensed under the same terms as Lua (MIT
license).  See included LICENSE file for full licensing details.
Please post any patches/improvements.*

*(c) 2020 Trung Nguyen.  Licensed under the same terms as Lua (MIT
license).  See included LICENSE file for full licensing details.
Please post any patches/improvements.*
