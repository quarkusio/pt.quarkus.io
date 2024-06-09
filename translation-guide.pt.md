# pt.quarkus.io Projeto de tradução - Guia de tradução

O projeto de tradução pt.quarkus.io está trabalhando na tradução de [quarkus.io](https://quarkus.io) para o Português Brasileiro.

## Método de tradução

[quarkus.io](https://quarkus.io) é um site estático desenvolvido em Jekyll e seu conteúdo em asciidoctor (.adoc).
O repositório está localizado em [quarkusio/quarkusio.github.io](https://github.com/quarkusio/quarkusio.github.io) e é publicado sob CC BY 3.0.
Neste projeto, usamos um utilitário chamado po4a para extrair texto de um arquivo .adoc, traduzi-lo, gravá-lo de volta no arquivo .adoc e compilá-lo para criar um site com versão em português.
O fluxo de trabalho de extração de texto usando po4a, aplicação de texto traduzido usando memória de tradução, tradução de rascunhos usando tradução automática e processamento de reescrita são automatizados pelo GitHub Actions neste repositório.
O texto extraído é armazenado no [diretório l10n](l10n) como um arquivo .po, que é um formato de arquivo que gerencia o texto traduzido.

## Contribuindo com a tradução

Se você quiser contribuir com a tradução, clone este repositório localmente, edite o arquivo .po no [diretório l10n](l10n) e envie um Pull-Request.
Você pode verificar o status da tradução de cada arquivo [aqui](l10n/stats/translation.csv).

## Declaração para iniciar a tradução

Para evitar inconvenientes, como vários membros trabalhando no mesmo arquivo ao mesmo tempo ou duplicação de trabalho.
Indique em qual arquivo e intervalo você deseja começar a trabalhar com um problema do GitHub.
Por outro lado, ao criar uma issue no GitHub, verifique se alguém já iniciou trabalho no destino de um problema existente no GitHub.

### Trabalho de tradução

O arquivo .po é um arquivo de texto, mas diversas ferramentas auxiliam na edição. Por exemplo, [POEdit](https://poedit.net/)
Ele suporta execução em Windows/Mac/Linux e possui inúmeras teclas de atalho, tornando-o conveniente para uso durante a edição.

### Importação e tradução automática de destinos de tradução

Quando [quarkus.io](https://quarkus.io) é atualizado, os arquivos a serem traduzidos são importados automaticamente para este repositório usando o fluxo de trabalho GitHub Actions e um arquivo .po será criado. O arquivo .po contém traduções existentes armazenadas na memória de tradução e usar [quarkus-adoc-po-translator](https://github.com/doc-l10n-kit/quarkus-adoc-po-translator) irá inserir o texto traduzido automaticamente pela API DeepL, então use-o como uma tradução aproximada.

No entanto, por se tratar de uma tradução automática, há muitas partes erradas e está marcada como "confirmação necessária" (fuzzy), e a tradução não será refletida a menos que a marca "fuzzy" seja removida...
Revise e corrija a tradução e remova a marca "difusa".

### Arquivo traduzido

No futuro gostaríamos de traduzir todos os arquivos .po em [diretório l10n](l10n), mas antes de tudo, traduzir o conteúdo principal "guias" [diretório l10n/po/pt_BR/_guides](l10n/po/pt_BR/_guides).
A seguir, traduzir o "blog" para [diretório l10n/po/pt_BR/_posts](l10n/po/pt_BR/_posts).

### Lidando com frases sem tradução

O arquivo .po pode conter frases que não precisam ser traduzidas na íntegra, como código-fonte e URLs.
Nesse caso, não há necessidade de copiar o texto original como está. Por favor, deixe a tradução em branco. O texto original será então usado como está.

### Visualizar resultados da tradução

Se você traduzir o arquivo .po e criar um pull-request, o site será construído automaticamente com GitHub Actions, e a URL onde você pode visitar temporariamente o site será enviada como comentário no pull request no GitHub em cerca de 5 minutos.
Você pode conferir a prévia do resultado da tradução nesse site temporário, então use-o.

### Suporte/tradução de atualização de modelo HTML

O conteúdo do quarkus.io é escrito em asciidoctor (.adoc), mas parte do texto está incluída no modelo Jekyll HTML.
O texto escrito no modelo Jekyll HTML não pode ser interpretado em po4a, então coloque-o no [diretório l10n/override](l10n/override).
Coloque uma cópia dos arquivos que o po4a não consegue manipular, traduza esse arquivo manualmente e use-os na construção do site Jekyll.
A localização é obtida substituindo o arquivo original.
Se o arquivo original for atualizado upstream, o arquivo copiado no [diretório l10n/override](l10n/override) também precisará ser atualizado.
Observe que neste momento não há função para detectar e notificar a atualização do arquivo original no upstream.
