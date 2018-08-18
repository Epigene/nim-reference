## User-defined sypes in Nim

### Objects
```nim
# define
type
  Dog = object
    name: string
    age: int  

# use
var Dog: Dog
var Dog = Dog(name: "Neo", age: 28)
```

### Tuples
```nim
# define
type
  Point = tuple[x, y: int]
  Point2 = (int, int)
  
# use, key names irrelevant
let pos: Point = (x: 100, y: 50)
doAssert pos == (100, 50)
```

### Enums
```nim
type
  Chem = enum
  chemH,
  chemC,
  chemFe

let chemical: Chem = chemFe

type
  Chem {.pure.} = enum
    H, C, Fe

let chemical = Chem.H
```
