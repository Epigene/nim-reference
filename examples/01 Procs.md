## Proc definition and use

```nim
import sequtils

let numbers = @[1, 2, 3, 4, 5, 6]

let odd = filter(numbers, proc (x: int): bool = x mod 2 != 0)

assert odd == @[1, 3, 5]
```

```nim
import sequtils, future

let numbers = @[1, 2, 3, 4, 5, 6]

let odd = filter(numbers, (x: int) -> bool => x mod 2 != 0)

assert odd == @[1, 3, 5]
```
