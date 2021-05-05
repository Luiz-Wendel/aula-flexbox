# Flexbox

## O que vamos aprender?

Alinhar e distribuir corretamente o conteúdo da página HTML é essencial para criar uma página com uma boa experiência para o usuário. Nos blocos anteriores você aprendeu como posicionar os elementos utilizando as propriedades `float` e `position`. Agora você vai aprender sobre o Flexbox (Flexible Box).

O Flexbox foi um módulo de layout do CSS criado para facilitar a criação de estruturas flexíveis e responsivas que ajudam no alinhamento e distribuição dos elementos na página, sendo possível ser feito na vertical e/ou na horizontal.

Para melhor entender o conceito de flexbox você deve compreender dois  conceitos muito utilizados ao se tratar do assunto, o flex contêiner e flex item. Um flex container é um elemento pai que possui a propriedade flex, e os seus respectivos elementos filhos são denominados flex itens.

## Você será capaz de:

Fazer com que um elemento pai (flex contêiner) seja flexível para poder melhor acomodar seus elementos filhos (flex itens) de maneira que fiquem bem alinhados e distribuídos na página.

Utilizar corretamente os atributos provenientes do uso da propriedade flex tanto para o caso dos contêineres quanto para o caso dos flex itens.

Disponibilizar os elementos filhos de um flex contêiner na forma de linha e/ou coluna.

Entender conceitos referentes ao Flexbox como:
  * Flex contêiner;
  * Flex item;
  * Eixo principal;
  * Eixo cruzado.

## Porque isso é importante?

Atualmente você pode entrar em um site de diversas maneiras (através de um computador, celular, tablet, videogame, entre outros) e com isso fica difícil definir qual o tamanho da tela que vai mostrar o conteúdo. É aí que entra a necessidade de um elemento flexível, que pode alterar o seu tamanho e a disposição de seu conteúdo conforme o tamanho disponível na tela.

Imagine, por exemplo, que sempre que você precisasse adicionar um novo item a uma lista de produtos tivesse que adicionar a posição exata dele na tela para ele ficar alinhado com os demais itens, essa forma seria muito complexa. Agora imagine que você tenha um elemento que conforme você vai adicionando itens dentro dele ele se expande de forma a adicionar o novo elemento e ainda deixa ele alinhado e agrupado conforme a posição dos demais itens, independentemente de saber o tamanho do conteúdo, essa segunda forma seria muito mais simples. E esse é o comportamento que você consegue ao utilizar o Flexbox.

## Conteúdos

### Propriedades do flex conteiner *(elemento pai)*

#### display

Você já viu a propriedade `display` nos blocos passados, mas agora você vai aprender um novo valor, o `flex`.

A propriedade `display: flex` em um elemento permite que você use outras propriedades flex para construir páginas responsivas, além de transformar este elemento em um flex contêiner.

#### flex-direction

A propriedade `flex-direction` define a direção de alinhamento dos elementos filhos do contêiner. Quando essa propriedade não é definida seu comportamento padrão é `row` *(linha)*.

Para melhor entender como essa propriedade funciona você tem que entender um conceito muito usado no Flexbox, o main-axis *(eixo principal)* e cross-axis *(eixo cruzado)*. A propriedade `flex-direction` possui dois valores principais: `row` e `column`. A diferença entre esses dois valores são as direções do eixo principal e do eixo cruzado.

O `flex-direction: row` define o **eixo principal** como sendo **horizontal**, da esquerda para a direita, e o **eixo cruzado** sendo **vertical**, de cima para baixo.

Enquanto que o `flex-direction: column` define o **eixo principal** como sendo **vertical**, de cima para baixo, e o **eixo cruzado** como sendo **horizontal**, da esquerda para a direita.

Opções:
  * row *(linha)*;
  * row-reverse *(linha reversa)*;
  * column *(coluna)*;
  * column-reverse *(coluna reversa)*.

<!-- TODO: Exemplos -->

#### justify-content

A propriedade `justify-content` define como os flex itens serão alinhados e/ou espaçados entre si. Quando essa propriedade não é definida seu comportamento padrão é o `flex-start` *(flex-início)*.

É importante notar que o alinhamento dessa propriedade é feito conforme o **eixo principal** do flex contêiner.

Opções:
  * flex-start;
  * flex-end;
  * space-between;
  * space-around;
  * space-evenly;
  * center.

<!-- TODO: Exemplos -->

#### align-items

A propriedade `align-items` tem o com objetivo alinhar os flex itens conforme o **eixo cruzado**. Quando essa propriedade não é definida seu comportamento padrão é o `stretch` *(esticar)*.

Opções:
  * stretch;
  * center;
  * flex-start;
  * flex-end;
  * baseline.

<!-- TODO: Exemplos -->

#### flex-wrap

Por padrão (`flex-wrap: nowrap`) o flex contêiner junta todos os flex itens para caber na mesma linha/coluna, mas com a propriedade `flex-wrap` podemos definir o comportamento de wrap *("embrulho")* do contêiner. Ou seja, você pode fazer com que o flex contêiner crie novas linhas/colunas (dependendo do eixo) conforme o tamanho dos flex itens vão ultrapassando o tamanho do **eixo principal** do flex contêiner.

Opções:
  * nowrap;
  * wrap;
  * wrap-reverse.

