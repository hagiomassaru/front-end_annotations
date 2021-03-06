---
tags: [front-end, programacao]
title: css_animacao
created: '2021-11-28T15:22:38.472Z'
modified: '2021-12-08T14:14:53.196Z'
---

 # Animacao com CSS

 A animacao em css e definida em tres pilares.
 - Criar a animacao
 - Indicar qual propriedade queremos modificar
 - Definir o tempo da animacao

 # Criando animacao e indicando as propriedades

 Para criar animacao usamos o codigo abaixo.

 ```css
@keyframes Identificador {
    from{proprieda_a_ser_modificada} /* Inicio da animacao */
    to{proprieda_a_ser_modificada} /* Fim da animacao */
}
 ```

 **EX:**

 ```css
@keyframes changeColor {
    from{background-color: red;}
    to{background-color: blue;}
    
}
 ```

 # Indicando duracao e atribuindo animacao

 Agora com a animacao criada podemos atribuir ela a um elemento css

 ```css
.box{
    width: 200px;
    height: 200px;
    border-style: solid;
    animation-name: Identificador; /* Atribuindo animacao */
    animation-duration: 3s; /* definindo tempo */
}

 ```

 # Controle por porcentagem

Esse tipo de controle e muito util caso queremos ter maior autonomia ao criar animacoes. Isso possibilita modificar varias propriedades alem do `from` e o `to`.

```css
@keyframes changeColor {
    0% {background-color: red;}
    25% {background-color: green;}
    50% {background-color: yellow;}
    75% {background-color: blueviolet;}
    100% {background-color: blue;}
    
}
```

e tambem podemos alterar mais de uma propriedade ao mesmo tempo ( o mesmo vale para `from` e `to`)

```css
@keyframes changeColor {
    0% {background-color: red;width: 200px;}
    25% {background-color: green;}
    50% {background-color: yellow;width: 800px;}
    75% {background-color: blueviolet;}
    100% {background-color: blue;width: 200px;}
    
}
```
# Animation Delay

Essa propriedade serve para definirmos o tempo de espera antes da animacao comecar de fato.

```css
.box{
    width: 200px;
    height: 200px;
    border-style: solid;
    animation-name: changeColor;
    animation-duration: 9s;
    animation-delay: 4.5s; /* Definindo delay */
}
```
em cado de valores negativos, a animacao comeca a partir do valor negativo estipulado.

```css
.box{
    width: 200px;
    height: 200px;
    border-style: solid;
    animation-name: changeColor;
    animation-duration: 9s;
    animation-delay: -4.5s; /* Definindo delay */
    /* a animacao comeca a partir dos 4.5 segundos */
}
```

# Animation Iteration Count - Loop

Esse prorpriedade serve para criarmos loops em nossas animacoes

**Syntax**
`animation-iteration-count: number|infinite|initial|inherit;`

- Loop infinito
```css
.box{
    animation-iteration-count: infinite;
}
```

- Loop finito
```css
.box{
    animation-iteration-count: 2;
}
```

# Animation Direction

A propriedade `animation-direction` define se uma anima????o deve ser reproduzida para frente, para tr??s ou em ciclos alternativos.

**Syntax**
- `animation-direction: normal|reverse|alternate|alternate-reverse;`
    - `normal` -> Valor padr??o. A anima????o ?? reproduzida normalmente (para a frente)
    - `reverse` -> A anima????o ?? reproduzida na dire????o inversa (para tr??s)
    - `alternate` -> A anima????o ?? tocada primeiro e depois para tr??s
    - {alternate-reverse} -> A anima????o ?? reproduzida primeiro e depois para a frente

# Animation fill mode

A propriedade animation-fill-mode especifica um estilo para o elemento quando a anima????o n??o est?? sendo reproduzida (antes de come??ar, depois de terminar ou ambos)

**Syntax**
- `animation-fill-mode: none|forwards|backwards|both|initial|inherit;`
    - `none` -> Valor padr??o. A anima????o n??o aplicar?? nenhum estilo ao elemento antes ou depois da execu????o
    - `forwards` -> O elemento manter?? os valores de estilo definidos no ??ltimo quadro-chave (depende da anima????o-dire????o e da anima????o-itera????o-contagem)
    - `backwards` -> O elemento obter?? os valores de estilo definidos pelo primeiro quadro-chave (depende da dire????o da anima????o) e os manter?? durante o per??odo de atraso da anima????o
    - `both` -> A anima????o seguir?? as regras para frente e para tr??s, estendendo as propriedades da anima????o nas duas dire????es

