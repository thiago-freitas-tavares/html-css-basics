# Front-End vs. Back-End

## Front-End Developer

- Projeta o aspecto visual do website, incluindo fontes, cores, layout e gráficos.
- Linguagens: JavaScript, HTML, CSS.
- Frameworks: jQuery, AngularJS, SASS, Bootstrap, EmberJS, React, Vue.

## Back-End Developer

- Projeta a estrutura de dados, lógica e conexão com servidor, banco de dados e APIs.
- Linguagens: Python, Ruby, Java, PHP, C#.
- Framework: Django, Flask, Rails, Spring, Laravel, ASP.NET.

# Linguagens

## HTML (Hypertext Markup Language)

- Linguagem de marcação (markup) utilizada para definir os blocos de construção das páginas web (estrutura física).

## CSS (Cascading StyleSheet)

- Linguagem de estilo (styling) utilizada para estilizar as páginas web (efeitos visuais).

## JavaScript

- Linguagem de programação utilizada para adicionar funcionalidade às páginas web.

# Framework vs. Library (Biblioteca)

- Ambos são conjuntos de códigos reutilizáveis, desenvolvidos por outras pessoas, para facilitar e acelerar o desenvolvimento de aplicações mais complexas.
- A diferença é que a biblioteca tem foco em uma funcionalidade específica, enquanto o framework tenta fornecer todo o necessário para o desenvolvimento uma aplicação completa.

# Version Control System (VCS) ou Source Code Management (SCM) ou Revision Control System (RCS)

- Permite acompanhar as alterações em um código através da criação de versões, possibilitando o retorno para versões anteriores em caso de falha.
- Exemplos: Git, Subversion (SVN), Mercurial.

# WEB

## URL (Uniform Resource Locator)

- Endereço que permite localizar recursos (websites, imagens, vídeos, fontes) na internet.

## Modelo Cliente/Servidor (Client/Server)

- O cliente (browser) envia um HTTP request para o servidor (web server - computador que hospeda o recurso que se deseja acessar).
- O servidor (web server) devolve um HTTP response ao cliente (browser).

* HTTP (Hypertext Transfer Protocol): linguagem que permite a comunicação entre cliente e servidor.
* HTTPS = HTTP + Encryption.

`Exemplo de HTTP request:`
GET /index.html HTTP/1.1 (index.html é a página/arquivo e 1.1 é a versão HTTP)
Host: www.qqrcoisa.com
Accept-Language: pt-br

`Exemplo de HTTP response:`
HTTP/1.1 200 OK (número 200 representa o código do status, neste caso bem sucedido/OK)
Date: 06 out 2023 19:00
Content-Type: text/html

<!DOCTYPE html> (código HTML da homepage do website ou documento)
<html>
...
</html>

- O browser lê o código HTML recebido no HTTP response e constrói um `DOM (Document Object Model)`, que é um modelo representativo dos objetos e elementos (building blocks da página - parágrafo de texto, imagem, link) do documento HTML.
- No código do documento HTML haverá referência a outros recursos (imagens, vídeos, fontes), com endereços (URLs) específicos. Para cada recurso, o browser envia um diferente HTTP request ao servidor, sendo a maioria realizada em paralelo para que a página seja carregada o mais rápido possível.
- Após o browser receber o retorno de todos os recursos, ele renderiza o documento HTML na tela.

# Inspecionando HTTP request e HTTP response no DevTools do Google Chrome

`Windows Google Chrome`

- (3 pontos na vertical) -> Mais ferramentas -> Ferramentas do desenvolvedor (DevTools). [ctrl + shift + i]

`DevTools`

- Aba `Network` permite inspecionar o tráfico de rede (request/response) ao acessar um site. [ctrl + r - recarrega a página]
- A primeira request se refere ao homepage do website que se deseja acessar e as demais aos recursos adicionais referenciados.
- É possível clicar em cada request para acessar informações mais detalhadas (Headers, Preview, Response).

# Criando um documento HTML

- Na pasta `html-css` criar arquivo `index.html`, que representa a homepage do website.
- <!DOCTYPE html> é uma doctype declaration, que informa os browsers que este é um documento HTML5 (HTML não é case sensitive).

Elementos para definir a estrutura da webpage:

1. `html + tab` = <html> </html>: opening tag + closing tag.
2. `head + tab` = <head> </head>: passa informações sobre a página para o browser.
3. `title + tab` = <title> </title>: título da página que aparece no browser.
4. `body + tab` = <body> </body>: elementos que irão aparecer na página.

`index.html`: Botão Direito -> Open with Live Server [alt + L + alt + O]

- Abre no browser padrão o URL http://127.0.0.1:5500/index.html

* 127.0.0.1 = referencia o computador atual.
* 5500 = número da porta em que ocorre a comunicação com o web server.
* index.html = nome do arquivo.

