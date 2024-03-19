```rust
let n = 2
let m = 2

match n {
  1 | m => print("1 or {n}"),
  let _ => print("any other")
}
```
```rust
class Point(x, y)

let p = Point(2, 3)

match p {
  Point(4, 5) => {}
  Point(let xp, 6 | 7) | let Point(xp, 5) => {}
  Point(let xp, let yp) | let Point(xp, yp) => {}
}
```
