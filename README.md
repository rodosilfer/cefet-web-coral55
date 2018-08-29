# cefet-web-coral55

Um cardápio das gostosuras marítimas servidas na Lanchonete do Coral 55.

## Atividade

Você deve estilizar a página do cardápio (arquivo `index.html`) de forma a
implementar o _comprehensive layout_ criado por um _designer_ (arquivo
`coral55-comp.png`). Você deve usar a especificação do _layout_ (arquivo
`coral55-specs.png`).

### Diretrizes do Exercício

Aqui estão os itens que precisam ser implementados:

1. Use elementos semânticos no lugar de `<div></div>` e `<span></span>`
  sempre que um deles existir.
1. Use a fonte "Ravie" que está inclusa no projeto, dentro da pasta `fonts`.
1. Estude qual o melhor seletor CSS para cada situação.
1. Use espaçamento (vertical) duplo para os itens do cardápio.
1. Inclua o `<script></script>` `js/bubbles.js`.
1. Lembre-se de como funciona o _box-model_ na hora de definir as dimensões
  dos elementos.
1. Lembre-se de que elementos posicionados de forma `absolute` têm seu como
  seu sistema de coordenadas o **seu ancestral mais próximo que esteja com
  posicionamento não-estático** (_i.e._, `position: [absolute, relative,
  fixed]`).
  - Tipicamente colocamos `position: relative;` no elemento pai de um elemento
    com `position: absolute;` para servir de sistema de coordenadas.

### Roteiro

Minha sugestão é escolher cada parte da página para estilizar. Eu fiz na
seguinte ordem:

1. Estilização do recipiente geral da página (`#recipiente`) - [como ficou][passo1]
1. Estilização do cabeçalho (`header`) - [como ficou][passo2]
1. Estilização da seção lateral (`#lateral`) - [como ficou][passo3]
   - Esta é a parte mais demorada da atividade prática
   - Além de estilizar essa seção, também tirei `#cardapio` de baixo dela
   - Deixe a lateral com `position` absolute e posicionado no topo e o `#recipiente` com position relative. Assim, defina o `height` como 100% para que ele ocupe 100% do recipiente (a altura de um elemento também é relacionado com seu ancestral não estático mais próximo).
1. Estilização do cardápio (`#cardapio`) - [como ficou][passo4]
1. Estilização do rodapé (`footer`) - [como ficou][passo5]
1. Estilização do _ticket_ (`#ticket`) - [como ficou][passo6]

[passo1]: https://github.com/daniel-hasan/cefet-web-coral55/raw/gh-pages/roteiro/passo1.png
[passo2]: https://github.com/daniel-hasan/cefet-web-coral55/raw/gh-pages/roteiro/passo2.png
[passo3]: https://github.com/daniel-hasan/cefet-web-coral55/raw/gh-pages/roteiro/passo3.png
[passo4]: https://github.com/daniel-hasan/cefet-web-coral55/raw/gh-pages/roteiro/passo4.png
[passo5]: https://github.com/daniel-hasan/cefet-web-coral55/raw/gh-pages/roteiro/passo5.png
[passo6]: https://github.com/daniel-hasan/cefet-web-coral55/raw/gh-pages/roteiro/passo6.png


### <abbr title="Frequently Asked Questions">FAQ</abbr>

- Para rotacionar um elemento no sentido horário:

  ```css
  #elemento {
    transform: rotate(45deg); /* dado em graus, sentido horário */
  }
  ```
- Para fazer uma transição suave da posição `left` de um elemento, usamos
  a propriedade `transition`:

  ```css
  #elemento {
    /* ... */
    left: -100px;
    transition: left 100ms ease-out; /* propriedade, duração, interpolação */
  }
  #element:hover {
    left: 0;
  }
  ```
- Centralizando um elemento `block` cuja largura é sempre a mesma:

  ```css
  #elemento {
    width: /* um valor */;
    margin-left: auto;
    margin-right: auto;
  }
  ```
- Meu degradê não está funcionando... por quê?
  - Possivelmente, você está atribuindo um `linear-gradient(...)` para a
    propriedade `background-color`, mas um degradê é, para o CSS, um
    `background-image`
