# Canal das Ofertas — GitHub Pages

Site estático baseado nos arquivos enviados. A vitrine lê **duas abas publicadas em CSV** do Google Sheets, cujas URLs já estão no `config.js`.

## Publicar no GitHub Pages

1. Entre em https://github.com e crie uma conta, se necessário.
2. Clique em **New repository** e escolha um nome, por exemplo `canal-das-ofertas`.
3. Selecione **Public** (ou outra opção compatível com sua conta e GitHub Pages) e crie o repositório.
4. Use **Add file → Upload files** e envie `index.html` e `config.js` para a **raiz** do repositório.
5. Clique em **Commit changes**.
6. Abra **Settings → Pages → Build and deployment**; selecione **Deploy from a branch**.
7. Escolha a branch `main`, a pasta `/ (root)` e clique em **Save**.
8. Aguarde a publicação e visite `https://SEU-USUARIO.github.io/canal-das-ofertas/` (substitua o usuário e o nome do repositório).
9. Verifique no celular e no computador: carregamento, categorias, imagens, pesquisa, cupons, links de afiliados e canais.

## Atualizar sem editar o código

1. Edite a **planilha Google original** que está por trás dos URLs CSV do `config.js` (não apenas o arquivo Excel baixado).
2. Na aba **Produtos**, mantenha as colunas e a ordem existentes; uma linha representa um produto. Marque `Ativo *` como `Sim` ou `Não`.
3. Na aba **Configurações**, edite os valores da coluna B sem mudar os nomes dos campos na coluna A.
4. Se ainda não estiverem publicados, no Google Sheets use **Arquivo → Compartilhar → Publicar na Web**, selecionando cada aba e o formato CSV. Copie cada URL publicada para `config.js`.
5. Atualize a página do site; a publicação e caches do Google podem provocar atraso. O código já acrescenta um parâmetro de atualização aos pedidos CSV.

**ATENÇÃO:** Publicar abas em CSV torna os dados dessas abas acessíveis a qualquer pessoa com o link. Não inclua dados confidenciais, tokens ou senhas.

## Conferências antes de divulgar

- Os links CSV existentes no `config.js` **não foram validados ao vivo** neste pacote; confirme que ambos respondem com CSV e correspondem à planilha desejada. O ID da planilha original e o ID da publicação CSV são diferentes por natureza.
- O Apps Script de cliques é **opcional** e não foi testado. O código original possui mais de um mecanismo de registro; confira se não há cliques duplicados.
- Substitua links de afiliado de demonstração e confira permissões das imagens do Google Drive.
- Confira CNPJ, e-mail, WhatsApp, redes sociais, preços e datas de validade.
- Não mude a ordem das 20 colunas na aba Produtos: o leitor atual identifica colunas pela posição.
- A vitrine não processa pagamentos: cada botão leva à plataforma de venda externa.

## Arquivos

- `index.html`: visual, leitura de CSV e interações da vitrine.
- `config.js`: URLs das abas CSV e endereço opcional do Apps Script.

## Ajustes técnicos aplicados

- Verificação do código HTTP das respostas CSV.
- Escape de texto de produtos inserido como HTML.
- Validação de URLs HTTP/HTTPS para links de afiliado e imagens principais.
- Proteção do seletor de miniaturas contra inserção de JavaScript via endereço da imagem.
- Validação do formato de cor primária.

**Limitação:** Este pacote foi revisado estaticamente, mas não teve teste completo em navegador contra os serviços externos. Faça os testes de publicação antes de divulgar.
