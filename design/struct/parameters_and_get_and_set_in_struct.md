```rust
struct St(a: u8, b: u8) : (p1: u8, p2: u8) {
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
}

fn main() {
  let st: St = St{1, 2}(3, 4)

  println!(st.p1) // error, p1 is not a field

  println!(st.f) // error, f is private

  println!(st.f_get()) // prints 8

  println!(st.c) // access c, which is p1 + p2, in this case: 7

  println!(st.d) // access d, which is a + b, in this case: 3

  println!(st.e) // access e, which is a + b, in this case: 3

  st.a = 7

  println!(st.d) // continues being 3

  println!(st.e) // now is 9
}
```