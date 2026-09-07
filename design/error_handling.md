```rust
error NetworkError
error IOError

type UserError = NetworkError | IOError

fn f(): u8 ! UserError {
  if false => throw NetworkError
  if false => throw IOError
  ret 6
}

fn main() {
  handle f() {
    0#~5 {}
    5#~ {}
  } err {
    NetworkError {}
    IOError {}
  }
}
```