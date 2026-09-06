## [Language] allow to initialize fields in class and struct bodies

https://github.com/dada-lang/dada/issues/261

in most (if not all) programming languages with `class` or `struct` is allowed to initialize a field directly at declaration in its block, something like:
```rust
class Cl(a: u8, b: u8) {
  c: u8 = 4
}

async fn main() {
  let cl: Cl = Cl{1, 2}
  cl.c # access 4
}
```
in Dada, when I try it I get :
```
c: u8 = 4
  |         ^ I don't know what to do with this, it appears to be extra
```
Examples of programming languages that works like this: Swift, Kotlin, C++, Python, Java, C#, Dart, Javascript

It would allow too pass arguments to parameters similar to functions:
```rust
class Cl(a: u8, b: u8) : (p1: u8, p2: u8) {
  c: u8 = p1 + p2
}

async fn main() {
  let cl: Cl = Cl{1, 2}(3, 4)
  cl.c # access c, which is p1 + p2, in this case: 7

  cl.p1 # error, p1 is not a field
}
```
Examples of programming languages that works like this: Kotlin, Dart

this proposal allow to initialize fields this way

## Correlated to
https://github.com/dada-lang/dada/issues/262