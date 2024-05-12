<style>
*{
  font-family: Pragmasevka Nerd Font;
}
</style>

# Comments
```lua
-- Single line comment

--[[

multi
line comment

]]
```

# Print
```lua
print("Something")
```

*Results:* `Something`

## String Concatenation
```lua
print ("My name is " .. "Aditya Gautam")
```

*Results:* `My name is Aditya Gautam`

# Data Types

- Int / Floats
- Nil
- String
- Boolean
- Tables { }

# Variables
```lua
local x
print(x)

x = nil
print(x)
```

*Results:*
```
nil
nil
```

- Local Scope Variables are not allowed to be reused outside of its scope ( file / function )

```lua
var1 = "this is a global variable"
_G.var2 = "this is how you specifically define a global var"
```

*Results:*
```
```
# Multi-line Strings
```lua
local str = [[
This
is
a
multi
line
string!
]]
print(str)
```

*Results:*
```
This
is
a
multi
line
string!

```

# Multiple Variables In a Single Line
```lua
local one, two, three = "one", 2, false
print(one, two, three)
```

*Results:* `one	2	false`

# Strings
```lua
local name = "Aditya Gautam"
print(#name)

local x = #"something"
print(x)

local num = 20
local str = tostring(num)

print(num, str)
print(type(num), type(str))

print("My\t\vName\t\vIs\t\vAditya") -- works in a terminal
```

*Results:*
```
13
9
20	20
number	string
My	Name	Is	Aditya
```

#\<variable\> returns length of the variable

## Methods
```lua
local name = "Aditya Gautam"
print(name)
print(string.lower(name))
print(string.upper(name))
print(string.len(name))
print(#name)
```

*Results:*
```
Aditya Gautam
aditya gautam
ADITYA GAUTAM
13
13
```

# Mathematical Operations
```lua
print ( 5 + 3 )
print ( 5 - 3 )
print ( 5 * 3 )
print ( 5 / 3 )
print ( 5 ^ 3 )
print ( 5 % 3 )
```

*Results:*
```
8
2
15
1.6666666666667
125.0
2
```

## Methods
```lua
print(math.min(10,5,100,12.34,102))
print(math.max(10,5,100,12.34,102))
print(math.ceil(12.01))
print(math.floor(12.99))
print(math.random())
print(math.random(100))
print(math.random(10,50))

-- Random, however, could theoretically get the same thing twice
-- How to prevent that, you might ask, eh?
-- Use a seed

-- Updates every second
math.randomseed(os.time())
print(math.random())

```

*Results:*
```
5
102
13
12
0.82087092343667
38
20
0.32910260030208
```

# Logical And Comparison Operators
- And
- Or
- Not
- ==
- ~=
- <
- \>
- <=
- \>=

# If Loop
```lua
local num = 0
if num < 5 then
  print("something")
end
```

*Results:* `something`

```lua
local age = 18
if age < 18 then
  print("Child L")
elseif age == 18 then
  print("demn big boiiiii")
else
  print("ok")
end
```

*Results:* `demn big boiiiii`

# Ternary Operator
```lua
local age = 19
local status = age > 18 and "Adult" or "Child"
print(status)
```

*Results:* `Adult`

# LOOPS
- For
- While
- Repeat

```lua
for i = 1,5 do
  print(i)
end
```

*Results:*
```
1
2
3
4
5
```

```lua
for i = 5,1,-2 do
  print(i)
end
```

*Results:*
```
5
3
1
```

```lua
local count = 0
while count < 10 do
  count = count + 1
  if count == 8 then
    break
  end
  print(count)
end
```

*Results:*
```
1
2
3
4
5
6
7
```
```lua
local num = 0
repeat 
  num = num + 1
  print(num)
until num >= 5
```

*Results:*
```
1
2
3
4
5
```

# INPUT
```lua
print("Something: ")
local ans = io.read()
print(ans)
```
- Print stmts give an extra \n char at the end
- To resolve that, use io.write to write to the stdout

```lua
io.write("Something: ")
local ans = io.read()
print(ans)
```

# TABLES
```lua
local tbl = { "1", "2", "3", "something", { "another", "table" }}
print(tbl)
for i = 1, #tbl, 1 do
  print(tbl[i])
end
print(tbl[5][1])
print(tbl[9])
```

*Results:*
```
table: 0x618f088bdf90
1
2
3
something
table: 0x618f088bce80
another
nil
```

- NOTE: Indexing in Lua is from 1 rather than 0 like other languages
- Does not give "out of range" error
- rather, gives a nil value

```lua
local nums = { 1,3,4 }
table.insert(nums, 5)
for i = 1,#nums do
  print(nums[i])
end
print()
table.insert(nums, 3, 7) -- 2nd arg is index
for i = 1,#nums do
  print(nums[i])
end
print()
table.remove(nums, 3) -- removes by index
for i = 1,#nums do
  print(nums[i])
end
print()
```

*Results:*
```
1
3
4
5

1
3
7
4
5

1
3
4
5

```
