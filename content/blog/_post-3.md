---
title: "A diversao ta comecando"
date: 2026-05-20T22:36:19-03:00
---

Aqui eu acho que entendi o que o `match` significa. Basicamente eh uma estrutura que compara o resultado de uma expressao. No [post anterior]({{% ref "/blog/_post-2"%}}), vimos que o `match` eh escrito logo antes da funcao, o que pra mim foi bem estranho mas esta estutura compara o resultado da funcao e verifica se ha alguma compatibilidade de respostas. Neste ponto creio que seja quase igual o `Comparator` ou `Comparable` do java.

Seguindo com o guia uma coisa me chamou atencao foi a capacidade de reuso de variaveis com o que o Rust chama de _'shadowing'_, top de excelente.
Eh explicado sobre os diferentes tipos de inteiros, nao entendi muito bem mas creio eu que eh algo muito parecido com `Integer`, `int`, `Long` e `long` no java, suspeito.

Cara mas uma coisa eu ja adorei, eh muito dinamico e simples construir uma estrutura e logo apos tratar excecoes, muito pratico.

Ta ficando divertido e eu queria continuar mas meu tempo acabou!

Codigo atual:

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
