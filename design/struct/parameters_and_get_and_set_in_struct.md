```rust
struct St(a: u8, b: u8) : (p1: u8, p2: u8) {
  field_non_instantiable_initialized: u8 = 4
  c: u8 = p1 + p2
  d: u8 = a + b
  e: u8 => {
    get => a + b
    set => c = newValue
    // or
    set(newC) => c = newC
  }
  priv f = p1 + 5

  mtd (self) f_get(): u8 => f

  ctor cn(a, b = 6) [c = 8] {}

  // equivalent to
  //fn cn(a: u8, b: u8 = 6): Self => ret Self{a, b, 8}
  fn cn(a: u8, b: u8 = 6): Self => ret Self{a: a, b: b, c: 8}

  mtd (shrd self) sum_fields(): u8 => self.a + self.b + self.c + self.field_non_instantiable_initialized

  fn check(value: u8): String =>
    ret if value > 120 -> "Invalid value"
    else -> "ok"
}

fn main() {
  let st: St = St{1, 2}(3, 4)

  println!(st.p1) // error, p1 is not a field

  println!(st.f) // error, f is private

  println!(st.f_get()) // prints 8

  println!(st.field_non_instantiable_initialized) // prints 4

  println!(st.c) // access c, which is p1 + p2, in this case: 7

  println!(st.d) // access d, which is a + b, in this case: 3

  println!(st.e) // access e, which is a + b, in this case: 3

  st.a = 7

  println!(st.d) // continues being 3

  println!(st.e) // now is 9
}
```
