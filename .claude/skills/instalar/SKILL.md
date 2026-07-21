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
primeiro. 5-7 minutos, não mais que isso.

## Antes de começar

Ler `_memoria/empresa.md`. Se já tiver conteúdo real (não é o template em branco), perguntar:

> "Já existe uma configuração aqui. Quer refazer do zero ou só completar o que falta?"

Checar também o nome da pasta atual. Se for genérico — `NimbusOS`, `nimbusos`, `template`,
`meu-negocio`, `negocio`, `teste`, `test`, ou variação óbvia dessas, case-insensitive — guardar
isso pra usar na Fase 5. Se já tem nome próprio, seguir sem mencionar.

## Fase 1 — Escolha do perfil

Perguntar qual perfil mais combina com o negócio:

1. **Solopreneur / criador solo** — uma pessoa só, mistura de marca pessoal e negócio
2. **Freelancer** — atende clientes, organiza por projeto/cliente
3. **Agência / consultoria** — equipe pequena entregando pra vários clientes
4. **Empresa** — empresa estabelecida com setores (marketing, comercial, financeiro, etc.)

A resposta determina qual molde usar na Fase 3: `templates/perfis/solopreneur.md`,
`freelancer.md`, `agencia.md` ou `empresa.md`. Se for "freelancer" ou "agência/consultoria",
`clientes/<nome>/` é onde cada cliente vive isolado — mencionar isso já aqui.

## Fase 2 — Entrevista

Fazer essas perguntas em ordem, esperando a resposta de cada uma antes de seguir. Se vier resposta
vaga, repetir uma vez pedindo concretude — não insistir mais que isso, registrar o que vier.

**Sobre o negócio:**
1. "Como você chama o que você faz? (nome do negócio, ou seu nome se for marca pessoal)"
2. "O que você entrega, em uma frase do jeito que você falaria pro vizinho?"
3. "Quem te paga? (perfil de cliente real — descreve em uma ou duas frases, sem persona genérica)"
4. "Você toca sozinho ou tem equipe? Se tem, quantos e cada um fazendo o quê?"

**Sobre voz:**
5. "Me cola um exemplo da tua escrita — uma legenda do Insta, um email pra cliente, qualquer
   coisa real e recente. Assim eu calibro o jeito de escrever sem precisar adivinhar."
6. "O que te dá ranço quando alguém escreve assim? (ex: 'vamos juntos!', emoji em email formal,
   'caro cliente', jargão de guru, 'alavancar', 'sinergia')"

**Sobre foco:**
7. "Qual o gargalo do teu negócio hoje? O que tá segurando ele de crescer?"
8. "Se eu pudesse tirar UMA coisa que você repete toda semana das tuas costas, qual seria?"

**Sobre identidade visual:**
9. "Tem identidade visual definida ou tá no zero? Se tem, me passa as cores principais e a fonte
   — e se tiver os arquivos da fonte (não só o nome), salva em `identidade/fontes/` e confirma
   aqui. Sem arquivo, eu carrego a fonte via Google Fonts pelo nome."
10. "Tem logo? Se sim, joga o arquivo em `identidade/logo.png` (ou `.svg`) e me confirma."

## Fase 3 — Preenchimento dos arquivos

**`_memoria/empresa.md`** — respostas 1-4, mais o perfil escolhido na Fase 1. Formato simples:
nome, o que faz, perfil de cliente, equipe.

**`_memoria/preferencias.md`**
- "Exemplo de referência" recebe o texto colado na resposta 5, literalmente.
- "Tom de voz" é sua leitura em 2-3 frases do padrão desse texto.
- "O que evitar" vem direto da resposta 6.

**`_memoria/estrategia.md`**
- "Gargalo principal" da resposta 7.
- A resposta 8 vira candidata a virar skill via `/mapear-rotinas` — anotar isso explicitamente
  no arquivo.
- "Prioridade das próximas semanas" derivada do gargalo (o que ataca ele direto).