# Criando um documento HTML que simula um tweet

5. `img + tab` = <img src="" alt="">: não possui closing tag, pois este elemento não pode ter elemento filho.

- `src` (source) representa o caminho onde a imagem está armazenada e `alt` (alternative text) representa o texto a ser exibido caso, por algum motivo, a imagem não possa ser exibida, mas também por questões de acessibilidade e compreensão dos sistemas de busca.

6. `p + tab` = <p> </p>: parágrafo que permite a inserção de texto, neste exemplo o @ do usuário e o corpo do tweet.

# Formatando os elementos do documento HTML com CSS

7. `style + tab` = <style> </style>: código CSS neste elemento.

- `img {}` alterar a width de uma imagem altera o height proporcionalmente.
- `img {}` border com metade do valor do width/height torna a imagem um círculo.
- `p {}` estiliza todos os parágrafos contidos no código, se quisermos estilizar um parágrafo específico, ele deve ser separado dos demais elementos através de um atributo chamado class (classification), que o coloca em uma categoria diferente.
- `class + tab` = class="": neste exemplo criamos a categoria username.
- `p.usename {}` = .username {}: o `p` pode ser retirado e esta regra será aplicada a todo elemento (indepoendente do tipo) classificado na categoria username.

- Os browsers ignoram espaço em branco no HTML e CSS, ou seja, compreendem o código independente da sua formatação (espaçamento das linhas e etc), porém, formatação é de extrema importância na leitura e manutenção de um código.
- A extensão Prettier é utilizada por milhões de desenvolvedores e se todos no mesmo time formatarem com a mesma extensão, isso resulta em uma padronização automática do código.

* Manual: [ctrl + shift + p] -> Format Document
* Automático: Engrenagem -> Settings -> Format on Save -> Check

# Inspecionando nossa Página no DevTools do Google Chrome

`DevTools`

- Aba `Elements` contém o DOM (Document Object Model) com todos os elementos que criamos e alguns elementos adicionados automaticamente pelo Live Server. Neste exemplo um elemento <script> </script>.
- Ao passar o mouse sobre um elemento, ele é marcado na tela. Ao clicar neste elemento, a Aba Secundária `Styles` apresenta as estilizações aplicadas a este elemento, sendo possível as habilitar/desabilitar através do check box e editá-las (up/down) para avaliar as mudanças em tempo real.
- O link à direita referencia a linha do documento HTML que está sendo alterada. Clicar neste link te leva para a Aba `Source` do código nesta linha específica. Lembrando que estas são somente simulações de alteração, carregar a página novamente retorna para a estilização original do documento HTML.

# Validando WebPages

`HTML Validator`

- O website `validator.w3.org` é um Markup Validation Service, que analisa códigos HTML com o intuito de identificar potenciais erros. Pode ser utilizado através de 3 métodos: URI (Uniform Resource Identifier), upload de documento ou entrada direta do código.

Validando o código em questão:

1. Warning: Consider adding a `lang` attribute to the `html` start tag to declare the language of this document.
   Esta é uma boa prática para avisar às ferramentas de busca qual a língua padrão da webpage -> `lang + tab` = lang="" (abreviação da língua entre os colchetes).
2. Error: The character encoding was not declared. Proceeding using windows-1252.
3. Info: Trailing slash on void elements has no effect and interacts badly with unquoted attribute values.

`CSS Validator`

- O website `jigsaw.w3.org/css-validator` é um CSS Validation Service, que analisa códigos CSS com o intuito de identificar potenciais erros.
- Neste exemplo, o código CSS está embutido dentro do código HTML, por isso realizaremos a validação através da entrada direta do código, mas em aplicações mais complexas a boa prática é separar o código CSS em outro arquivo.

Validando o código em questão:

1. Parabéns! Não foram encontrados erros na sua folha de estilo.

# Aprofundando nos Elementos

- `! + tab` = HTML Boilerplate (template básico em HTML)

# Elementos de Meta

- <meta charset="UTF-8">
- Character Set é um conjunto de caracteres utilizados para representar texto em um computador, com o mapeamento de cada caractere para um valor numérico. ASCII (American Standard Code for Information Interchange) foi o pioneiro, porém, representa apenas caracteres da língua inglesa. O mais utilizado hoje em dia é o UTF-8 (Unicode Transformation Format), que pode representar quase todos os caracteres do mundo.

- <meta name="viewport" content="width=device-width, initial-scale=1.0">
- Viewport representa a área poligonal (normalmente retangular) que está sendo exibida no momento. Neste elemento se configura a largura inicial e o fator de zoom, o que é importante para que a webpage seja exibida de forma coerente em todos dispositivos (celular, tablet, desktop).

- Exemplos adicionais:

