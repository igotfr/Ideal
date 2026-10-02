## Rust
```rust
fn f(_: &mut u8) {}

fn main() {
  let mut a: u8 = 2;
  let b: &mut u8 = &mut a;
  let c: &mut u8 = &mut a;

  f(&mut a);
  f(c);
}
```
## Ideal
```rust
fn f(_: rmut u8) {}

fn main() {
  var a: u8 = 2
  let b: rmut u8 = a.rmut, c: rmut u8 = a->b.rmut

  f(a->b->c.rmut)
}
```