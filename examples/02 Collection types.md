## Nim's collection types

### Array
Size can not be changed after declaration!

```nim
var list: array[3, int]

list[0] = 1
list[1] = 42

assert list[0] == 1
assert list[1] == 42
assert list[2] == 0
```

```nim
# idiomatic to use `low` and `high` for array loops
for i in list.low .. list.high:
  echo(list[i])
```

### Sequence

```nim
var list: seq[int] = @[] # empty seq's type must be specified
var list = @[4, 8, 15] # seq's type can be inferred

list[0] = 1
list.add(1) # can grow
assert list[0] == 1

# use the builder if you know the starting size
var list = newSeq[string](3)
assert list[0] == nil
list[2] = "c"
```

```nim
# Idiomatic to use `len` for sequence loops
for i in 0 .. <list.len:
  stdout.write($list[i] & " ")
```

### Set
Allows only unique values, and the type must be ordinal (countable)

```nim
var collection: set[int16]
assert collection == {}

let collection = {'a', 'x', 'r'}
assert 'a' in collection # the `in` keyword

# check bitwise intersection (*) or disjoint (^)
let collection = {'a', 'T', 'z'}
let isNotAllLowerCase = {'A' .. 'Z'} * collection == {}
assert(isNotAllLowerCase)
```
