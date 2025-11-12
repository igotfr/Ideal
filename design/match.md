```rust
let n = 2
let m = 2

match n {
  1 | m => print("1 or {n}"),
  let _ => print("any other")
}
```
```rust
struct Point(x, y)

let p = Point{2, 3}

match p {
  Point{4, 5} => {}
  Point{let xp, 6 | 7} | Point{let xp, 8..=10} | plet Point{xp, 11} => {}
  Point{let xp, let yp} | plet Point{xp, yp} => {}
}
```
