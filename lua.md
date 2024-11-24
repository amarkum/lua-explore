
# Lua Examples with Explanations

This README provides detailed examples of Lua programming features along with explanations. Each section demonstrates a specific aspect of the language.

## Full Lua Script with Features

```lua
-- Variables and Data Types
local number = 10        -- A number variable
local text = "Lua"       -- A string variable
local isAlive = true     -- A boolean variable
local list = {1, 2, 3}   -- A table representing a list (array)
print("Number:", number, "Text:", text, "Alive:", isAlive)
```

### Explanation:
- Lua uses `local` to define variables with local scope.
- Data types include numbers, strings, booleans, and tables (arrays or dictionaries).

---

```lua
-- Control Structures
local age = 18
if age >= 18 then
    print("Adult")       -- If condition is true
else
    print("Minor")       -- Else condition
end
```

### Explanation:
- `if-then` statements are used for conditional logic.
- `>=` checks if a value is greater than or equal to another.

---

```lua
-- Loops
for i = 1, #list do       -- Iterate from 1 to the length of the list
    print("List item:", list[i])
end
```

### Explanation:
- Lua loops include `for`, `while`, and `repeat`.
- `#list` gives the length of the table (array).

---

```lua
-- Function
function greet(name)
    return "Hello, " .. name .. "!"  -- Concatenate strings with `..`
end
print(greet("Alice"))
```

### Explanation:
- Functions are defined using the `function` keyword.
- String concatenation is done with `..`.

---

```lua
-- Tables
local person = {name = "John", age = 30}  -- Table with key-value pairs
print(person.name .. " is " .. person.age .. " years old.")
```

### Explanation:
- Tables in Lua can act as arrays or dictionaries.
- Access dictionary-style tables with `table.key`.

---

```lua
-- Metatables
local t1 = {x = 1, y = 2}
local t2 = {x = 3, y = 4}
setmetatable(t1, {
    __add = function(a, b)
        return {x = a.x + b.x, y = a.y + b.y}  -- Define addition behavior
    end
})
local result = t1 + t2
print("Result x:", result.x, "y:", result.y)
```

### Explanation:
- Metatables allow customization of table behavior.
- `__add` defines how the `+` operator works for tables.

---

```lua
-- Coroutines
function exampleCoroutine()
    print("Coroutine started")
    coroutine.yield()   -- Pause execution
    print("Coroutine resumed")
end
local co = coroutine.create(exampleCoroutine)
coroutine.resume(co)    -- Start coroutine
coroutine.resume(co)    -- Resume coroutine
```

### Explanation:
- Coroutines allow functions to be paused and resumed.
- Useful for cooperative multitasking.

---

```lua
-- File Handling
local file = io.open("example.txt", "w")  -- Open file in write mode
file:write("Hello, Lua!")                -- Write to file
file:close()                             -- Close file
```

### Explanation:
- `io.open` is used to open a file.
- File modes include `"w"` (write), `"r"` (read), and `"a"` (append).

---

```lua
-- Object-Oriented Programming
local Animal = {}                         -- Define a table as a class
function Animal:new(name)
    local obj = {name = name}             -- Create an object
    self.__index = self
    setmetatable(obj, self)               -- Set metatable
    return obj
end
function Animal:speak()
    print("I am " .. self.name)
end
local dog = Animal:new("Dog")
dog:speak()
```

### Explanation:
- Lua supports OOP using tables and metatables.
- `self` refers to the object instance.
- `setmetatable` associates a table with a metatable.

---

## How to Run the Code
1. Save the script in a file (e.g., `script.lua`).
2. Install Lua on your system if not already installed.
3. Run the script using the command: `lua script.lua`.

This README provides a comprehensive guide to Lua basics and demonstrates its powerful features.