**`identidade/identidade.md`** — se o usuário deu cores/fonte/logo (respostas 9-10), preencher os
campos correspondentes, incluindo "Arquivos" da Tipografia se ele mandou arquivo de fonte. Se
não, deixar em branco e avisar:

> "Deixei o `identidade/identidade.md` em branco. Sempre que definir a identidade visual, edita
> lá — as skills visuais (`/carrossel`, `/frontend-design`, etc.) leem esse arquivo antes de criar
> qualquer coisa."

Se o usuário quiser um ponto de partida, apontar pra `templates/identidade/exemplos/` (exemplos
ilustrativos, não pra copiar os valores, só o nível de detalhe esperado).

**`CLAUDE.md`** — ler o molde correspondente ao perfil da Fase 1 em `templates/perfis/<perfil>.md`.
Usar "Pastas específicas desse perfil" pra montar a estrutura de pastas, e "O que descrever" como
guia do que incluir sobre o negócio. **Editar só a seção "Sobre este negócio" do `CLAUDE.md` raiz
— nunca sobrescrever o arquivo inteiro.** O resto do arquivo (Fluxo de trabalho, Aprender com
correções, Manter a memória em dia, Criação de skills) são regras universais do NimbusOS, válidas
em qualquer instalação, não específicas desse negócio. Se o perfil envolver clientes, mencionar
que `clientes/<nome>/` isola cada um (memória e identidade próprias, nunca misturadas).

## Fase 4 — Resumo

```
✓ Perfil aplicado: [perfil]
✓ Contexto do negócio: _memoria/empresa.md
✓ Tom de voz: _memoria/preferencias.md
✓ Foco atual: _memoria/estrategia.md
✓ Identidade: identidade/identidade.md  [preenchida | em branco — completar depois]
✓ CLAUDE.md adaptado pro perfil [perfil]
```

## Fase 5 — Renomear a pasta (se necessário)

Se o nome da pasta atual for genérico (detectado em "Antes de começar"), gerar um slug do nome do
negócio (resposta 1): minúsculas, sem acento, espaço vira hífen, caractere especial fora. Ex:
"Padaria do Zé" → `padaria-do-ze`.

Mostrar:

> "Última coisa: a pasta ainda tá com nome genérico ('[nome atual]'). Pra ter cara do seu
> negócio, recomendo renomear pra '[slug]'.
>
> Como fazer: fecha o VS Code, renomeia a pasta no Explorer (Windows) ou Finder (Mac) — ou no
> terminal, fora dela: `mv <nome-atual> <slug>` — e abre o VS Code de novo na pasta renomeada.
>
> Se preferir outro nome, me fala que eu ajusto a sugestão."

Se a pasta já tem nome próprio (não genérico), pular essa fase sem mencionar.

## Fase 6 — Próximos passos

> "Pronto — o sistema já sabe quem vocês são. No começo de cada sessão, roda `/abrir` que eu
> carrego tudo isso antes da primeira frase. Quando quiser fazer um carrossel, plano de SEO,
> campanha ou qualquer outra coisa, é só chamar a skill que cabe.
>
> Você mencionou que repete '[resposta da pergunta 8]' toda semana — quando quiser tirar isso das
> costas de vez, roda `/mapear-rotinas` que eu transformo isso numa skill própria."

Se o usuário perguntar sobre backup/versionamento, mencionar `/salvar`.

## Regras

- Nunca inventar dado que não foi dado — registrar exatamente o que veio, mesmo que incompleto.
- Nunca escrever "preenchido pelo /instalar" nos arquivos finais depois de preenchidos de verdade
  — esse aviso é só do template em branco.
- Nunca sobrescrever o `CLAUDE.md` inteiro — editar só a seção "Sobre este negócio", o resto é
  regra universal do sistema.
- A instalação inteira deve durar 5-7 minutos no máximo. Se o usuário estiver enrolando numa
  pergunta, registrar o que tem e seguir — não insistir.
- Não fazer perguntas fora das listadas sem motivo concreto.
