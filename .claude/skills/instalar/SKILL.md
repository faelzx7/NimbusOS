---
name: instalar
description: >
  Configura o NimbusOS pela primeira vez num negócio: entrevista sobre o que a empresa faz, como
  ela fala, onde dói no dia a dia, e identidade visual. Preenche _memoria/empresa.md,
  preferencias.md, estrategia.md e identidade/identidade.md, e adapta o CLAUDE.md ao tipo de negócio.
  Use quando o usuário quiser configurar o sistema pela primeira vez, ou pedir explicitamente
  "instalar", "configurar o NimbusOS", "primeiro setup", "/instalar".
---

# /instalar — Primeira configuração

Isso é uma conversa, não um formulário. Uma pergunta de cada vez, esperando resposta real antes
de seguir. O objetivo: o sistema sair daqui sabendo quem é o negócio, como ele fala, e o que fazer
primeiro.

## Antes de começar

Ler `_memoria/empresa.md`. Se já tiver conteúdo real (não é o template em branco), perguntar:

> "Já existe uma configuração aqui. Quer refazer do zero ou só completar o que falta?"

Se for instalação limpa, seguir direto.

## Passo 1 — Tipo de negócio

Perguntar qual descrição mais se encaixa:

1. Sou eu sozinho (marca pessoal, criador, consultor solo)
2. Atendo clientes por projeto (freelancer)
3. Tenho uma equipe pequena entregando pra vários clientes (agência)
4. Empresa com áreas definidas (marketing, comercial, operação, etc.)

Isso define qual molde usar no Passo 4: `templates/perfis/solopreneur.md`,
`freelancer.md`, `agencia.md` ou `empresa.md`. Se a resposta for "agência" ou "freelancer com
clientes", `clientes/<nome>/` é onde cada cliente vive isolado — mencionar isso já aqui.

## Passo 2 — Entrevista

Uma pergunta por vez. Se a resposta vier vaga, pedir concretude uma vez; na segunda vez, registrar
o que veio e seguir (não travar a instalação numa pergunta só).

**Negócio:**
1. "Qual o nome? (do negócio, ou seu nome se for marca pessoal)"
2. "Em uma frase, o que vocês entregam — do jeito que você explicaria pra alguém de fora do ramo?"
3. "Quem realmente paga por isso? Descreve o cliente real, não uma persona genérica."
4. "Time de quantas pessoas, e quem faz o quê?"

**Voz:**
5. "Cola aqui um texto real seu — uma legenda, um email pra cliente, uma mensagem — recente e
   que soe como vocês. Isso calibra a escrita melhor que qualquer lista de adjetivos."
6. "Tem alguma palavra, expressão ou jeito de escrever que te incomoda quando você vê em outro
   lugar? (isso vira lista do que evitar)"

**Foco:**
7. "O que está travando o crescimento agora — o gargalo real, não o ideal distante?"
8. "Qual tarefa você repete toda semana e adoraria não precisar mais pensar nela?"

**Identidade visual:**
9. "Tem cores e fonte definidas? Se tiver, me passa."
10. "Tem arquivo de logo? Se tiver, salva em `identidade/logo.png` (ou `.svg`) e confirma aqui."

## Passo 3 — Preencher os arquivos

- **`_memoria/empresa.md`** — respostas 1-4, mais o perfil escolhido no Passo 1.
- **`_memoria/preferencias.md`** — "Exemplo de referência" recebe o texto colado na pergunta 5
  literalmente; "Tom de voz" é sua leitura de 2-3 frases sobre o padrão desse texto; "O que
  evitar" vem da resposta 6.
- **`_memoria/estrategia.md`** — "Gargalo principal" da resposta 7; a resposta 8 vira candidata
  a virar skill via `/mapear-rotinas` (anotar isso explicitamente no arquivo); "Prioridade das
  próximas semanas" derivada do gargalo.
- **`identidade/identidade.md`** — preencher com respostas 9-10. Se não houver nada definido,
  deixar em branco e avisar que as skills visuais usam um padrão neutro até isso ser preenchido.
  Se o usuário quiser um ponto de partida, apontar pra `templates/identidade/exemplos/` (exemplos
  ilustrativos, não pra copiar os valores, só o nível de detalhe esperado).

## Passo 4 — Adaptar o CLAUDE.md

Ler o molde correspondente ao perfil do Passo 1 em `templates/perfis/<perfil>.md`. Usar a seção
"Pastas específicas desse perfil" de lá pra montar a estrutura de pastas, e "O que descrever"
como guia do que incluir sobre o negócio. Editar a seção "Sobre este negócio" do `CLAUDE.md` raiz
com isso (não reescrever o arquivo inteiro, só essa seção) — nome, o que o negócio faz, e a
estrutura de pastas relevante. Se o perfil envolver clientes, mencionar explicitamente que
`clientes/<nome>/` isola cada um (memória e identidade próprias, nunca misturadas).

## Passo 5 — Resumo

```
✓ Perfil: [perfil escolhido]
✓ Negócio: _memoria/empresa.md
✓ Voz e tom: _memoria/preferencias.md
✓ Foco atual: _memoria/estrategia.md
✓ Identidade: identidade/identidade.md  [preenchida | em branco — completar quando definir a marca]
✓ CLAUDE.md atualizado
```

## Passo 6 — Próximos passos

> "Pronto — o sistema já sabe quem vocês são. A partir de agora, roda `/abrir` no começo de cada
> sessão pra eu carregar esse contexto antes da primeira frase.
>
> Você mencionou que repete '[resposta da pergunta 8]' toda semana — quando quiser tirar isso da
> sua rotina de vez, roda `/mapear-rotinas` que eu transformo isso numa skill própria."

Se o usuário perguntar sobre backup/versionamento, mencionar `/salvar`.

## Regras

- Nunca inventar dado que não foi dado — registrar exatamente o que veio, mesmo que incompleto.
- Nunca escrever "preenchido pelo /instalar" nos arquivos finais depois de preenchidos de verdade
  — esse aviso é só do template em branco.
- A instalação inteira deve durar poucos minutos. Se o usuário estiver com pressa numa pergunta,
  registrar o que tiver e seguir — não insistir.
- Não fazer perguntas fora das listadas sem motivo concreto.
