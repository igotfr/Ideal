```rust
struct St(
  field1: u8,
  field2: u8,
  field3: u8
) {
  cons cn(field1, field2 = 6) [field3 = 8] {}

  // equivalent to
  fn cn(a: u8, b: u8 = 6): Self {
    Self{field1: a, field2: b, field3: 8}
  }
}

St#cn(8)
```
