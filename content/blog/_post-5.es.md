---
title: "Primer ejercicio"
date: 2026-05-31T00:16:08-03:00
toc: true
---
Utilizando lo aprendido en el último post, creé algunas rutinas con lo que se presentó en el tutorial de Rust.

## Imprimir e insertar datos

En el tutorial se nos enseña cómo insertar datos del usuario, tratarlos y/o convertirlos. En este ejercicio hice lo que todo principiante hace, un programa que pide un input e imprime lo que fue escrito por el usuario:

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

Bien simple, pero sirvió para asentar el conocimiento sobre cómo tratar un String con la función ``.trim()`` y usar el propio valor de la variable para imprimirlo en pantalla. Muy bueno.

## Comparar números

En este hice uso del ``match`` y ``cmp`` para comparar un número A contra un número B. El usuario inserta el primer número y luego un segundo número y el programa dice si este es menor/mayor o igual a aquel.

Prácticamente lo mismo que el tutorial, pero con un enfoque diferente.

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

## Ejercicio completo

Aquí está el programa completo que le pide al usuario insertar su nombre y otro que hace una comparación entre dos números.

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

Fue muy divertido hacer estas rutinas simples. ¡Y más aún verlas funcionando!

repo de los códigos: [github.com/redmasters/rust](https://github.com/redmasters/rust)
