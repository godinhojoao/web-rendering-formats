# Formatos de renderização de páginas web

## O que é SSG ?

### Static site generation
 - Basicamente um site estático: HTML, CSS E JS.
 - Por exemplo, um site gerado com hexo ou GatsbyJS.

#### Fluxo para o usuário:
- https://www.youtube.com/watch?v=1zhT23VDVDc&ab_channel=FranckAbgrall
- Buscas prévias em APIs já foram realizadas para buildar todas as páginas possíveis.
- Ao digitar a url do site no mecanismo de busca a primeira vez e acessar o site:
  - A CDN busca a página solicitada e renderiza ela, sem grandes carregamentos e necessidade de servidor.
- Caso o usuário abra outra página:
  - Novamente o mesmo processo é repetido e a tela é renderizada rapidamente. Pois não tem nenhum carregamento no client ou no servidor.

#### Pontos positivos ?
- Performance: são mais performáticos que as outras abordagens por serem simples html, css e js.
- Custo: pois podem ser hospedados de qualquer forma, inclusive em CDNs que são mais baratas e performáticas que servidores convencionais.
- Segurança: por serem simples html, css e js, sem grandes infraestruturas os sites estáticos são menos suscetíveis a vulnerabilidades.

#### Pontos negativos ?
- À medida que o número de páginas cresce o tempo de build aumenta consideravelmente, não sendo possível utilizar para sites com conteúdos dinâmicos.
  - Causando dificuldade para escalar aplicações grandes, com muitas páginas.
- Dificuldade para relizar atualizações constantes no conteúdo do site. Pois depois de toda alteração é necessário gerar o build novamente.

#### Quando desenvolver um site utilizando SSG ?
- Site simples, sem muita interação do usuário.
- Pouca alteração no conteúdo.
- Poucas páginas.
- Quando a performance é essencial.

Exemplos: Landing page, blogs com poucas alterações no conteúdo ou portfólios.

#### Como desenvolver um site utilizando SSG ?
- Podemos fazer isso utilizando o framework NextJS.

---------------------------------------------------------

## O que é CSR ?

### Single page aplication
  - O que estamos mais acostumados a utilizar, as famosas SPAs.
  - Nas quais o cliente recupera informações de APIs e renderiza o HTML no lado do cliente.

#### Fluxo para o usuário:
- https://www.youtube.com/watch?v=4-Lel1oaV7M&ab_channel=FranckAbgrall
- Ao digitar a url do site no mecanismo de busca a primeira vez e acessar o site:
  - A página inicia branca para carregar o HTML e SCRIPTS principais, por exemplo, o "index.html".
  - Após isso a página pode ter uma tela de carregamento, para os dados serem buscados na API.
  - Após tudo ser buscado na API a página é renderizada da forma esperada.
- Caso o usuário abra outra página:
  - A tela de carregamento aparece direto, pois a estrutura principal já foi carregada.
  - Depois a busca na API é realizada.
  - Por fim, a renderização da página.

#### Pontos positivos ?
- Páginas ricas em interações sem precisar recarregar, por exemplo a navegação, etc...
- Site mais rápido após o primeiro loading. O primeiro loading é o mais demorado em uma SPA.

#### Pontos negativos ?
- Load inicial pode ser muito grande.
- Performance pode ser imprevisível, pois em algumas páginas podemos ter mais Javascript e em outras menos.
  - Algumas vezes buscamos mais dados na API, tendo que renderizar mais ou menos elementos dependendo, fazendo com que a performance seja variante.
- Rankeamento em mecanismos de buscas prejudicados ( SEO ).
  - Atualmente o google consegue indexar algumas partes da aplicação SPA, no entanto, o google ainda não espera o conteúdo todo ser carregado para indexar. Prejudicando assim o "SEO" do site.

#### Quando desenvolver um site utilizando CSR ?
- Quando a indexação em mecanismos de busca não for prioridade.
- Quando o usuário interage muito com a página e não queremos diversos refreshs a cada interação.
- Quando as informações vão ser diferentes para cada usuário, no caso de autenticações, por exemplo.

Exemplos: Twitter web, Facebook Web, Spotify Web.

#### Como desenvolver um site utilizando CSR ?
- Podemos fazer isso utilizando HTML, CSS E JS vanilla ou até mesmo utilizando algum framework para construção de SPAs como, por exemplo, Angular ou ReactJS.

---------------------------------------------------------

## O que é SSR ?

### Server side rendering
  - Basicamente a renderização da página toda no lado do servidor e a entrega do site totalmente "montado" para o cliente com HTML, CSS, etc...

#### Fluxo para o usuário:
- https://www.youtube.com/watch?v=0bvo6UKkNDA&ab_channel=FranckAbgrall
- Ao digitar a url do site no mecanismo de busca a primeira vez e acessar o site:
  - Uma chamada é feita no servidor, o servidor pega os dados em uma API.
  - Após isso ele cria o HTML, estilos, etc...
  - E envia tudo renderizado para o cliente.
- Caso o usuário abra outra página:
  - O processo é repetido, toda vez que o usuário navegar entre as páginas.

#### Pontos positivos ?
- Ótimo em SEO.
- Melhor performance para o usuário. ( Conteúdo visto mais rápido que no SPA )
- Código compartilhado com o backend em NodeJS.
- Menor processamento no lado do usuário.

#### Pontos negativos ?
- Time to first byte (TTFB) maior, o servidor precisa preparar todo conteúdo para enviar.
  - O conteúdo é exibido mais rápido, no entanto, a tela fica toda em branco antes disso acontecer.
- Reload completo após mudar rota.
  - Podemos prevenir isso, no entanto, é um comportamento padrão em sites que utilizam SSR.
- Custo elevado e alta demanda do servidor.

#### Quando desenvolver um site utilizando SSR ?
- Quando tem necessidades de um SPA, mas com maior performance.
- Conteúdo muda com muita frequência.
- Rankeamento em mecanismos de busca priorizado ( SEO ).

Exemplos: Ecommerce, Sites de Notícias.

### Como desenvolver um site utilizando SSR ?
- Podemos fazer isso utilizando nodejs, express e ejs.

---------------------------------------------------------

## Nextjs
- Com NextJs conseguimos desenvolver qualquer uma das abordagens mencionadas. Podendo até mesmo desenvolver o que é chamado de Incremental Site Regeneration ( ISR ), ou "abordagem híbrida".
- Fazendo com que possamos escalar a abordagem estática para milhares de páginas. Buildando as páginas em "tempo real".

## Slides:
- https://docs.google.com/presentation/d/e/2PACX-1vTJbTgIxw8bDIMAL8vV1NBn7rZ0dH0ymlI_gXz5B4vHAdCBVokP2T-6w7P0z7-qEw/pub?start=false&loop=false&delayms=60000