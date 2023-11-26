## Array
```rust
var a: [u8; 3] = #u8;3[1,2,3];
// or
var a: [u8; 3] = #u8[1,2,3];
// or
var a: [u8; 3] = [1,2,3];
```
## Vector
```rust
var v: [u8; vec] = #u8;vec[1,2,3];
// or
var v: [u8; vec] = #vec[1,2,3];

v = #vec[1,2,3,4]; // ok
v[1] = 7; // error
```
## Mutable Vector
```rust
var v: [u8; mvec] = #u8;mvec[1,2,3];
v[1] = 7; // ok
```
