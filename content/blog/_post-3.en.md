---
title: "The fun is starting"
date: 2026-05-20T22:36:19-03:00
tags: ["rust", "learning"]
---

Here I think I understood what `match` means. Basically it's a structure that compares the result of an expression. In the [previous post]({{% ref "/blog/_post-2"%}}), we saw that `match` is written right before the function, which was really strange to me, but this structure compares the result of the function and checks whether there is any compatibility of answers. At this point I believe it's almost the same as Java's `Comparator` or `Comparable`.

Following the guide, one thing that caught my attention was the ability to reuse variables with what Rust calls _'shadowing'_, top-notch excellent.
It explains the different integer types, I didn't understand very well but I believe it's something very similar to `Integer`, `int`, `Long` and `long` in Java, I suspect.

Man, but one thing I already loved, it's very dynamic and simple to build a structure and right after handle exceptions, very practical.

It's getting fun and I wanted to keep going but my time ran out!

Current code:

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

    let guess: u32 = guess.trim().parse().expect("Please type a number!");

    println!("You guessed: {guess}");

    match guess.cmp(&secret_number) {
        Ordering::Less => println!("Too small!"),
        Ordering::Greater => println!("Too big!"),
        Ordering::Equal => println!("You win!"),
    }
}
```
