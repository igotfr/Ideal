```pony
let arr Array[4, u8] = Array[4, u8]{3, 5, 7, 9};
let arr Array[4, u8] = Array{3, 5, 7, 9};
let arr Array[4, u8] = [4, u8]{3, 5, 7, 9};
let arr Array[4, u8] = {3, 5, 7, 9};

let arr Array = Array[4, u8]{3, 5, 7, 9};
let arr Array = Array{3, 5, 7, 9};        // comptime_int
let arr Array = [4, u8]{3, 5, 7, 9};
let arr Array = {3, 5, 7, 9};             // comptime_int

let arr [4, u8] = Array[4, u8]{3, 5, 7, 9};
let arr [4, u8] = Array{3, 5, 7, 9};
let arr [4, u8] = [4, u8]{3, 5, 7, 9};    // class unidentified
let arr [4, u8] = {3, 5, 7, 9};           // class unidentified

let arr = Array[4, u8]{3, 5, 7, 9};
let arr = Array{3, 5, 7, 9};              // comptime_int
let arr = [4, u8]{3, 5, 7, 9};            // class unidentified
let arr = {3, 5, 7, 9};                   // comptime_int, class unidentified

// -----------------------------------------------------------------------------

let arr Array:4, u8 = Array:4, u8{3, 5, 7, 9};
let arr Array:4, u8 = Array{3, 5, 7, 9};
let arr Array:4, u8 = :4, u8{3, 5, 7, 9};
let arr Array:4, u8 = {3, 5, 7, 9};

let arr Array = Array:4, u8{3, 5, 7, 9};
let arr Array = Array{3, 5, 7, 9};        // comptime_int
let arr Array = :4, u8{3, 5, 7, 9};
let arr Array = {3, 5, 7, 9};             // comptime_int

let arr :4, u8 = Array:4, u8{3, 5, 7, 9};
let arr :4, u8 = Array{3, 5, 7, 9};
let arr :4, u8 = :4, u8{3, 5, 7, 9};      // class unidentified
let arr :4, u8 = {3, 5, 7, 9};            // class unidentified

let arr = Array:4, u8{3, 5, 7, 9};
let arr = Array{3, 5, 7, 9};              // comptime_int
let arr = :4, u8{3, 5, 7, 9};             // class unidentified
let arr = {3, 5, 7, 9};                   // comptime_int, class unidentified

// -----------------------------------------------------------------------------

let arr: [4]u8 = [4]u8{3, 5, 7, 9}; // Zig way
```

```pony
let arr List[u8] = List[u8]{3, 5, 7, 9};
let arr List[u8] = List{3, 5, 7, 9};
let arr List[u8] = [u8]{3, 5, 7, 9};
let arr List[u8] = {3, 5, 7, 9};

let arr List = Array[u8]{3, 5, 7, 9};
let arr List = Array{3, 5, 7, 9};        // comptime_int
let arr List = [u8]{3, 5, 7, 9};
let arr List = {3, 5, 7, 9};             // comptime_int

let arr [u8] = List[u8]{3, 5, 7, 9};
let arr [u8] = List{3, 5, 7, 9};

let arr = List[u8]{3, 5, 7, 9};
let arr = List{3, 5, 7, 9};              // comptime_int

// -----------------------------------------------------------------------------

let arr List:u8 = List:u8{3, 5, 7, 9};
let arr List:u8 = List{3, 5, 7, 9};
let arr List:u8 = :u8{3, 5, 7, 9};
let arr List:u8 = {3, 5, 7, 9};

let arr List = List:u8{3, 5, 7, 9};
let arr List = List{3, 5, 7, 9};         // comptime_int
let arr List = :u8{3, 5, 7, 9};
let arr List = {3, 5, 7, 9};             // comptime_int

let arr :u8 = List:u8{3, 5, 7, 9};
let arr :u8 = List{3, 5, 7, 9};

let arr = List:u8{3, 5, 7, 9};
let arr = List{3, 5, 7, 9};              // comptime_int
```

```pony
let map: Map[string, u8] = Map[string, u8]{"a": 3, "b": 5, "c": 7, "d": 9};
let map: Map[string, u8] = {"a": 3, "b": 5, "c": 7, "d": 9};
```
