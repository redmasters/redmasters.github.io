---
title: "La diversión está empezando"
date: 2026-05-20T22:36:19-03:00
tags: ["rust", "aprendizaje"]
---

Aquí creo que entendí qué significa `match`. Básicamente es una estructura que compara el resultado de una expresión. En el [post anterior]({{% ref "/blog/_post-2"%}}), vimos que `match` se escribe justo antes de la función, lo que para mí fue muy extraño, pero esta estructura compara el resultado de la función y verifica si hay alguna compatibilidad de respuestas. En este punto creo que es casi igual al `Comparator` o `Comparable` de Java.

Siguiendo con la guía, una cosa que me llamó la atención fue la capacidad de reutilizar variables con lo que Rust llama _'shadowing'_, súper excelente.
Se explica sobre los diferentes tipos de enteros, no entendí muy bien pero creo que es algo muy parecido a `Integer`, `int`, `Long` y `long` en Java, sospecho.

Amigo, pero una cosa que ya me encantó, es muy dinámico y simple construir una estructura y justo después tratar excepciones, muy práctico.

Se está poniendo divertido y quería continuar, ¡pero mi tiempo se acabó!

Código actual:

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
