# NimbusOS

Um sistema operacional pra negócios dentro do Claude Code: memória própria, identidade visual
aplicada em tudo que é gerado, e um conjunto de skills pra marketing, SEO, ads, copy, segurança e
operação do dia a dia — com você no comando.

## Primeiro uso

Abra o Claude Code na pasta do NimbusOS e rode `/instalar`. A entrevista de configuração monta a
memória do negócio e a identidade visual. Depois disso, é só usar.

## Skills

**Núcleo**
`/instalar` configura o sistema na primeira vez · `/abrir` carrega o contexto no início de uma
sessão · `/salvar` versiona o trabalho no Git · `/atualizar` reconcilia a memória com o estado
real do projeto · `/novo-projeto` isola um cliente ou iniciativa em pasta própria ·
`/mapear-rotinas` transforma tarefas repetidas em skills novas.

**Conteúdo e SEO**
`/carrossel` gera carrossel/post visual (HTML → PNG via Playwright) com a identidade da marca ·
`/publicar-tema` entrega blog + carrossel + legendas amarrados a partir de um tema · `/seo` roda
pesquisa de demanda, concorrência, GMB, on-page, estratégia de conteúdo, monitoramento e GEO ·
`/responder-avaliacoes` escreve respostas humanas pra reviews · `/aprovar-post` publica o blog e
deixa o carrossel e as legendas prontos pra postar (postagem automática nas redes é opcional).

**Anúncios pagos**
`/anuncio-google` monta campanha completa em CSVs pra importar no Google Ads Editor ·
`/relatorio-ads` lê exports de Google e Meta Ads e devolve relatório semanal com alertas.

**Copy e segurança**
`/copy` escreve copy de venda e institucional com diagnóstico de consciência do público antes de
gerar texto · `/seguranca-site` audita segurança de forma não-intrusiva, de fora (SSL, headers,
exposições comuns, CMS desatualizado, autenticação de e-mail) · `/seguranca-codigo` revisa
segurança dentro do próprio código/arquitetura de uma aplicação (auth, segredos, banco de dados,
dependências, apps desktop, OWASP Top 10).

**Produção**
`/analisar-dados` lê CSV/XLSX/PDF e devolve resumo executivo · `/email-profissional` rascunha
e-mail a partir de contexto livre · `/frontend-design` cria e revisa interfaces web com
hierarquia, espaçamento, cor e tipografia tratados como parte do código.

## Como pensa

`_memoria/` é o que o sistema sabe sobre o negócio — quem é, como fala, o que importa agora.
`identidade/` é como a marca aparece em tudo que é gerado. `clientes/<nome>/` (criado pelo
`/novo-projeto`) isola cada cliente com sua própria memória e identidade, sem misturar com o
negócio principal nem com outro cliente. `marketing/`, `saidas/` e `scripts/` guardam o que o
sistema produz. `dados/` é zona de entrada — solte ali um arquivo pra `/analisar-dados` ou
`/relatorio-ads` lerem uma vez; nada além do `README.md` dessa pasta é versionado.

`templates/` guarda material de apoio: `perfis/` tem um molde de estrutura de pastas por tipo de
negócio (autônomo, freelancer, agência, empresa), usado pelo `/instalar`; `identidade/exemplos/`
mostra o nível de detalhe esperado numa identidade preenchida; `ferramentas/catalogo.md` lista
APIs/CLIs/conectores MCP úteis; `skills/catalogo.md` lista skills prontas (nativas do Claude Code
e de terceiros) que complementam as do NimbusOS — os dois últimos são consultados pelo
`/mapear-rotinas` antes de propor skill nova.

Cada skill vive em `.claude/skills/<nome>/SKILL.md` — pra ajustar o comportamento de qualquer
uma, é só editar o arquivo direto.

## Licença

Software proprietário. O acesso é individual e não pode ser revendido nem redistribuído — veja
`LICENSE.md`.
