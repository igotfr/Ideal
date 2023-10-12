```rust
let a: [u8; 3] = #u8;3[1,2,3];
```
```rust
let v: [u8; vec] = #u8;vec[1,2,3];
v[1] = 7; // error
```
```rust
let v: [u8; mvec] = #u8;mvec[1,2,3];
v[1] = 7; // ok
```
