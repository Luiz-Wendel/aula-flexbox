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

*Para testar na prática, crie um arquivo html na sua pasta do conteúdo do dia de hoje no seu repositório `trybe-exercises` e copie e cole o seguinte código que será usado durante todo o conteúdo:*
```html
<!DOCTYPE html>
<html lang="pt-br">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Flexbox</title>
    <style>
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }

      body {
        background-color: black;
        color: white;
      }

      .container {
        margin: 0 auto;
        position: relative;
        top: 50%;
        background-color: darkred;
        width: 500px;
        height: 500px;
      }

      .item {
        background-color: darkblue;
        width: 25px;
        /* height: 25px; */
      }

      .item:nth-of-type(3) {
        background-color: blueviolet;
      }

      .item:nth-of-type(5) {
        background-color: teal;
      }
    </style>
  </head>

  <body>
    <!--
    !   Para uma melhor experiência dos exemplos
    !   do conteúdo modifique apenas o CSS!
  -->
    <div class="container">
      <div class="item">1</div>
      <div class="item">2</div>
      <div class="item">3</div>
      <div class="item">4</div>
      <div class="item">5</div>
      <div class="item">6</div>
      <div class="item">7</div>
      <div class="item">8</div>
      <div class="item">9</div>
      <div class="item">10</div>
    </div>
  </body>
</html>
```

Exercícios (altere apenas o CSS, mais especificamente a classe `.container`):
  1. Adicione a propriedade `display: flex;`;
  2. Quando você define o `display` como `flex` temos o comportamento `flex-direction: row;` como padrão, mas adicione essa propriedade mesmo assim (nada deve mudar);
  3. Outro valor utilizado para essa propriedade é o `row-reverse` *(linha reversa)*, mude o valor da propriedade `flex-direction` para este novo valor e preste atenção nos números;
  4. Você observou os principais valores para o eixo principal horizontal, agora mude a propriedade `flex-direction` para `column` *(coluna)* e observe o eixo principal mudar para a vertical;
  5. Você também pode inverter o sentido do eixo principal que nem foi feito no terceiro exemplo mudando o valor do `flex-direction` para `column-reverse` *(coluna reversa)*.

Para mais informações você pode acessar a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/flex-direction).

#### justify-content

A propriedade `justify-content` define como os flex itens serão alinhados e/ou espaçados entre si. Quando essa propriedade não é definida seu comportamento padrão é o `flex-start` *(flex-início)*.

É importante notar que o alinhamento dessa propriedade é feito conforme o **eixo principal** do flex contêiner.

Vamos testar as principais opções?
Volte no seu arquivo HTML e siga os exercícios:
  1. Retorne o valor de `flex-direction` para `row`;
  2. Adicione a propriedade `justify-content: flex-start;`, nada mudou! :disappointed_relieved: Isso se deve ao fato do `flex-start` ser o valor padrão;
  3. Agora teste com os valores:
    3.1. `flex-end` *(flex-fim)*;
    3.2. `space-between` *(espaço-entre)*;
    3.3. `space-around` *(espaço-em-volta)*;
    3.4. `space-evenly` *(espaço-igualitário)*;
    3.5. `center` *(centro)*.
  4. Caso você fique curioso vale a pena repetir o terceiro exemplo com o `flex-direction: row;`.

Para mais informações você pode acessar a [documentação do MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content).

#### align-items

A propriedade `align-items` tem o com objetivo alinhar os flex itens conforme o **eixo cruzado**. Quando essa propriedade não é definida seu comportamento padrão é o `stretch` *(esticar)*.

Pronto para ver na prática?
Volte no seu arquivo HTML e siga os exercícios:
  1. Altere as propriedades para ficar assim: `flex-direction: row;` e `justify-content: flex-start;`;
  2. Adicione a propriedade `align-items: stretch`, nada mudou! :pensive: Imagino que você já saiba o porquê, certo? Isso mesmo! `stretch` eh o valor padrão;
  3. Agora teste com os valores:
    3.1. `flex-start` *(flex-início)*;
    3.2. `flex-end` *(flex-fim)*;
    3.3. `center` *(centro)*;
  4. Pequeno desafio: tentar deixar o conteúdo centralizado no quadrado vermelho.

