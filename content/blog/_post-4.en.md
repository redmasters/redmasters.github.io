---
title: "Program Complete!"
date: 2026-05-24T20:49:18-03:00
tags: ["rust", "learning"]
---
Today I finished the 'guessing game', the Rust program from the tutorial. I'm still stunned by how simple it is to handle errors in Rust and to use ``loop``.

### Loop

Recalling that, in the previous post we had a brief handling or conversion of numbers there, in this case from String to integers(?). In this session I learned another incredible thing in Rust, the use of ``loop``.

And it's so simple that I spent a few minutes staring at the screen to see what the catch was, because using ``loop`` in Rust is basically:

```rust
loop {
 //codigo
}
```

I kept looking at it and asking myself where it would break, because it wasn't possible. But it is possible, simple and direct. It's a loop and that's it, you decide whether it will stay infinite or stop; in the case of the tutorial program, the ``break`` happens when you get the number right.

I believe that in this session of the tutorial, the use of ``match``, ``let``, ``loop`` and ``mut`` were well exemplified. The ``match`` mainly where, thanks to it, the program is able to validate the user's value input; if it is different from a number it returns a ``Result`` of type ``Err`` and continues in the ``loop``, otherwise it returns the number and follows the code flow.

Very interesting the learning so far, I'm going to create some exercises to practice what I learned during the [guessing game](https://doc.rust-lang.org/book/ch02-00-guessing-game-tutorial.html) tutorial.

### Diff of the previous code

```diff
use std::cmp::Ordering;
use std::io;

use rand::Rng;

use std::cmp::Ordering;
use std::io;

use rand::Rng;

fn main() {
 
     let secret_number = rand::thread_rng().gen_range(1..=100);
 
-    println!("The secret number is: {secret_number}");
-
-    println!("Please input your guess.");
-
-    let mut guess = String::new();
-
-    io::stdin()
-    .read_line(&mut guess)
-        .expect("Failed to read line");
-
-    let guess: u32 = guess.trim().parse().expect("Please type a number!");
-
-    println!("You guessed: {guess}");
-
-    match guess.cmp(&secret_number) {
-        Ordering::Less => println!("Too small!"),
-        Ordering::Greater => println!("Too big!"),
-        Ordering::Equal => println!("You win!"),
+    loop {
+        println!("Please input your guess.");
+
+        let mut guess = String::new();
+
+        io::stdin()
+            .read_line(&mut guess)
+            .expect("Failed to read line");
+
+        let guess: u32 = match guess.trim().parse() {
+            Ok(num) => num,
+            Err(_) => continue,
+        };
+
+        println!("You guessed: {guess}");
+
+        match guess.cmp(&secret_number) {
+            Ordering::Less => println!("Too small!"),
+            Ordering::Greater => println!("Too big!"),
+            Ordering::Equal => {
+                println!("You win!");
+                break;
+            }
+        }
     }
+
 }
```

### Complete Code

```rust
use std::cmp::Ordering;
use std::io;

use rand::Rng;

fn main() {

    println!("Guess the number!");

    let secret_number = rand::thread_rng().gen_range(1..=100);

    loop {
        println!("Please input your guess.");

        let mut guess = String::new();

        io::stdin()
            .read_line(&mut guess)
            .expect("Failed to read line");

        let guess: u32 = match guess.trim().parse() {
            Ok(num) => num,
            Err(_) => continue,
        };

        println!("You guessed: {guess}");

        match guess.cmp(&secret_number) {
            Ordering::Less => println!("Too small!"),
            Ordering::Greater => println!("Too big!"),
            Ordering::Equal => {
                println!("You win!");
                break;
            }
        }
    }

}

```