<!-- TODO: Exemplos -->

#### flex-flow

Como as propriedades `flex-direction` e`flex-wrap` são muito usadas em conjunto, foi criado uma nova propriedade que combina as duas, a `flex-flow`, que recebe como valor duas `strings` separadas por um espaço, a primeira string referente ao `flex-direction`e a segunda string referente ao `flex-wrap`.

Exemplo:
```CSS
flex-flow: row wrap;
```

Caso você queira testar essa nova propriedade, você pode usar o código do exercício anterior. :wink:

#### align-content

Você pode controlar o espaçamento entre as linhas/colunas criadas pelo wrap com a propriedade `align-content`.

É importante entender que essa propriedade não vai ter efeito caso a propriedade `flex-wrap` tenha o valor `nowrap`.

Opções mais usadas:
  * flex-start
  * flex-end
  * center
  * space-between
  * space-around
  * stretch

Para uma lista completa de opcoes e mais informacoes sobre a propriedade voce pode visitar a pagina da [MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/align-content).

Caso você queira testar essa nova propriedade, você pode usar o código do exercício anterior. :wink:

### Propriedades dos flex itens *(elementos filhos)*

#### flex-shrink

A propriedade `flex-shrink` permite aos flex itens diminuírem de tamanho caso o tamanho total dos flex itens sejam maior que o tamanho do flex contêiner.

O valor recebido pela propriedade é um número que especifica a razão que o item vai diminuir em relação aos outros itens. Quando essa propriedade não é definida seu valor padrão é `1`.

<!-- TODO: Exemplos -->

#### flex-grow

Conforme você aprendeu na propriedade anterior que se refere a razão que o item vai diminuir, a propriedade `flex-grow` define a razão que o item vai aumentar conforme o tamanho do flex contêiner aumenta. A propriedade também recebe como valor um número e tem como valor padrão `0`.

<!-- TODO: Exemplos -->

#### flex-basis

Caso você queira definir um valor inicial para o tamanho do flex item a propriedade que você está procurando é a `flex-basis`. Essa propriedade define o tamanho inicial do flex item antes do CSS aplicar ajustes do `flex-shrink` ou `flex-grow`.

Quando essa propriedade não é definida seu comportamento padrão é ajustar o tamanho baseado no conteúdo e tem valor padrão de `auto`.

<!-- TODO: Exemplos -->

#### flex

Todas as propriedades do flex item vistas anteriormente podem ser estabelecidas através de uma única propriedade do flex item, a `flex`, que recebe como valor 3 strings separadas por espaço, a primeira referente ao `flex-grow`, a segunda referente ao `flex-shrink` e a terceira referente ao `flex-basis`.

Exemplo:
```CSS
flex: 0 1 auto;
```

<!-- TODO: Exemplos -->

#### order

Mudar a ordem em que os flex itens são mostrados dentro do flex contêiner? Sim, você pode! Basta usar a propriedade `order`, que recebe um número como valor e que se refere a posição dele referente aos outros elementos. Quando você não define a propriedade o seu valor padrão é `0`.

A ordem que os elementos aparecem é feita em ordem crescente do valor da propriedade `order`. Mas se mais de um flex item tiver o mesmo valor, o que acontece? O flex item que vier primeiro no HTML vai aparecer antes. Também é importante ressaltar que você pode utilizar valores negativos. :wink:

<!-- TODO: Exemplos -->

#### justify-self

Você aprendeu a alinhar os flex itens no **eixo principal** usando a propriedade `justify-content` no flex contêiner, mas e se você quiser que um flex item específico tenha um alinhamento no **eixo principal** diferente do restante? A propriedade `justify-self` resolve esse problema, com ela você pode mudar o alinhamento de um único flex item sem mudar o alinhamento no **eixo principal** dos outros flex itens.

<!-- TODO: Exemplos -->

#### align-self

Assim como você aprendeu na propriedade anterior, também é possível mudar o alinhamento no eixo principal de um flex item, você também pode mudar o alinhamento no **eixo cruzado** de um flex item específico sem alterar o alinhamento dos outros flex itens. Para conseguir esse efeito você pode usar a propriedade `align-self`.

<!-- TODO: Exemplos -->

## Exercícios

<!-- TODO: Exercicios + EXTRAS -->

## Recursos Adicionais

[Guia de Flexbox escrito pela MDN](https://developer.mozilla.org/pt-BR/docs/Learn/CSS/CSS_layout/Flexbox "MDN")

[CSS FlexBox: Um Guia Visual](https://www.alura.com.br/artigos/css-guia-do-flexbox?gclid=EAIaIQobChMIleKjwumu8AIV0AaICR20pA9hEAAYASAAEgIxcvD_BwE "Alura")

[Guia completo para Flexbox (em inglês)](https://css-tricks.com/snippets/css/a-guide-to-flexbox/ "CSS-Tricks")

[Ajude o Froggy e seus amigos utilizando CSS](https://flexboxfroggy.com/ "Flexbox Froggy")

[Aprenda Flexbox com um jogo de tower defense](http://www.flexboxdefense.com/ "Flebox Defense")

[Escreva comandos do Flexbox para se defender de zumbis](https://mastery.games/flexboxzombies/ "Flexbox Zombies")

## Gabarito