Para mais informações você pode acessar a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/align-items).

#### flex-wrap

Por padrão (`flex-wrap: nowrap`) o flex contêiner junta todos os flex itens para caber na mesma linha/coluna, mas com a propriedade `flex-wrap` podemos definir o comportamento de wrap *("embrulho")* do contêiner. Ou seja, você pode fazer com que o flex contêiner crie novas linhas/colunas (dependendo do eixo) conforme o tamanho dos flex itens vão ultrapassando o tamanho do **eixo principal** do flex contêiner.

Que tal praticar?
Volte no seu arquivo HTML e siga os exercícios:
  1. Defina as propriedades `flex-direction: row;`, `justify-content: flex-start;` e `align-items: stretch;`;
  2. Altere o valor da `width` da classe `.item` para `100px`;
  3. Adicione `flex-wrap: nowrap;`, nada deve mudar. Fique atento se você está adicionando para a classe `.container`;
  4. Teste os outros valores:
    4.1. `wrap` *(embrulhar)*;
    4.2. `wrap-reverse` *(embrulhar-inverso)*.
  5. Agora mude o valor da `width` da classe `.item` de volta para `25px`.

Para mais informações você pode acessar a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/flex-wrap).

#### flex-flow

Como as propriedades `flex-direction` e`flex-wrap` são muito usadas em conjunto, foi criado uma nova propriedade que combina as duas, a `flex-flow`, que recebe como valor duas `strings` separadas por um espaço, a primeira string referente ao `flex-direction`e a segunda string referente ao `flex-wrap`.

Exemplo:
```CSS
flex-flow: row wrap;
```

Exercícios! :smile:
  1. Remova as propriedades `flex-direction` e `flex-wrap`;
  2. Adicione a propriedade `flex-flow: row nowrap;`, nada vai mudar;
  3. Agora teste com outros valores, lembre dos valores aprendidos (exemplo: `flex-flow: row-reverse wrap;`).

Para mais informações você pode acessar a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/flex-flow).

#### align-content

Você pode controlar o espaçamento entre as linhas/colunas criadas pelo wrap com a propriedade `align-content`. Essa propriedade possui valores semelhantes ao do `justify-content`, porem seu valor padrao eh o `normal`.

É importante entender que essa propriedade não vai ter efeito caso a propriedade `flex-wrap` tenha o valor `nowrap`.

Voce pode testar a nova propriedade com alguns exercicios:
  1. Defina as seguintes propriedades: `flex-flow: row wrap;`, `justify-content: flex-start;` e `align-items: stretch;`;
  2. Adicione a propriedade `align-content: normal;`, nada muda;
  3. Teste os seguintes valores:
    3.1. `flex-start`;
    3.2. `flex-end`;
    3.3. `center`;
    3.4. `space-between`;
    3.5. `space-around`;
    3.6. `stretch`.

Para mais informações você pode acessar a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/align-content).

### Propriedades dos flex itens *(elementos filhos)*

#### flex-shrink

A propriedade `flex-shrink` permite aos flex itens diminuírem de tamanho caso o tamanho total dos flex itens sejam maior que o tamanho do flex contêiner.

O valor recebido pela propriedade é um número que especifica a razão que o item vai diminuir em relação aos outros itens. Quando essa propriedade não é definida seu valor padrão é `1`.

Que tal exercitar?
  1. Antes de começar você deve remover todas as propriedades da classe `.container` que se referem ao flex, e deixar apenas o `display: flex;`;
  2. Remova o comentário da propriedade `height` *(agora na classe `.item`)* e altere a `width` para `75px`;
  3. Adicionar a propriedade `flex-shrink: 1;` para o seletor `.item:nth-of-type(3)`, nada muda;
  4. Agora teste com outros valores (exemplo: 0, 2), você também pode adicionar o `flex-shrink` para o seletor `.item:nth-of-type(5)`.

Para mais informações você pode acessar a [documentação do MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink).

#### flex-grow

Conforme você aprendeu na propriedade anterior que se refere a razão que o item vai diminuir, a propriedade `flex-grow` define a razão que o item vai aumentar conforme o tamanho do flex contêiner aumenta. A propriedade também recebe como valor um número e tem como valor padrão `0`.

