---
title: "First Exercise"
date: 2026-05-31T00:16:08-03:00
toc: true
---
Using what I learned in the last post, I created a few routines based on what was presented in the Rust tutorial.

## Print and input data

In the tutorial we are taught how to input data from the user, handle it and/or convert it. In this exercise I did what every beginner does, a program that asks for an input and prints what was written by the user:

001.rs

```rust
fn main(){

    println!("----Imprima seu nome----");
    println!("Qual o seu nome?");

    let mut name = String::new();

    io::stdin()
    .read_line(&mut name)
    .expect("Tente novamente");

    let name = name.trim();
    println!("{name} eh um otimo nome!");

/// resto do codigo

```

Pretty simple, but it was enough to settle the knowledge about how to handle String with the ``.trim()`` function and use the variable's own value to be printed on the screen. Very good.

## Comparing numbers

In this one I used ``match`` and ``cmp`` to compare a number A against a number B. The user enters the first number and then a second number and the program says whether this one is less than/greater than or equal to that one.

Practically the same thing as the tutorial but in a different approach.

```rust
    println!("---Compare numeros!---");
    println!("Insira o primeiro numero:");

    let mut number_a = String::new();

    io::stdin()
        .read_line(&mut number_a)
        .expect("Falha ao ler o numero");
    let number_a: u32 = number_a.trim()
        .parse()
        .expect("Por favor insira o primeiro numero");

    println!("Voce inseriu o numero {number_a}");

    println!("Insira o segundo numero:");
    let mut number_b = String::new();

    io::stdin()
        .read_line(&mut number_b)
        .expect("Falha ao ler o numero");


    let number_b: u32 = number_b.trim()
        .parse()
        .expect("Por favor insira o segundo numero");

    match number_a.cmp(&number_b) {
        Ordering::Less => println!("{number_a} eh menor que {number_b}"),
        Ordering::Greater=> println!("{number_a} eh maior que {number_b}"),
        Ordering::Equal=> println!("{number_a} eh igual a {number_b}")
    }

```

## Complete exercise

Here is the complete program that asks the user to enter their name and another one that makes a comparison between two numbers.

```rust
use std::cmp::Ordering;
use std::io;

fn main(){

    println!("----Imprima seu nome----");
    println!("Qual o seu nome?");

    let mut name = String::new();

    io::stdin()
    .read_line(&mut name)
    .expect("Tente novamente");

    let name = name.trim();
    println!("{name} eh um otimo nome!");

    println!("---Compare numeros!---");
    println!("Insira o primeiro numero:");

    let mut number_a = String::new();

    io::stdin()
        .read_line(&mut number_a)
        .expect("Falha ao ler o numero");
    let number_a: u32 = number_a.trim()
        .parse()
        .expect("Por favor insira o primeiro numero");

    println!("Voce inseriu o numero {number_a}");

    println!("Insira o segundo numero:");
    let mut number_b = String::new();

    io::stdin()
        .read_line(&mut number_b)
        .expect("Falha ao ler o numero");


    let number_b: u32 = number_b.trim()
        .parse()
        .expect("Por favor insira o segundo numero");

    match number_a.cmp(&number_b) {
        Ordering::Less => println!("{number_a} eh menor que {number_b}"),
        Ordering::Greater=> println!("{number_a} eh maior que {number_b}"),
        Ordering::Equal=> println!("{number_a} eh igual a {number_b}")
    }

}
```

It was really fun to do these simple routines. Even more so to see them working!

code repo: [github.com/redmasters/rust](https://github.com/redmasters/rust)
