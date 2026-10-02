---
title: "First application in Rust"
date: 2026-05-19T11:29:50-03:00
tags: ["rust", "learning"]
---

In this study session we followed (me, in this case) the documentation that leads us to build our first application in Rust. A guessing game where the user tries to guess a number from 1 to 100.
Throughout the tutorial we're shown how to install other libraries using Crate, editing the `Cargo.toml` file and adding the dependency that randomizes, which seems to me that Rust doesn't do natively and needs an external dependency for that ~~in Java it does, cof cof~~ right after we run the `Cargo build` command, the dependency we added to the `Cargo.toml` file (I read it: cargo tomoio), the Crate then downloads everything properly, preventing everything from breaking because, as explained in the doc, Rust saves it beforehand in the `Cargo.lock` file, just like Node does.

Then it starts to get a bit complicated because right after the `match` expression is used, and I didn't understand very well how it works because it's invoked in a quite strange way, you know:

```rust
  match guess.cmp(&secret_number) {
    // rest of the function
  }

```

Which is a bit crazy because that `guess` there is a variable we typed before. So I didn't understand anything, my time ran out and I'll continue in the next study session.

Code written so far:

```rust
use std::cmp::Ordering;
use std::io;

use rand::Rng;

fn main() {

    println!("Guess the number!");

    let secret_number = rand::thread_rng().gen_range(1..=100);

    println!("The secret number is: {secret_number}");

    let mut guess = String::new();

    io::stdin()
      .read_line(&mut guess)
      .expect("Failed to read line!");

    println!("You guessed: {guess}");

    match guess.cmp(&secret_number) {
        Ordering::Less => println!("Too small!"),
        Ordering::Greater => println!("Too big!"),
        Ordering::Equal => println!("You win!"),
    }
}


```
