# FlexBox

Esse tipo de elemento serve para deixar os elementos 'flexiveis' o bastante para se adequarem ao tamanho do elemento pai. Na pratica estamos falando de um definir um estilo que se adequa a qualquer tamanho de tela.

## Definir a propriedade

```css
elementoPai{
    display: flex;
}
```

> Ao aplicas `display: flex;` em um elemento que tenha filhos, todos eles vao ter uma mudanca.
> Sendo assim podemos atraves do mesmo aplicar mudancas em todos os seus filhos.

## Flex-direction

Define como os itens flexíveis são colocados no contêiner flexível, definindo o eixo principal e a direção (normal ou invertido).

- `flex-direction: row;`
- `flex-direction: row-reverse;`
- `flex-direction: column;`
- `flex-direction: column-reverse;`


<img src='./images/flex/flex5.png' style='width:600px'>

## Flex-wrap

Define se os itens flexíveis são forçados a ficarem na mesma linha ou se podem ser quebradas em varias linhas. Se o argumento for valido, ele define a direção em que as linhas são empilhadas.


- `flex-wrap: nowrap;` -> Os itens flexíveis são agrupados em uma unica linha, o que pode fazer com que o flex container transborde. O cross-start é equivalente ao início ou antes, dependendo do valor da `flex-direction`. **Este é o valor padrão.**
- `flex-wrap: wrap;` -> Os itens flexíveis são quebrados em multiplas linhas. O cross-start é equivalente a iniciar ou antes dependendo do valor do `flex-direction` e cross-end é o oposto do especificado cross-start.
- `flex-wrap: wrap-reverse;` -> Se comporta da mesma maneira que o `wrap` mas a de linha ocorre na direção contrária, ou seja, para a linha acima.

<img src='./images/flex/flex-wrap3.png' style='width:600px'>

## Flex-flow

A propriedade CSS flex-flow é uma junção das propriedades flex-direction e flex-wrap.
- Syntax
    * `flex-flow: flex-direction flex-wrap;`
```css
/* exemplo */
div {
  display: flex;
  flex-flow: row-reverse wrap;
}
```