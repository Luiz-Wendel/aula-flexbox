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

Você pode testar a nova propriedade com alguns exercícios:
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

### HTTP Gato

Agora você vai criar uma página flexível usando imagens do site [HTTP Cats](https://http.cat/).

Copie o HTML abaixo em um arquivo `index.html`:

```html
<!DOCTYPE html>
<html lang="pt-br">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Flexbox - HTTP Gato</title>
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.2/css/all.min.css"
      integrity="sha512-HK5fgLBL+xu6dm/Ii3z4xhlSUyZgTT9tuc/hSrtw6uzJOvgRr2a9jyxxT1ely+B+xFAmJKVSTbpM/CuL7qxO8w=="
      crossorigin="anonymous"
    />
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <header>
      <a href="#" id="home">
        <i id="logo" class="fas fa-cat"></i>
        <p>HTTP Gato</p>
      </a>
      <nav class="links">
        <ul>
          <li>Informação</li>
          <li>Sucesso</li>
          <li>Redirecionamentos</li>
          <li>Cliente</li>
          <li>Servidor</li>
        </ul>
      </nav>
    </header>
    <main>
      <div class="images-container">
        <div class="image">
          <img src="https://http.cat/100" alt="Erro 100" />
        </div>
        <div class="image">
          <img src="https://http.cat/101" alt="Erro 101" />
        </div>
        <div class="image">
          <img src="https://http.cat/102" alt="Erro 102" />
        </div>
        <div class="image">
          <img src="https://http.cat/200" alt="Erro 200" />
        </div>
        <div class="image">
          <img src="https://http.cat/201" alt="Erro 201" />
        </div>
        <div class="image">
          <img src="https://http.cat/202" alt="Erro 202" />
        </div>
        <div class="image">
          <img src="https://http.cat/204" alt="Erro 204" />
        </div>
        <div class="image">
          <img src="https://http.cat/206" alt="Erro 206" />
        </div>
        <div class="image">
          <img src="https://http.cat/207" alt="Erro 207" />
        </div>
        <div class="image">
          <img src="https://http.cat/300" alt="Erro 300" />
        </div>
        <div class="image">
          <img src="https://http.cat/301" alt="Erro 301" />
        </div>
        <div class="image">
          <img src="https://http.cat/302" alt="Erro 302" />
        </div>
        <div class="image">
          <img src="https://http.cat/303" alt="Erro 303" />
        </div>
        <div class="image">
          <img src="https://http.cat/304" alt="Erro 304" />
        </div>
        <div class="image">
          <img src="https://http.cat/305" alt="Erro 305" />
        </div>
        <div class="image">
          <img src="https://http.cat/307" alt="Erro 307" />
        </div>
        <div class="image">
          <img src="https://http.cat/308" alt="Erro 308" />
        </div>
        <div class="image">
          <img src="https://http.cat/400" alt="Erro 400" />
        </div>
        <div class="image">
          <img src="https://http.cat/401" alt="Erro 401" />
        </div>
        <div class="image">
          <img src="https://http.cat/402" alt="Erro 402" />
        </div>
        <div class="image">
          <img src="https://http.cat/404" alt="Erro 404" />
        </div>
        <div class="image">
          <img src="https://http.cat/405" alt="Erro 405" />
        </div>
        <div class="image">
          <img src="https://http.cat/406" alt="Erro 406" />
        </div>
        <div class="image">
          <img src="https://http.cat/408" alt="Erro 408" />
        </div>
        <div class="image">
          <img src="https://http.cat/409" alt="Erro 409" />
        </div>
        <div class="image">
          <img src="https://http.cat/500" alt="Erro 500" />
        </div>
        <div class="image">
          <img src="https://http.cat/501" alt="Erro 501" />
        </div>
        <div class="image">
          <img src="https://http.cat/502" alt="Erro 502" />
        </div>
        <div class="image">
          <img src="https://http.cat/503" alt="Erro 503" />
        </div>
        <div class="image">
          <img src="https://http.cat/504" alt="Erro 504" />
        </div>
        <div class="image">
          <img src="https://http.cat/506" alt="Erro 506" />
        </div>
      </div>
    </main>
    <footer>
      <p>
        Imagens obtidas do site <a href="https://http.cat/">http.cat</a> &copy;
        HTTP Gato
      </p>
    </footer>
  </body>
</html>
```

E o conteúdo abaixo em um arquivo `style.css`, o arquivo CSS tem que estar na mesma pasta do arquivo HTML, caso você queira colocar em outra pasta não se esqueça de mudar o caminho do link no arquivo HTML:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

img {
  width: 200px;
  height: 200px;
}
```

Os prints dos exemplos usados foram feitos usando o tamanho da página como sendo de um laptop (1440px, 900px), você pode utilizar a extensão [Window Resizer](https://chrome.google.com/webstore/detail/window-resizer/kkelicaakdanhinjdeammmilcgefonfh) para a desenvolver a página no mesmo tamanho.

Agora a prática!
  1. Altere o CSS para que a logo e o nome do site fiquem lado a lado, faça a mesma coisa para os itens da tag `nav`;
    ![ex-01](https://drive.google.com/uc?export=view&id=1R-LOEpgfeHu1tlLqnybyatKaySPTTgA7)

  2. Agora faça com que o conteúdo do `header` fique em uma linha e separados entre si e com um espaço entre as bordas horizontais do seu contêiner;
    ![ex-02](https://drive.google.com/uc?export=view&id=15Ul5Icksy1ji_hSlpdWWSjXGqfffLJnm)

  3. Adicione um espaçamento entre os itens de navegação;
    ![ex-03](https://drive.google.com/uc?export=view&id=1PPEYhJEXc9grGUQiDtCE0ZbvkPoRDKwh)

  4. Estilize o `header` da sua maneira, segue um exemplo, mas fique a vontade para estilizar do jeito que o seu coração mandar!;
    Exemplo:
    ![ex-04](https://drive.google.com/uc?export=view&id=1-jL6lGHcct8gntp6QMvNmxAjOA_TkX4J)

  5. Agora você tem que transformar a `div` com a classe `.images-container` em um flex contêiner que, caso o tamanho dos flex itens ultrapasse o tamanho da `div`, adicione novas linhas;
    ![ex-05](https://drive.google.com/uc?export=view&id=1p50TlNaG5BJc0aL6RsbNatx8hFbx_NWe)

  6. Que tal alinhar as imagens de forma a utilizar toda a largura da página e adicionar espaços em volta dos flex itens? Adicione também um `padding` para a tag `div` com classe `.image`;
    Sua página deve ficar algo próximo a este exemplo:
    ![ex-06](https://drive.google.com/uc?export=view&id=1Niw7H7q2YBmHCprFcqIwHXT6CF8vb9Et)

  7. Para finalizar adicione alguns estilos no `footer` para combinar com os estilos utilizados no `header`, tente focar nas propriedades do Flexbox;
  Exemplo:
    ![ex-07](https://drive.google.com/uc?export=view&id=1rSOqjFkjZYoPsJxhr0t-Ikx_TlpW3S1p)

  8. Agora que você já organizou bem a página que tal um desafio? Agrupe cada imagem em sua respectiva seção de [códigos de status de respostas HTTP](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Status) *(não precisa entender o que cada um significa pois você verá isso em outro bloco)* e adicione um título para cada seção. Fique a vontade para alterar o HTML da forma que você achar que for melhor;
  Seções:
    Respostas de **informação** (100-199);
    Respostas de **sucesso** (200-299);
    **Redirecionamentos** (300-399);
    Erros do **cliente** (400-499);
    Erros do **servidor** (500-599).
  Tente obter algo parecido com este exemplo:
    ![ex-08](https://drive.google.com/uc?export=view&id=1Fh-tz6WlDjk6lr6ROJ8f79jXggB7_GB-)

~~Por hoje eh soh pessoal!~~ Agora que você finalizou os exercícios, que tal fazer os exercícios extras para treinar sobre as propriedades dos flex itens? *(Você pode utilizar os mesmos arquivos que criou nestes exercícios, ou se preferir, copiar o gabarito do exercício 8)*

### Exercícios extras

Uma pessoa desenvolvedora gostou muito da pagina que você criou e pediu alguns ajustes para poder começar a usar a página para lecionar novas pessoas desenvolvedoras sobre os códigos HTTP:
  1. Ela percebeu que os métodos mais acessados são os erros, então pediu para que as seções de erro estivessem antes das demais seções;
  ![ex-extra-01](https://drive.google.com/uc?export=view&id=1NWoC7Wv-Vi_u4AuRJCz7B_lhsI8sx-oE)

  2. Foi pedido também para fazer o mesmo com os links da barra de navegação;
  ![ex-extra-02](https://drive.google.com/uc?export=view&id=1SempZvSMkZDL53FmV8DhPCeEEOQb5qza)

  3. Ela achou o tamanho das imagens pequeno demais e pediu para que o valor base para cada uma fosse de `400px`; *(não esqueça de alterar a `width` e `height` da tag `img` para `100%` para ter efeito)*
  ![ex-extra-03](https://drive.google.com/uc?export=view&id=1QgHQ0ta9-LId4LyfeUoZ9xUEnCVKINA4)

  4. Ela também pediu para que as imagens da direita aumentassem em uma razão de `2`; *(Diminua a largura da página para ver o resultado)*
  ![ex-extra-04](https://drive.google.com/uc?export=view&id=1Hwt8sNrzHovmEkkhThyZrajVF-OqXqkh)

  5. Para finalizar, ela pediu para adicionar os códigos de cada seção, depois do título. E que cada código que ocupe uma posição ímpar diminua de tamanho em uma razão maior que os outros.
  Lista dos códigos usados na página *(existem outros)*:
  * 100, 101, 102;
  * 200, 201, 202, 204, 206, 207;
  * 300, 301, 302, 303, 304, 305, 307, 308;
  * 400, 401, 402, 404, 405, 406, 408, 409;
  * 500, 501, 502, 503, 504, 506.
    Siga as instruções:
    5.1. Crie uma `div` e insira os códigos dentro de um parágrafo;
    5.2. Coloque os códigos na mesma linha;
    5.3. Defina um tamanho base para os parágrafos de `100px`;
    5.4. Defina uma cor de fundo para os parágrafos;
    5.5. Faça com que os parágrafos em posição ímpar diminuam numa razão de `2`;
    5.6. Mude a cor de fundo dos parágrafos em posição ímpar para melhor verificar o comportamento do item anterior. *(Não se esqueça de diminuir a largura da página para verificar o efeito)*
  ![ex-extra-05](https://drive.google.com/uc?export=view&id=1H0P13H2tmwhiWRtQCl0d4pCRt0aGK15E)

## Recursos Adicionais

[Guia de Flexbox escrito pela MDN](https://developer.mozilla.org/pt-BR/docs/Learn/CSS/CSS_layout/Flexbox "MDN")

[CSS FlexBox: Um Guia Visual](https://www.alura.com.br/artigos/css-guia-do-flexbox?gclid=EAIaIQobChMIleKjwumu8AIV0AaICR20pA9hEAAYASAAEgIxcvD_BwE "Alura")

[Guia completo para Flexbox (em inglês)](https://css-tricks.com/snippets/css/a-guide-to-flexbox/ "CSS-Tricks")

[Ajude o Froggy e seus amigos utilizando CSS](https://flexboxfroggy.com/ "Flexbox Froggy")

[Aprenda Flexbox com um jogo de tower defense](http://www.flexboxdefense.com/ "Flebox Defense")

[Escreva comandos do Flexbox para se defender de zumbis](https://mastery.games/flexboxzombies/ "Flexbox Zombies")

## Gabarito

### HTTP Gato

Gabarito dos exercícios:
  1. Altere o CSS para que a logo e o nome do site fiquem lado a lado, faça a mesma coisa para os itens da tag `nav`;
  ```css
  #home {
    display: flex;
  }

  .links ul {
    display: flex;
  }
  ```

  2. Agora faça com que o conteúdo do `header` fique em uma linha e separados entre si e com um espaço entre as bordas horizontais do seu contêiner;
  ```css
  header {
    display: flex;
    justify-content: space-around;
  }
  ```

  3. Adicione um espaçamento entre os itens de navegação;
  ```css
  .links {
    width: 60%;
  }

  .links ul {
    display: flex;
    justify-content: space-between;
  }
  ```

  4. Estilize o `header` da sua maneira, segue um exemplo, mas fique a vontade para estilizar do jeito que o seu coração mandar!;
  CSS para o exemplo apresentado:
  ```css
  header {
    display: flex;
    justify-content: space-around;
    align-items: center;
    background-color: black;
    color: darkred;
  }

  header a {
    text-decoration: none;
    color: darkred;
    font-weight: 900;
  }

  #logo {
    margin-right: 0.5em;
  }

  #home {
    display: flex;
  }

  .links {
    width: 60%;
  }

  .links ul {
    display: flex;
    justify-content: space-between;
    list-style: none;
  }

  .links ul li {
    padding: 0.25em;
    font-weight: 600;
    cursor: pointer;
  }
  ```

  5. Agora você tem que transformar a `div` com a classe `.images-container` em um flex contêiner que, caso o tamanho dos flex itens ultrapasse o tamanho da `div`, adicione novas linhas;
  ```css
  .images-container {
    display: flex;
    flex-wrap: wrap;
  }
  ```

  6. Que tal alinhar as imagens de forma a utilizar toda a largura da página e adicionar espaços em volta dos flex itens? Adicione também um `padding` para a tag `div` com classe `.image`;
  ```css
  .images-container {
    display: flex;
    justify-content: space-around;
    align-content: flex-start;
    flex-wrap: wrap;
  }

  .image {
    padding: 1em;
  }
  ```

  7. Para finalizar adicione alguns estilos no `footer` para combinar com os estilos utilizados no `header`, tente focar nas propriedades do Flexbox;
  ```css
  footer {
    background-color: black;
    color: darkred;
    padding: 0.5em;
    display: flex;
    justify-content: center;
  }

  footer a {
    text-decoration: none;
    color: darkred;
    font-weight: 900;
  }
  ```

  8. Agora que você já organizou bem a pagpáginaina que tal um desafio? Agrupe cada imagem em sua respectiva seção de [códigos de status de respostas HTTP](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Status) *(não precisa entender o que cada um significa pois você verá isso em outro bloco)* e adicione um título para cada seção. Fique a vontade para alterar o HTML da forma que você achar que for melhor;
  Arquivo index.html:
  ```html
  <!DOCTYPE html>
  <html lang="pt-br">
    <head>
      <meta charset="UTF-8" />
      <meta http-equiv="X-UA-Compatible" content="IE=edge" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title>Flexbox - HTTP Gato</title>
      <link
        rel="stylesheet"
        href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.2/css/all.min.css"
        integrity="sha512-HK5fgLBL+xu6dm/Ii3z4xhlSUyZgTT9tuc/hSrtw6uzJOvgRr2a9jyxxT1ely+B+xFAmJKVSTbpM/CuL7qxO8w=="
        crossorigin="anonymous"
      />
      <link rel="stylesheet" href="style.css" />
    </head>
    <body>
      <header>
        <a href="#" id="home">
          <i id="logo" class="fas fa-cat"></i>
          <p>HTTP Gato</p>
        </a>
        <nav class="links">
          <ul>
            <li>Informação</li>
            <li>Sucesso</li>
            <li>Redirecionamentos</li>
            <li>Cliente</li>
            <li>Servidor</li>
          </ul>
        </nav>
      </header>
      <main>
        <section id="information">
          <h1>Respostas de informação</h1>
          <div class="images-container">
            <div class="image">
              <img src="https://http.cat/100" alt="Erro 100" />
            </div>
            <div class="image">
              <img src="https://http.cat/101" alt="Erro 101" />
            </div>
            <div class="image">
              <img src="https://http.cat/102" alt="Erro 102" />
            </div>
          </div>
        </section>
        <section id="success">
          <h1>Respostas de sucesso</h1>
          <div class="images-container">
            <div class="image">
              <img src="https://http.cat/200" alt="Erro 200" />
            </div>
            <div class="image">
              <img src="https://http.cat/201" alt="Erro 201" />
            </div>
            <div class="image">
              <img src="https://http.cat/202" alt="Erro 202" />
            </div>
            <div class="image">
              <img src="https://http.cat/204" alt="Erro 204" />
            </div>
            <div class="image">
              <img src="https://http.cat/206" alt="Erro 206" />
            </div>
            <div class="image">
              <img src="https://http.cat/207" alt="Erro 207" />
            </div>
          </div>
        </section>
        <section id="redirection">
          <h1>Redirecionamentos</h1>
          <div class="images-container">
            <div class="image">
              <img src="https://http.cat/300" alt="Erro 300" />
            </div>
            <div class="image">
              <img src="https://http.cat/301" alt="Erro 301" />
            </div>
            <div class="image">
              <img src="https://http.cat/302" alt="Erro 302" />
            </div>
            <div class="image">
              <img src="https://http.cat/303" alt="Erro 303" />
            </div>
            <div class="image">
              <img src="https://http.cat/304" alt="Erro 304" />
            </div>
            <div class="image">
              <img src="https://http.cat/305" alt="Erro 305" />
            </div>
            <div class="image">
              <img src="https://http.cat/307" alt="Erro 307" />
            </div>
            <div class="image">
              <img src="https://http.cat/308" alt="Erro 308" />
            </div>
          </div>
        </section>
        <section id="client">
          <h1>Erros do cliente</h1>
          <div class="images-container">
            <div class="image">
              <img src="https://http.cat/400" alt="Erro 400" />
            </div>
            <div class="image">
              <img src="https://http.cat/401" alt="Erro 401" />
            </div>
            <div class="image">
              <img src="https://http.cat/402" alt="Erro 402" />
            </div>
            <div class="image">
              <img src="https://http.cat/404" alt="Erro 404" />
            </div>
            <div class="image">
              <img src="https://http.cat/405" alt="Erro 405" />
            </div>
            <div class="image">
              <img src="https://http.cat/406" alt="Erro 406" />
            </div>
            <div class="image">
              <img src="https://http.cat/408" alt="Erro 408" />
            </div>
            <div class="image">
              <img src="https://http.cat/409" alt="Erro 409" />
            </div>
          </div>
        </section>
        <section id="server">
          <h1>Erros do servidor</h1>
          <div class="images-container">
            <div class="image">
              <img src="https://http.cat/500" alt="Erro 500" />
            </div>
            <div class="image">
              <img src="https://http.cat/501" alt="Erro 501" />
            </div>
            <div class="image">
              <img src="https://http.cat/502" alt="Erro 502" />
            </div>
            <div class="image">
              <img src="https://http.cat/503" alt="Erro 503" />
            </div>
            <div class="image">
              <img src="https://http.cat/504" alt="Erro 504" />
            </div>
            <div class="image">
              <img src="https://http.cat/506" alt="Erro 506" />
            </div>
          </div>
        </section>
      </main>
      <footer>
        <p>
          Imagens obtidas do site <a href="https://http.cat/">http.cat</a> &copy;
          HTTP Gato
        </p>
      </footer>
    </body>
  </html>
  ```
  Arquivo style.css:
  ```css
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  img {
    width: 200px;
    height: 200px;
  }

  header {
    display: flex;
    justify-content: space-around;
    align-items: center;
    background-color: black;
    color: darkred;
  }

  header a {
    text-decoration: none;
    color: darkred;
    font-weight: 900;
  }

  #logo {
    margin-right: 0.5em;
  }

  #home {
    display: flex;
  }

  .links {
    width: 60%;
  }

  .links ul {
    display: flex;
    justify-content: space-between;
    list-style: none;
  }

  .links ul li {
    padding: 0.25em;
    font-weight: 600;
    cursor: pointer;
  }

  section {
    display: flex;
    align-items: center;
    flex-direction: column;
  }

  .images-container {
    width: 100%;
    display: flex;
    justify-content: space-around;
    align-content: flex-start;
    flex-wrap: wrap;
  }

  .image {
    padding: 1em;
  }

  footer {
    background-color: black;
    color: darkred;
    padding: 0.5em;
    display: flex;
    justify-content: center;
  }

  footer a {
    text-decoration: none;
    color: darkred;
    font-weight: 900;
  }
  ```

### Exercícios extras

Gabarito dos exercícios extras:
  1. Ela percebeu que os métodos mais acessados são os erros, então pediu para que as seções de erro estivessem antes das demais seções;
  ```css
  main {
    display: flex;
    flex-direction: column;
  }

  #client, #server {
    order: -1;
  }
  ```

  2. Foi pedido também para fazer o mesmo com os links da barra de navegação;
  ```css
  .links ul li:nth-child(4),
  .links ul li:nth-child(5) {
    order: -1;
  }
  ```

  3. Ela achou o tamanho das imagens pequeno demais e pediu para que o valor base para cada uma fosse de `400px`;
  ```css
  img {
    width: 100%;
    height: 100%;
  }

  .image {
    flex-basis: 400px;
  }
  ```

  4. Ela também pediu para que as imagens da direita aumentassem em uma razão de `2`;
  ```css
  .image:nth-child(even) {
    flex-grow: 2;
  }
  ```

  5. Para finalizar, ela pediu para adicionar os códigos de cada seção, depois do título. E que cada código que ocupe uma posição ímpar diminua de tamanho em uma razão maior que os outros.
  Arquivo index.html:
  ```html
  <!DOCTYPE html>
  <html lang="pt-br">
    <head>
      <meta charset="UTF-8" />
      <meta http-equiv="X-UA-Compatible" content="IE=edge" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title>Flexbox - HTTP Gato</title>
      <link
        rel="stylesheet"
        href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.2/css/all.min.css"
        integrity="sha512-HK5fgLBL+xu6dm/Ii3z4xhlSUyZgTT9tuc/hSrtw6uzJOvgRr2a9jyxxT1ely+B+xFAmJKVSTbpM/CuL7qxO8w=="
        crossorigin="anonymous"
      />
      <link rel="stylesheet" href="style.css" />
    </head>
    <body>
      <header>
        <a href="#" id="home">
          <i id="logo" class="fas fa-cat"></i>
          <p>HTTP Gato</p>
        </a>
        <nav class="links">
          <ul>
            <li>Informação</li>
            <li>Sucesso</li>
            <li>Redirecionamentos</li>
            <li>Cliente</li>
            <li>Servidor</li>
          </ul>
        </nav>
      </header>
      <main>
        <section id="information">
          <h1>Respostas de informação</h1>
          <div class="codes">
            <p>100</p>
            <p>101</p>
            <p>102</p>
          </div>
          <div class="images-container">
            <div class="image">
              <img src="https://http.cat/100" alt="Erro 100" />
            </div>
            <div class="image">
              <img src="https://http.cat/101" alt="Erro 101" />
            </div>
            <div class="image">
              <img src="https://http.cat/102" alt="Erro 102" />
            </div>
          </div>
        </section>
        <section id="success">
          <h1>Respostas de sucesso</h1>
          <div class="codes">
            <p>200</p>
            <p>201</p>
            <p>202</p>
            <p>204</p>
            <p>206</p>
            <p>207</p>
          </div>
          <div class="images-container">
            <div class="image">
              <img src="https://http.cat/200" alt="Erro 200" />
            </div>
            <div class="image">
              <img src="https://http.cat/201" alt="Erro 201" />
            </div>
            <div class="image">
              <img src="https://http.cat/202" alt="Erro 202" />
            </div>
            <div class="image">
              <img src="https://http.cat/204" alt="Erro 204" />
            </div>
            <div class="image">
              <img src="https://http.cat/206" alt="Erro 206" />
            </div>
            <div class="image">
              <img src="https://http.cat/207" alt="Erro 207" />
            </div>
          </div>
        </section>
        <section id="redirection">
          <h1>Redirecionamentos</h1>
          <div class="codes">
            <p>300</p>
            <p>301</p>
            <p>302</p>
            <p>303</p>
            <p>304</p>
            <p>305</p>
            <p>307</p>
            <p>308</p>
          </div>
          <div class="images-container">
            <div class="image">
              <img src="https://http.cat/300" alt="Erro 300" />
            </div>
            <div class="image">
              <img src="https://http.cat/301" alt="Erro 301" />
            </div>
            <div class="image">
              <img src="https://http.cat/302" alt="Erro 302" />
            </div>
            <div class="image">
              <img src="https://http.cat/303" alt="Erro 303" />
            </div>
            <div class="image">
              <img src="https://http.cat/304" alt="Erro 304" />
            </div>
            <div class="image">
              <img src="https://http.cat/305" alt="Erro 305" />
            </div>
            <div class="image">
              <img src="https://http.cat/307" alt="Erro 307" />
            </div>
            <div class="image">
              <img src="https://http.cat/308" alt="Erro 308" />
            </div>
          </div>
        </section>
        <section id="client">
          <h1>Erros do cliente</h1>
          <div class="codes">
            <p>400</p>
            <p>401</p>
            <p>402</p>
            <p>404</p>
            <p>405</p>
            <p>406</p>
            <p>408</p>
            <p>409</p>
          </div>
          <div class="images-container">
            <div class="image">
              <img src="https://http.cat/400" alt="Erro 400" />
            </div>
            <div class="image">
              <img src="https://http.cat/401" alt="Erro 401" />
            </div>
            <div class="image">
              <img src="https://http.cat/402" alt="Erro 402" />
            </div>
            <div class="image">
              <img src="https://http.cat/404" alt="Erro 404" />
            </div>
            <div class="image">
              <img src="https://http.cat/405" alt="Erro 405" />
            </div>
            <div class="image">
              <img src="https://http.cat/406" alt="Erro 406" />
            </div>
            <div class="image">
              <img src="https://http.cat/408" alt="Erro 408" />
            </div>
            <div class="image">
              <img src="https://http.cat/409" alt="Erro 409" />
            </div>
          </div>
        </section>
        <section id="server">
          <h1>Erros do servidor</h1>
          <div class="codes">
            <p>500</p>
            <p>501</p>
            <p>502</p>
            <p>503</p>
            <p>504</p>
            <p>506</p>
          </div>
          <div class="images-container">
            <div class="image">
              <img src="https://http.cat/500" alt="Erro 500" />
            </div>
            <div class="image">
              <img src="https://http.cat/501" alt="Erro 501" />
            </div>
            <div class="image">
              <img src="https://http.cat/502" alt="Erro 502" />
            </div>
            <div class="image">
              <img src="https://http.cat/503" alt="Erro 503" />
            </div>
            <div class="image">
              <img src="https://http.cat/504" alt="Erro 504" />
            </div>
            <div class="image">
              <img src="https://http.cat/506" alt="Erro 506" />
            </div>
          </div>
        </section>
      </main>
      <footer>
        <p>
          Imagens obtidas do site <a href="https://http.cat/">http.cat</a> &copy;
          HTTP Gato
        </p>
      </footer>
    </body>
  </html>
  ```

  Arquivo style.css:
  ```css
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  img {
    width: 100%;
    height: 100%;
  }

  header {
    display: flex;
    justify-content: space-around;
    align-items: center;
    background-color: black;
    color: darkred;
  }

  header a {
    text-decoration: none;
    color: darkred;
    font-weight: 900;
  }

  #logo {
    margin-right: 0.5em;
  }

  #home {
    display: flex;
  }

  .links {
    width: 60%;
  }

  .links ul {
    display: flex;
    justify-content: space-between;
    list-style: none;
  }

  .links ul li {
    padding: 0.25em;
    font-weight: 600;
    cursor: pointer;
  }

  section {
    display: flex;
    align-items: center;
    flex-direction: column;
  }

  .images-container {
    width: 100%;
    display: flex;
    justify-content: space-around;
    align-content: flex-start;
    flex-wrap: wrap;
  }

  .image {
    padding: 1em;
  }

  footer {
    background-color: black;
    color: darkred;
    padding: 0.5em;
    display: flex;
    justify-content: center;
  }

  footer a {
    text-decoration: none;
    color: darkred;
    font-weight: 900;
  }

  main {
    display: flex;
    flex-direction: column;
  }

  #client, #server {
    order: -1;
  }

  .links ul li:nth-child(4),
  .links ul li:nth-child(5) {
    order: -1;
  }

  .image {
    flex-basis: 400px;
  }

  .image:nth-child(even) {
    flex-grow: 2;
  }

  .codes {
    width: 100%;
    display: flex;
    justify-content: center;
  }

  .codes p {
    background-color: black;
    color: white;
    padding: 5px 0;
    font-weight: 600;
    text-align: center;
    flex-basis: 100px;
  }

  .codes p:nth-child(odd) {
    background-color: darkgray;
    flex-shrink: 2;
  }
  ```
