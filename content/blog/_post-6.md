---
title: "redoxide - Dota Overlay free em Rust"
date: 2026-08-01T13:26:00
toc: true
---
Sempre que me perguntam como iniciar em programação, eu sempre falo a mesma coisa, parece até uma frase batida, e repito: "Aprenda com projetos", "Erre, leia o debug", "Leia a documentação". Creio que seja o caminho mais rápido, se você quer ver como as coisas funcionam. Então eu estou provando do que eu mesmo digo, estou aprendendo Rust e decidi fazer um projeto que me ajuda no dia a dia.

Vibecodado, obviamente, desde o backend ao front, ainda tô engatinhando com Rust, mal sei as variáveis básicas, constantes etc. Mas vendo como "as coisas funcionam" me faz entender e meio que me obriga a aprender a ler o código, pois, no final, por mais que a IA escreva todo o código, eu quero saber se o fluxo está como planejei, se não tem algo a ser melhorado, e nada melhor que aprender programação, programando de fato (mesmo que seja o Copilot hehe).

## O Projeto

![redoxide logo?](/images/redoxide.png)

É um overlay que fica sobre o Dota2 com alguns painéis com feedbacks visuais e benchmarks da partida atual. Ele é como um assistente que te indica se você tá performando bem dentro da partida, com dados como 'farming', 'timming' de itens, patrimônio etc. São métricas comuns que você, como jogador, acha em sites como o Stratz, DotaBuff e o OpenDota, métricas comuns e gratuitas.

Hoje existem overlays que já fazem muito bem esse trabalho, como o Overwolf Overlay e o Stratz e outros que te cobram por isso, o que acho injusto até, mas certa vez no trabalho eu ouvi que "nós programadores somos como pedreiros, fazemos a casa dos outros, mas não construímos nada pra nós". O que faz totalmente sentido, pois "contruir a casa dos outros" é o nosso trabalho e, ao terminar o dia de serviço, tenho toda certeza que você não quer continuar trabalhando. Mais aí nessa ideia que nós, como programadores, não construímos nada pra nós, um merda né?! Daí pensei "ora pois, sou programador e vou construir e algo que preciso!"

Uni o útil (preciso aprender rust) ao agradável (overlay pro meu dotinha) e tô desenvolvendo esse projeto; meu objetivo é deixar free pra comunidade de dota usar e, quem sabe, contribuir para evolução. Eu peco muito em design de interfaces, então deixo tudo na mão do copilot e das skills sobre ui/ux que encontro.

# Ibagens

Algumas screenshots do redoxide:

## Painel Gerenciador

![Gerenciador](/images/manager.png)
> Painel Gerenciador do usuario

![Gerenciador com dev tools](/images/manager-dev.png)
> Painel Gerenciador com algumas ferramentas pra teste

## Painel de Patrimonio "Networth Panel"

![painel networth](/images/networth-panel.png)
> Painel onde o player verifica em tempo real se esta dentro do timming de farm

## Painel de Itens

![painel items](/images/items-panel.png)
> Painel com sugestao para build de itens, baseado em Win Rates

Mais paineis ou benchmarks serao adicionados conforme eu achar necessidade, to pensando em algum tracking de performance por posicao (Carry, Mid, Off ou Suportes) mas isso eh soh ideia.

Falei falei mas ta aqui o link do git: <https://github.com/redmasters/redoxide-dota>
