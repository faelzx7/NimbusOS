# NimbusOS

O sistema operacional do seu negócio dentro do Claude Code.

Em poucos minutos, o NimbusOS dá ao seu negócio uma memória própria, uma identidade visual que
entra em tudo que ele gera, e 19 skills prontas pra fazer conteúdo, SEO, anúncios, copy, segurança
e operação rodarem com você no volante. E se você atende clientes, cada um mora numa pasta
isolada — o contexto de um nunca vaza pro outro.

Bora decolar.

## Ligando o sistema

Dois caminhos. Escolhe o que combina com você.

**Pelo Claude (mais rápido).** Abre o Claude Code em qualquer pasta e cola:

> Clona o https://github.com/faelzx7/NimbusOS.git na pasta atual, entra nela e roda o `/instalar`.

Ele clona, entra na pasta e já dispara a entrevista de configuração. Você só responde.

**Pelo terminal (mais previsível).**

```bash
git clone https://github.com/faelzx7/NimbusOS.git
cd NimbusOS
code .
```

Na janela do VS Code que abrir: terminal integrado → `claude` → `/instalar`.

Se quiser, renomeie a pasta pro nome do seu negócio depois — a partir da instalação, ela é o seu
negócio, não um template. O `/instalar` roda uma vez só: te entrevista, monta a memória e deixa o
sistema configurado. Depois disso, é só usar.

## O sistema

**Núcleo — o jeito de operar o dia a dia.** `/abrir` carrega o contexto no começo de cada sessão ·
`/salvar` versiona seu trabalho no Git · `/atualizar` varre o projeto e mantém a memória em dia ·
`/novo-projeto` cria uma pasta isolada pra cada cliente ou iniciativa · `/mapear-rotinas` descobre
o que você repete e transforma em skill própria.

**Conteúdo e SEO — a vitrine pública.** `/carrossel` cria carrosséis 1080×1350 com a identidade da
marca, renderizados em PNG · `/publicar-tema` pega um tema e entrega artigo de blog + carrossel +
legendas, tudo amarrado · `/seo` roda o fluxo completo (demanda, concorrência, Google Meu Negócio,
on-page, conteúdo, monitoramento e presença em respostas de IA) · `/responder-avaliacoes` escreve
respostas humanas pras reviews do Google · `/aprovar-post` publica o blog e deixa carrossel e
legendas prontos pra postar.

**Anúncios pagos — onde o dinheiro entra.** `/anuncio-google` monta a campanha inteira em CSV
pronto pra importar no Google Ads Editor · `/relatorio-ads` lê os exports de Google e Meta e
devolve um relatório semanal com alertas e recomendações.

**Copy — a palavra que vende.** `/copy` escreve headline, e-mail de venda, landing page, tagline
e carta de venda, diagnosticando o nível de consciência do público antes de escrever a primeira
linha.

**Segurança — o que protege a operação.** `/seguranca-site` audita um site de fora, sem invadir
(SSL, headers, exposições comuns, autenticação de e-mail) · `/seguranca-codigo` revisa a segurança
dentro do código de uma aplicação (autenticação, segredos, banco, dependências, OWASP).

**Produção — ferramentas do dia a dia.** `/analisar-dados` lê CSV, XLSX ou PDF e devolve um resumo
executivo · `/email-profissional` rascunha um e-mail a partir de contexto solto · `/frontend-design`
cria e revisa interfaces web com padrão visual profissional.

## A tese

IA não é uma ferramenta que seu negócio abre de vez em quando. É a camada em que ele roda.

A diferença não é fazer as mesmas coisas mais rápido — é fazer o que antes exigia um time inteiro.
E o pulo do gato é a memória: sem ela, cada tarefa começa do zero e você repete o mesmo contexto
pra sempre. Com o NimbusOS, o negócio lembra de quem é, de como fala e do que já deu certo — então
cada trabalho parte de onde o último parou, em vez de recomeçar.

O sistema não te substitui. Ele vira parte do seu negócio.

## Como o NimbusOS pensa

**`_memoria/` é o cérebro.** Tudo que importa mora aqui — quem é o negócio, como ele fala, o que
está em foco. O Claude lê isso antes de cada resposta. Quanto melhor a memória, melhor o sistema.

**`identidade/` é o rosto.** Cores, fontes, logo, padrão visual. Todo carrossel, slide e peça que
o sistema gera respeita isso.

**`clientes/<nome>/` é cada cliente, isolado.** Memória e identidade próprias, sem nunca misturar
com o negócio principal nem com outro cliente. É o que faz o NimbusOS servir uma agência inteira
sem embaralhar contexto.

**`marketing/`, `saidas/` e `scripts/` são o resultado.** O sistema produz, versiona no Git, e
fica tudo seu.

---

Software proprietário. O acesso é individual e não pode ser revendido nem redistribuído — veja
[`LICENSE.md`](LICENSE.md).
