---
title: "Programa Completo!"
date: 2026-05-24T20:49:18-03:00
tags: ["rust", "learning"]
---
Hoje finalizei o 'guessing game', programa em Rust do tutorial. Ainda estou estupefato como eh simples tratar erros em rust e usar ``loop``.

### Loop

Relembrando que, no post anterior tivemos ali um breve tratamento ou conversao de numeros, no caso de String para inteiros(?). Nesta sessao aprendi outra coisa incrivel no rust o uso do ``loop``.

E eh tao simples que eu fiquei alguns minutos olhando pra tela pra ver qual era a pegadinha pois usar ``loop`` no rust eh basicamente:

```rust
loop {
 //codigo
}
```

Fiquei olhando pra isso e me pergutando onde ia quebrar pois, nao era possivel. Mas eh possivel sim, simples e direto. Eh um loop e pronto, vc decide se ele vai ficar infinito ou parar, no caso do programa do tutorial o ``break`` se da quando vc acerta o numero.

Creio que nesta sessao do tutorial, o uso do ``match``, ``let``, ``loop`` e ``mut`` foram bem exemplificados. O ``match`` principalmente onde, gracas a ele o programa consegue fazer uma validacao de insercao de valores do usuario, caso seja diferente de um numero ele retorna um ``Result`` do tipo ``Err`` e continua no ``loop`` caso contrario ele retorna o numero e segue o fluxo do codigo.

Muito interessante o aprendizado ate agora, vou criar alguns exercicios para praticar o que aprendi durante o tutorial do [guessing game](https://doc.rust-lang.org/book/ch02-00-guessing-game-tutorial.html).

### Diff do codigo anterior

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

### Codigo Completo

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