# Animation timing function

A `animation-timing-function` especifica a curva de velocidade de uma anima????o.

**Syntax**
- `animation-timing-function: linear|ease|ease-in|ease-out|ease-in-out;`
    - `linear` -> A anima????o tem a mesma velocidade do in??cio ao fim 
    - `ease` -> Valor padr??o. A anima????o tem um in??cio lento, depois r??pido, antes de terminar lentamente 
    - `ease-in` -> A anima????o tem um come??o lento 
    - `ease-out` -> A anima????o tem um final lento 
    - `ease-in-out` -> A anima????o tem um come??o lento e um final lento

# Short Hand - codando animacao com uma linha

A propriedade `animation` ?? uma propriedade abreviada para :

- `animation-name`
- `animation-duration`
- `animation-timing-function`
- `animation-delay`
- `animation-iteration-count`
- `animation-direction`
- `animation-fill-mode`
- `animation-play-state`

**Syntax**

- `animation: name duration timing-function delay iteration-count direction fill-mode play-state;`
    - `animation-name` -> Especifica o nome do quadro-chave que voc?? deseja vincular ao seletor
    - `animation-duration` -> Especifica quantos segundos ou milissegundos uma anima????o leva para ser conclu??da
    - `animation-timing-function` -> Especifica a curva de velocidade da anima????o
    - `animation-delay` -> Especifica um atraso antes que a anima????o comece
    - `animation-iteration-count` -> Especifica quantas vezes uma anima????o deve ser reproduzida
    - `animation-direction` -> Especifica se a anima????o deve ou n??o ser reproduzida ao contr??rio em ciclos alternativos
    - `animation-fill-mode` -> Especifica quais valores s??o aplicados pela anima????o fora do momento em que ela est?? sendo executada
    - `animation-play-state` -> Especifica se a anima????o est?? em execu????o ou pausada


# Transitions

Como o proprio nome diz, sao as transicoes de uma propriedade css para outra. E podemos controlar modificando as seguintes propriedades:

- `transition-property`
- `transition-duration`
- `transition-timing-function`
- `transition-delay`

## transition-property

A propriedade de transition-property especifica o nome da propriedade CSS para a qual o efeito de transi????o ?? (o efeito de transi????o ser?? iniciado quando a propriedade CSS especificada for alterada).

**Syntax**

- `transition-property: none|all|property;`
    - `none` -> Nenhuma propriedade ter?? um efeito de transi????ot
    - `all` -> Valor padr??o. Todas as propriedades ter??o um efeito de transi????o
    - `property` -> Define uma lista separada por v??rgula de nomes de propriedades CSS para os quais o efeito de transi????o ??

Exemplo:
```css
div {
  transition-property: width, height;
}

div:hover {
  width: 300px;
  height: 300px;
}
```

## transition-duration

O `transition-duration` especifica quantos segundos (s) ou milissegundos (ms) um efeito de transi????o leva para ser conclu??do.

**Syntax**

`transition-duration: time;`

## transition-timing-function

a propriedade `transition-timing-function` especifica a curva de velocidade do efeito de transi????o.

**Syntax**

- `transition-timing-function: linear|ease|ease-in|ease-out|ease-in-out;`
    - `linear` -> A anima????o tem a mesma velocidade do in??cio ao fim 
    - `ease` -> Valor padr??o. A anima????o tem um in??cio lento, depois r??pido, antes de terminar lentamente 
    - `ease-in` -> A anima????o tem um come??o lento 
    - `ease-out` -> A anima????o tem um final lento 
    - `ease-in-out` -> A anima????o tem um come??o lento e um final lento


## transition-delay

A propriedade `transition-delay` especifica quando o efeito de transi????o ser?? iniciado.

**Syntax**

`transition-delay: time;`

## Short Hand - transition

Para codar todas essa propriedade com uma linha:

**Syntax**

- `transition: property duration timing-function delay;`
    - `transition-property`
    - `transition-duration`
    - `transition-timing-function`
    - `transition-delay`

Exemplo:
```css
input[type=text] {
  width: 100px;
  transition: width .35s ease-in-out;
}

input[type=text]:focus {
  width: 250px;
}
```
<img src="./images/Peek 17-12-2021 00-18.gif">

