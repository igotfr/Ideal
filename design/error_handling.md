```rust
error NetworkError
error IOError

type UserError = NetworkError | IOError

fn f(): u8 ! UserError {
    if false => throw NetworkError
    if false => throw IOError
    return 6
}

fn main() {
    handle f() =>
      ok {
        0..5 {}
        5.. {}
      }
      err {
        NetworkError {}
        IOError {}
      }
}
```