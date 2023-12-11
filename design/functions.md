## Functions
```rust
fn f(a: u8, b: f32): f32 {
  return a as f32 + b
}

f(4, 3.2);
```
## Methods
```rust
mtd (a: u8) m(b: 32): f32 {
  return a as f32 + b
}

4.m(3.2);
```
## Lambdas
```rust
lbd l(a: u8, b: f32): f32 {
  return a as f32 + b
}

// or immutable
lbd l(a: u8, b: f32): f32 = f;

l = g; // error

// or mutable
var lbd l(a: u8, b: f32): f32 = f;

l = g; // ok

l(4, 3.2);
```
## Method Lambdas
```rust
mlbd (a: u8) l(b: f32): f32 {
  return a as f32 + b
}

// or immutable
mlbd (a: u8) l(b: f32): f32 = f;

l = g; // error

// or mutable
var mlbd (a: u8) l(b: f32): f32 = f;

l = g; // ok

4.l(3.2);
```
