# LuaJIT-2.0.5

LuaJIT is a Just-In-Time (JIT) compiler for the Lua programming language.

Project Homepage: http://luajit.org/

LuaJIT is Copyright (C) 2005-2017 Mike Pall.
LuaJIT is free software, released under the MIT license.
See full Copyright Notice in the COPYRIGHT file or in luajit.h.

## Fibonacci Test

Run the `fibonacci.lua` use `luajit` on Windows:

```bash
cd test
.\fibonacci_luajit.bat
```

## fibonacci.lua

Source code of `fibonacci.lua`:

```lua
function fibonacci(n)
    if n >= 3 then
        return fibonacci(n - 2) + fibonacci(n - 1)
    else
        return 1
    end
end

function main()
    print("Enter a number [1-45]: ")
    local n = io.read("*number")

    print("");
    local startTime = os.clock()
    local fib_n = fibonacci(n)
    local endTime = os.clock()

    print("fibonacci(40) = "..fib_n.."\n")
    print("Used time: "..(endTime - startTime).." seconds")
end

main()
```

## Test Result

```bash
Enter a number [1-45]:
40

fibonacci(40) = 102334155

Used time: 0.53 seconds
```
