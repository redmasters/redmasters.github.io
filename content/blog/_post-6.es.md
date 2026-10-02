---
title: "redoxide - Overlay de Dota gratis en Rust"
date: 2026-08-01T13:26:00
toc: true
---
Siempre que me preguntan cómo empezar en programación, siempre digo lo mismo, hasta parece una frase repetida, y lo repito: "Aprende con proyectos", "Equivócate, lee el debug", "Lee la documentación". Creo que es el camino más rápido si quieres ver cómo funcionan las cosas. Así que estoy probando lo que yo mismo digo, estoy aprendiendo Rust y decidí hacer un proyecto que me ayuda en el día a día.

Vibecodeado, obviamente, desde el backend hasta el front, todavía estoy gateando con Rust, apenas sé las variables básicas, constantes, etc. Pero ver cómo "funcionan las cosas" me hace entender y de cierta forma me obliga a aprender a leer el código, porque, al final, por más que la IA escriba todo el código, quiero saber si el flujo está como lo planeé, si no hay algo que mejorar, y nada mejor que aprender programación programando de verdad (aunque sea con Copilot jeje).

## El proyecto

![redoxide logo?](/images/redoxide.png)

Es un overlay que se coloca sobre el Dota 2 con algunos paneles con feedbacks visuales y benchmarks de la partida actual. Es como un asistente que te indica si estás rindiendo bien dentro de la partida, con datos como 'farming', 'timming' de ítems, patrimonio, etc. Son métricas comunes que tú, como jugador, encuentras en sitios como Stratz, DotaBuff y OpenDota, métricas comunes y gratuitas.

Hoy existen overlays que ya hacen muy bien este trabajo, como Overwolf Overlay y Stratz y otros que te cobran por eso, lo que hasta me parece injusto, pero una vez en el trabajo escuché que "nosotros los programadores somos como albañiles, hacemos la casa de los otros, pero no construimos nada para nosotros". Lo que tiene todo el sentido, porque "construir la casa de los otros" es nuestro trabajo y, al terminar el día de servicio, tengo toda la certeza de que no quieres seguir trabajando. Pero ahí, con esta idea de que nosotros, como programadores, no construimos nada para nosotros, qué porquería, ¿no?! Entonces pensé "pues bien, soy programador y voy a construir algo que necesito!"

Uní lo útil (necesito aprender Rust) con lo agradable (overlay para mi Dota) y estoy desarrollando este proyecto; mi objetivo es dejarlo gratis para que la comunidad de Dota lo use y, quién sabe, contribuir a su evolución. Me cuesta mucho el diseño de interfaces, así que dejo todo en manos del Copilot y de las skills sobre UI/UX que encuentro.

# Capturas

Algunas capturas de redoxide:

## Panel Gestor

![Gestor](/images/manager.png)
> Panel Gestor del usuario

![Gestor con dev tools](/images/manager-dev.png)
> Panel Gestor con algunas herramientas para pruebas

## Panel de Patrimonio "Networth Panel"

![panel networth](/images/networth-panel.png)
> Panel donde el jugador verifica en tiempo real si está dentro del timming de farm

## Panel de Ítems

![panel de ítems](/images/items-panel.png)
> Panel con sugerencias para la build de ítems, basado en Win Rates

Se agregarán más paneles o benchmarks según lo que yo considere necesario; estoy pensando en algún tracking de rendimiento por posición (Carry, Mid, Off o Supports), pero eso es solo una idea.

Hablé y hablé, pero aquí está el link del git: <https://github.com/redmasters/redoxide-dota>
