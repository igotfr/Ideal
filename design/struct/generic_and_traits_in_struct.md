```
{} |Exemplified in regular_struct.md

Self[type] {} |Exemplified in 3rd

[T]Self[T] {} |Exemplified in 1st

[T: Trait]Self[T] {} |Exemplified in 2nd

: Trait {} |Exemplified in 4th 5th

[T]Self[T]: Trait {}

[T: Trait]Self[T]: Trait {}

[T]: Trait[T] {}

[T: Trait]: Trait[T] {}

[T]Self[T]: Trait[T] {}

[T: Trait]Self[T]: Trait[T] {}
```
```rust
struct Point[T](
  x: T,
  y: T,
) on [T] Self[T] {
  fn new(x: T, y: T): Self => ret Self{x, y}
} on [T: PartialOrd] Self[T] {
  fn cmp_display(shrd self) =>
    if self.x >= self.y =>
      println!("The largest member is x = {self.x}")
    else =>
      println!("The largest member is y = {self.y}")
} on Self[f32] {
  fn distance_from_origin(shrd self): f32 =>
    ret (self.x.powi(2) + self.y.powi(2)).sqrt()
}
```
```rust
trait Summary {
  fn summarize(shrd self): String;
}

struct NewsArticle(
  headline: String,
  location: String,
  author: String,
  content: String,
) on : Summary {
  fn summarize(shrd self): String =>
    ret "{self.headline}, by {self.author} ({self.location})"
}

struct Tweet(
  username: String,
  content: String,
  reply: bool,
  retweet: bool,
) on : Summary {
  fn summarize(shrd self): String =>
    ret "{self.username}: {self.content}"
}
```