- `meta:kw + tab` = <meta name="keywords" content="">
- Permite inserir palavras-chave para otimização do sistema de busca, mas hoje em dia a maioria não considera tanto essas palavras-chave.

- `meta:desc + tab` = <meta name="description" content="">
- Permite inserir uma descrição do website para ser exibido no resultado do sistema de busca

# Elementos de Texto

- `em + tab` = <em> </em>: enfatiza (emphasize) o texto dentro do elemento.
- Por padrão, a enfatização apresenta o texto em itálico, mas seu real intuito é de enfatizar o conteúdo para que os sitemas da busca possam extrair informações do documento HTML com mais facilidade. O itálico apenas como estilização deve ser feito em CSS. Dentro do elemento <style> </style> é possível alterar o padrão do emphasize com `em {}`.

- `strong + tab` = <strong> </strong>: representa forte importância, seriedade ou urgência para seu conteúdo.
- Por padrão, o elemento strong apresenta o texto em negrito, seu intuito é similar ao emphasize e dentro do elemento <style> </style> é possível alterar seu padrão com `strong {}`.

- Trick: Seleciona o Texto -> [ctrl + shift + p] -> Emmet: Wrap with Abbreviation -> `em` or `strong` or etc -> Enter

# Elementos de Cabeçalho (Heading)

- O HTML possui seis possibilidades de cabeçalho (h1 a h6), que se apresentam em negrito com diferentes tamanhos de fonte entre si, porém, seu objetivo é a definição de hierarquia entre os temas. Estilização deve ser feita em CSS.
- O cabeçalho h1 deve ser utilizado uma única vez na webpage, caso contrário, isso pode confundir os sistemas de busca sobre a real finalidade do site. Os demais níveis hierárquicos de heading podem ser utilizados mais de uma vez, conforme necessidade.

- `h1 + tab` = <h1> </h1> a `h6 + tab` = <h6> </h6>

# Caracteres Especiais (Entities)

- Se quisermos inserir em um elemento de texto uma palavra dentro dos símbolos de maior e menor que, ela não será exibida no site, pois o interpretador entende que trata-se da declaração de um elemento.
- Para resolver problemas como este, existe uma biblioteca de comandos de caracteres especiais (https://tools.w3cub.com/html-entities).
- Exemplos: &lt;palavra&gt; (<palavra>), &copy; (copiright) e &nbsp; (non-breaking space - para manter duas palavras na mesma linha qdo há quebra).

- Trick: `lorem50 + tab` = cria um dummy text com 50 palavras.

# Hyperlinks (Elemento de Âncora)

- `a + tab` = <a href=""></a>
- O elemento de âncora (anchor element) permite referenciar outro website através do seu href (hypertext reference), que pode ser um URL absoluto ou relativo.
- O URL absoluto é a informação para a localização do recurso de forma independente da página atual (protocolo + domínio + caminho). O URL relativo é a informação para a localização do recurso a partir da página atual.

- Neste caso, criaremos uma segunda página chamada `about.html` na pasta `company` para refereciarmos de forma relativa. Lembrando que o conteúdo do elemento anchor pode ser um texto, imagem, vídeo.
- Para retornar à pagina inicial, temos que criar um elemento âncora no `about.html` referenciando sua URL, e como neste caso estamos dentro da pasta `company`, temos que utilizar o comando `../` para retornar uma pasta acima. É possível repetir este comando para subir a qtd de pastas necessárias, mas nestes casos é bom avaliar se uma URL absoluta não seria mais interessante (neste caso `/index.html`).

- Acrescentando o atributo download dentro do elemento âncora é possível realizar o download do conteúdo através do hyperlink: `download + tab` = download="" (neste caso apagamos o `=""` pois o atributo não terá nenhum valor).
- Acrescentando uma identificação única aos cabeçalhos (`id + tab` = id="section-html") é possível criar um índice com hyperlinks (<a href="#section-html">HTML</a>). O `href` com apenas o `#` referencia o topo da página.
- Para acessar um website externo o conteúdo do `href` deve se uma referência absoluta e começar com o protocolo `https://`. Para que o website seja aberto em uma nova aba, temos que inserir o atributo `target="_blank"` no elemento âncora em questão.
- O comando `mailto:` no `href` permite criar um hyperlink que te direciona à aplicação padrão de e-mail com um novo e-mail pré-pronto para envio.

- PS: Link é o endereço que se deseja acessar. Hyperink é o elemento que o usuário clica para acessar o emdereço desejado.

# Imagens

- Determinar a altura e largura de exibição de uma imagem em CSS pode distorcê-la, dependendo da sua configuração original. Para evitar este problema, utilizamos a propriedade `object-fit: cover;`, que ajusta a imagem (crop) para que caiba dentro da caixa de altura e largura desejada.
