---
title: "Primeiro Exercicio"
date: 2026-05-31T00:16:08-03:00
toc: true
---
Utilizando o aprendizado do ultimo post criei algumas rotinas com o que foi apresentado no tutorial de Rust.

## Print e inserir dados

No tutorial nos eh ensinado como inserir dados do usuario, trata-los e ou converte-los. Neste exercicio fiz o que todo iniciante faz, um programa que pede um input e imprime o que foi escrito pelo usuario:

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

Bem simples, mas deu pra assentar o conhecimento sobre como tratar String com a funcao ``.trim()`` e usar a proprio valor da variavel para ser impressa na tela. Muito bom.

## Comparar numeros

Neste fiz o uso do ``match`` e ``cmp`` para comparar um numero A contra um numero B. O usuario insere o primeiro numero e depois um segundo numero e o programa diz se este eh menor/maior ou igual aquele.

Praticamente a mesma coisa do tutorial mas em uma abordagem diferente.

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

## Exercicio completo

Eis o programa completo que pede ao usuario para inserir seu nome e outro que faz uma comparacao entre dois numeros.

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

Foi bem divertido fazer estas simples rotinas. Mais ainda ve-las funcionando!

repo dos codigos: [github.com/redmasters/rust](https://github.com/redmasters/rust)
