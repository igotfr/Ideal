Dada doesn't need to be a completely new language, it can just be a syntax "correction" of Rust with some syntax sugar

in Dada:
```swift
class Rectangle(
    width: u32,
    height: u32,
) {
    fn square(size: u32) -> Self {
        Self(
            width: size,
            height: size,
        )
    }

    fn area(shared self) -> u32 {
        self.width * self.height
    }

    fn can_hold(shared self, other: shared Rectangle) -> bool {
        self.width > other.width && self.height > other.height
    }

    fn width(shared self) -> bool {
        self.width > 0
    }
}
```

in Rust:
```rust
#[derive(Debug)]
struct Rectangle {
    width: u32,
    height: u32,
}

impl Rectangle {
    fn square(size: u32) -> Self {
        Self {
            width: size,
            height: size,
        }
    }

    fn area(&self) -> u32 {
        self.width * self.height
    }

    fn can_hold(&self, other: &Rectangle) -> bool {
        self.width > other.width && self.height > other.height
    }

    fn width(&self) -> bool {
        self.width > 0
    }
}
```
___
in Dada:
```swift
class Point<T>(
    x: T,
    y: T,
) <T>$<T> {
    fn new(x: T, y: T) -> Self {
        Self(x, y)
    }
} <T: PartialOrd>$<T> {
    async fn cmp_display(shared self) {
        if self.x >= self.y {
            print("The largest member is x = {self.x}").await
        } else {
            print("The largest member is y = {self.y}").await
        }
    }
} $<f32> {
    fn distance_from_origin(shared self) -> f32 {
        (self.x.powi(2) + self.y.powi(2)).sqrt()
    }
}
```

in Rust:
```rust
struct Point<T> {
    x: T,
    y: T,
}

impl<T> Point<T> {
    fn new(x: T, y: T) -> Self {
        Self { x, y }
    }
}

impl Point<f32> {
    fn distance_from_origin(&self) -> f32 {
        (self.x.powi(2) + self.y.powi(2)).sqrt()
    }
}

impl<T: Display + PartialOrd> Point<T> {
    fn cmp_display(&self) {
        if self.x >= self.y {
            println!("The largest member is x = {}", self.x);
        } else {
            println!("The largest member is y = {}", self.y);
        }
    }
}
```
___
in Dada:
```swift
trait Summary {
    fn summarize(shared self) -> String;
}

class NewsArticle(
    headline: String,
    location: String,
    author: String,
    content: String,
) : Summary {
    fn summarize(shared self) -> String {
        "{self.headline}, by {self.author} ({self.location})"
    }
}

class Tweet(
    username: String,
    content: String,
    reply: bool,
    retweet: bool,
) : Summary {
    fn summarize(shared self) -> String {
        "{self.username}: {self.content}"
    }
}
```

in Rust:
```rust
pub trait Summary {
    fn summarize(&self) -> String;
}

pub struct NewsArticle {
    pub headline: String,
    pub location: String,
    pub author: String,
    pub content: String,
}

impl Summary for NewsArticle {
    fn summarize(&self) -> String {
        format!("{}, by {} ({})", self.headline, self.author, self.location)
    }
}

pub struct Tweet {
    pub username: String,
    pub content: String,
    pub reply: bool,
    pub retweet: bool,
}

impl Summary for Tweet {
    fn summarize(&self) -> String {
        format!("{}: {}", self.username, self.content)
    }
}
```