Aqui estão alguns exercícios para você praticar:
  1. Para esse exercício você deve retornar o valor da `width` para `25px`;
  2. Adicione a propriedade `flex-grow: 0;` para o seletor `.item:nth-of-type(3)`, nada muda;
  3. Altere o seu valor para `1` e veja o que acontece;
  4. Agora teste adicionando a propriedade para o seletor `.item:nth-of-type(5)` e mude os valores para entender melhor como funciona.

Para mais informações você pode acessar a [documentação do MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow).

#### flex-basis

Caso você queira definir um valor inicial para o tamanho do flex item a propriedade que você está procurando é a `flex-basis`. Essa propriedade define o tamanho inicial do flex item antes do CSS aplicar ajustes do `flex-shrink` ou `flex-grow`.

Quando essa propriedade não é definida seu comportamento padrão é ajustar o tamanho baseado no conteúdo e tem valor padrão de `auto`.

Habemus exercícios:
  1. Adicione a propriedade `flex-basis: 50px;` na classe `.item`;
  2. Perceba que as propriedades `flex-shrink` e `flex-grow` dos seletores nao tem mais efeito pois os flex itens ocupam todo o espaço do flex contêiner;
  3. Agora mude o valor para `40px`, as propriedades `flex-shrink` e `flex-grow` voltam a funcionar;
  4. Teste mais alguns valores a sua escolha.

Para mais informações você pode acessar a [documentação do MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis).

#### flex

Todas as propriedades do flex item vistas anteriormente podem ser estabelecidas através de uma única propriedade do flex item, a `flex`, que recebe como valor 3 strings separadas por espaço, a primeira referente ao `flex-grow`, a segunda referente ao `flex-shrink` e a terceira referente ao `flex-basis`.

Exemplo:
```CSS
flex: 0 1 auto;
```

Exercícios? ~~Não~~ Sim, exercícios!
  1. Remova as propriedades `flex-basis`, `flex-shrink` e `flex-grow` dos seletores e da classe `.item`;
  2. Adicione a propriedade `flex: 0 1 auto;` na classe `.item`, nada muda;
  3. Altere os valores conforme você aprendeu nas propriedades passadas;
  4. Não se esqueça de testar adicionando a propriedade `flex` para os seletores.

Para mais informações você pode acessar a [documentação do MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/flex).

#### order

Mudar a ordem em que os flex itens são mostrados dentro do flex contêiner? Sim, você pode! Basta usar a propriedade `order`, que recebe um número como valor e que se refere a posição dele referente aos outros elementos. Quando você não define a propriedade o seu valor padrão é `0`.

A ordem que os elementos aparecem é feita em ordem crescente do valor da propriedade `order`. Mas se mais de um flex item tiver o mesmo valor, o que acontece? O flex item que vier primeiro no HTML vai aparecer antes. Também é importante ressaltar que você pode utilizar valores negativos. :wink:

Praticar? ~~Nunca~~ Sempre!
  1. Adicione a propriedade `order: 0;` ao seletor `.item:nth-of-type(3)`, nada muda;
  2. Agora coloque um valor maior que `0`;
  3. Agora coloque um valor menor que `0`;
  4. Adicione a propriedade `order` ao outro seletor, você também pode criar outros seletores, deixe a imaginação à solta.

Para mais informações você pode acessar a [documentação do MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/order).

#### align-self

Assim como você aprendeu na propriedade anterior, também é possível mudar o alinhamento no eixo principal de um flex item, você também pode mudar o alinhamento no **eixo cruzado** de um flex item específico sem alterar o alinhamento dos outros flex itens. Para conseguir esse efeito você pode usar a propriedade `align-self`.

Exercícios finais: :sweat_smile:
  1. Adicione a propriedade `align-self: flex-start;` ao seletor `.item:nth-of-type(3)`, nada muda;
  2. Agora altere seu valor para `center`;
  3. Deixe a imaginação fluir e teste com outros valores, vale a pena colocar a propriedade em outros seletores para testar também.

Para mais informações você pode acessar a [documentação do MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/align-self).

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
