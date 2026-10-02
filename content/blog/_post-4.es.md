---
title: "¡Programa completo!"
date: 2026-05-24T20:49:18-03:00
tags: ["rust", "aprendizaje"]
---
Hoy terminé el 'guessing game', el programa en Rust del tutorial. Todavía estoy estupefacto de lo simple que es tratar errores en Rust y usar ``loop``.

### Loop

Recordando que, en el post anterior tuvimos ahí un breve tratamiento o conversión de números, en el caso de String a enteros(?). En esta sesión aprendí otra cosa increíble en Rust, el uso del ``loop``.

Y es tan simple que me quedé algunos minutos mirando la pantalla para ver cuál era la trampa, porque usar ``loop`` en Rust es básicamente:

```rust
loop {
 //codigo
}
```

Me quedé mirando esto y preguntándome dónde iba a romperse, porque no era posible. Pero sí es posible, simple y directo. Es un loop y ya, tú decides si va a quedarse infinito o parar; en el caso del programa del tutorial, el ``break`` ocurre cuando aciertas el número.

Creo que en esta sesión del tutorial, el uso de ``match``, ``let``, ``loop`` y ``mut`` quedaron bien ejemplificados. El ``match`` principalmente donde, gracias a él, el programa logra hacer una validación de la inserción de valores del usuario; si es diferente de un número, retorna un ``Result`` del tipo ``Err`` y continúa en el ``loop``, en caso contrario retorna el número y sigue el flujo del código.

Muy interesante el aprendizaje hasta ahora, voy a crear algunos ejercicios para practicar lo que aprendí durante el tutorial del [guessing game](https://doc.rust-lang.org/book/ch02-00-guessing-game-tutorial.html).

### Diff del código anterior

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

### Código completo

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
