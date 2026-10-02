---
title: "Primera aplicación en Rust"
date: 2026-05-19T11:29:50-03:00
tags: ["rust", "aprendizaje"]
---

En esta sesión de estudio seguimos (yo, en este caso) la documentación que nos lleva a construir nuestra primera aplicación en Rust. Un juego de adivinanzas donde el usuario intenta adivinar un número del 1 al 100.
A lo largo del tutorial se nos presenta cómo instalar otras bibliotecas utilizando Crate, editando el archivo `Cargo.toml` y agregando la dependencia que aleatoriza, lo que me parece que Rust no hace de forma nativa y necesita una dependencia externa para eso ~~en Java sí, cof cof~~ justo después ejecutamos el comando `Cargo build`, la dependencia que agregamos en el archivo `Cargo.toml` (yo lo leo: cargo tomoio), el Crate entonces descarga todo correctamente, evitando que todo se rompa porque, como se explica en la doc, Rust lo guarda previamente en el archivo `Cargo.lock`, igualito a como lo hace Node.

Luego empieza a complicarse un poco porque a continuación se usa la expresión `match`, que no entendí muy bien cómo funciona porque se invoca de una manera muy extraña, mira:

```rust
  match guess.cmp(&secret_number) {
    // resto de la funcion
  }

```

Lo cual es un poco loco porque ese `guess` de ahí es una variable que escribimos antes. O sea, no entendí nada, mi tiempo se acabó y continuaré en la próxima sesión de estudio.

Código escrito hasta ahora:

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
