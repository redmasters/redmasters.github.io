---
title: "Primeira aplicacao em Rust"
date: 2026-05-19T11:29:50-03:00
tags: ["rust", "learning"]
---

Nesta sessao de estudo seguimos(eu no caso) a documentacao que nos leva a construir nossa primeira aplicacao em Rust. Um jogo de adivinhacao onde o usuario tenta adivinhar um numero de 1 a 100.
Ao longo do tutorial nos eh apresentado como instalar outras bibliotecas utilizando o Crate, editando o arquivo `Cargo.toml` e adicionando a dependencia que randomiza, o que me parece que o Rust nao faz nativamente e precisa de uma dependencia externa pra isso ~~no java tem cof cof~~ logo apos executamos o comando `Cargo build`,  a dependencia que adicionamos no arquivo `Cargo.toml` (eu leio: cargo tomoio), o Crate entao baixa tudo certinho evitando que se quebre tudo pois, como explicado na doc, o Rust salva previamente no arquivo `Cargo.lock`, igualzinho o node faz.

Ai comeca a complicar um pouco pq em seguida eh usada a expressao `match` que eu nao entendi muito bem como ela funciona pq ela eh invocada de um jeito bem estranho saca so:

```rust
  match guess.cmp(&secret_number) {
    // resto da funcao
  }

```

Oq eh um pouco doido pois aquele `guess` ali eh uma variavel que digitamos antes. Ou seja nao entendi nada, meu tempo acabou e vou continuar na proxima sessao de estudos.

Codigo escrito ate agora:

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
