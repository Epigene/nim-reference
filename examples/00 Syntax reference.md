## Nim syntax reference

### Assignment
```nim
constnst x = 1 # Compile-time constant
let y = "Hi" # Immutable binding
var z = [1, 2, 3] # Mutable variable
```

### Calls
```nim
proc name(param: int): ReturnType = body

method name(param: float): ReturnType = body

iterator items(list: seq[int]): int = body

template name(param: typed) = body

macro name(param: string): untyped = body
```

### Flow control
```nim
if x > 5:
  body
elif y == "Hello":
  body
else:
  body
```

```nim
case x
of 1:
  body
of 2, 3: body
of 4..10:
  body
else
  body
```

```nim
# A compile-time check to skip code, usually tests
when isMainModule:
  block:
    let v1 = "a"
    let v2 = "b"

    doAssert v1 == v2
```

### Loops
```nim
for item in list:
  body 
```

```nim
for i in 0..<len(list):
  body
```

```nim
while x == 5:
  if y.len > 0:
    break
  else:
    continue
```

```nim
try:
  raise err
except Exception as exc:
  echo(exc.msg)
finally: discard
```
