---
title: "redoxide - Dota Overlay free em Rust"
date: 2026-08-01T13:26:00
toc: true
---
Sempre que me perguntam como iniciar em programacao eu sempre falo a mesmma coisa, parece ate uma frase batida e repito: "Aprenda com projetos", "Erre, leia o debug", "Leia a documentacao". Creio que seja o caminho mais rapido se voce quer ver como as coisas funcionam. Entao eu estou provando do que eu mesmo digo, estou aprendendo Rust e decidi fazer um projet que me ajuda no dia dia.

Vibecodado obviamente, desde o backend ao front, ainda to engatinhando com Rust, mal sei as variaveis basicas, constantes etc. Mas vendo como "as coisas funcionam " me faz entender e meio que me obriga a aprender a ler o codigo pois, no final por mais que a IA escreva todo o codigo, eu quero saber se o fluxo esta como planejei, se nao tem algo a ser melhorado e nada melhor que aprender programacao, programando de fato (mesmo que seja o Copilot hehe).

## O Projeto

![redoxide logo?](/images/redoxide.png)

Eh um overlay que fica sobre o Dota2 com alguns paineis com feedbacks visuais e benchmarks da partida atual. Ele eh como um assistente que te indica se voce ta performando bem dentro da partida com dados como 'farming', 'timming' de itens, patrimonio etc. Sao metricas comuns que voce como jogador acha em sites como o Stratz, DotaBuff e o OpenDota, metricas comuns e gratuitas.

Hoje existem overlays que ja fazem muito bem esse trabalho, como o Overwolf Overlay e o Stratz mas certa vez no trabalho eu ouvi que "nos programadores somos como pedreiros, fazemos a casa dos outros mas nao construimos nada pra nos". O que faz totalmente sentido pois "contruir a casa dos outros" eh o nosso trabalho e ao terminar o dia de servico tenho toda certeza que voce nao quer continuar trabalhando. Mais ai nessa ideia que nos como programadores nao construimos nada pra nos, um merda ne?! Dai pensei "ora pois, sou programador e vou construir e algo que preciso."

Uni o util (preciso aprender rust) ao agradavel (overlay pro meu dotinha) e to desenvolvendo esse projeto, meu objetivo eh deixar free pra comunidade dota usar e quem sabe contribuir para evolucao, eu peco muito em design de interfaces entao deixo tudo na mao do copilot e das skills sobre ui/ux que encontro.

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
