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
var v: Vec<u8> = vec#u8![1,2,3];
// or
var v: Vec<u8> = vec![1,2,3];

v = vec![1,2,3,4]; // ok
v[1] = 7; // error
```
## Mutable Vector
```rust
var v: MutVec<u8> = mutVec#u8![1,2,3];
// or
var v: MutVec<u8> = mutVec![1,2,3];

v = vec![1,2,3,4]; // ok
v[1] = 7; // ok
```
