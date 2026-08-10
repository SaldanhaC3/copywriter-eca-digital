# Copywriter Skill — ECA Digital

Skill de copywriting especialista, treinada em obras clássicas de copywriting (Claude Hopkins, David Ogilvy, Robert Cialdini, Joseph Sugarman, Andy Maslen, Cashvertising, Great Leads, Ray Edwards, Russell Brunson, Gustavo Ferreira, Ícaro de Carvalho, Dan Ariely, John Caples, Robert W. Bly) e em conformidade com a **Lei nº 15.211/2025 — Estatuto Digital da Criança e do Adolescente (ECA Digital)**.

A skill escreve copy (anúncios, landing pages, e-mails, posts, headlines, CTAs etc.) usando **apenas** o conhecimento contido nos arquivos de `references/` — não pesquisa na internet e não usa conhecimento externo. Antes de escrever, ela sempre pergunta se há limite de caracteres. Quando o público pode incluir adolescentes ou crianças, ela aplica automaticamente as diretrizes de conformidade com o ECA Digital.

## Por que os livros não estão neste repositório

O conhecimento foi **destilado** em resumos originais e paráfrases nos arquivos de `references/` — os livros-fonte são obras protegidas por direitos autorais e não podem ser redistribuídos. Apenas o texto da Lei 15.211/2025 (`references/lei-15211-2025-integra.md`), que é domínio público, está incluído na íntegra.

## Estrutura

```
copywriter-skill/
├── SKILL.md                     # skill no formato Anthropic (Claude Code / Claude.ai / plugins)
├── SYSTEM_PROMPT.md             # versão para colar em qualquer outra IA (ChatGPT, Gemini, etc.)
├── memoria-copy.template.md     # base do memoria-copy.md: fatos verificados, voz da marca, testes
└── references/
    ├── 01-fundamentos.md
    ├── 02-headlines-e-leads.md
    ├── 03-estruturas-e-formulas.md
    ├── 04-psicologia-e-persuasao.md
    ├── 05-funis-e-mercado-br.md
    ├── 06-eca-digital-diretrizes.md
    ├── 07-bly-copywriters-handbook.md
    ├── 08-caples-tested-advertising.md
    ├── 09-revisao-gramatical-ptbr.md
    ├── 10-conselho-editorial.md
    ├── 11-limites-e-contagem.md
    └── lei-15211-2025-integra.md
```

## Como instalar

### Claude Code

Clone (ou copie) esta pasta para dentro do diretório de skills do seu usuário:

```bash
git clone <url-do-repositorio> ~/.claude/skills/copywriter-eca-digital
```

O Claude Code detecta o `SKILL.md` automaticamente e a skill fica disponível via `/copywriter-eca-digital` ou é sugerida quando o pedido combina com a descrição.

### Claude.ai (Projetos)

1. Crie um novo Projeto.
2. Em "Instruções do projeto", cole o conteúdo de `SYSTEM_PROMPT.md`.
3. Faça upload de todos os arquivos da pasta `references/` como conhecimento do projeto.

### ChatGPT, Gemini ou outra IA

1. Copie o conteúdo de `SYSTEM_PROMPT.md` para o campo de instruções personalizadas / prompt de sistema (ou cole no início da conversa, se a ferramenta não tiver esse campo).
2. Anexe os arquivos de `references/` (se a ferramenta suportar upload de arquivos/conhecimento) ou cole o conteúdo deles na conversa antes de pedir a copy.

## Como usar

Basta pedir a copy normalmente (ex: "escreva um anúncio para Instagram sobre X"). A skill vai:

1. Resolver o limite de caracteres — perguntando quando o canal não determina o limite, ou declarando o default quando determina (headline de RSA são 30 caracteres, não uma preferência sua).
2. Verificar se o público pode incluir menores de 18 anos, **declarar esse julgamento em uma linha na entrega** — inclusive quando a resposta é não — e, se for sim, aplicar as diretrizes do ECA Digital.
3. Escrever um rascunho usando os frameworks das referências.
4. **Submeter o rascunho ao conselho editorial** — um painel de autores (Ogilvy, Caples, Cialdini, Ícaro de Carvalho etc.) que critica a peça, discorda entre si e fecha num veredito que muda a copy ou justifica por que ela fica como está.
5. **Revisar o português brasileiro** — corrigindo erros de concordância, regência e crase, mas preservando a oralidade que faz a copy funcionar (nada de engessar o texto na norma culta formal).
6. Entregar a copy final com contagem de caracteres e justificativa das escolhas.

### O conselho editorial

Antes de entregar, a copy passa por um "mini ambiente de teste": 2 a 5 autores da base são convocados conforme a peça, cada um levanta uma objeção concreta apontando trecho, e pelo menos dois precisam **discordar entre si** — o atrito é o ponto. As discordâncias são reais e documentadas (Hopkins × Ogilvy sobre resposta vs. marca, Ogilvy × Ícaro sobre fórmula vs. voz autêntica, Whitman × Cialdini sobre gatilho vs. ética, entre outras).

Quando as vozes não convergem, há uma hierarquia de desempate: conformidade legal (ECA) → honestidade → compreensão → objetivo da peça → adequação de público/canal → preferência estilística. E o conselho nunca inventa fato para "melhorar" a copy: se uma objeção só se resolve com um dado real que você não forneceu, ele pede o dado ou deixa placeholder.

Se você não quiser o debate numa solicitação específica, peça **"modo rápido"** — o conselho é dispensado, mas a revisão gramatical e a linha de acesso provável continuam acontecendo sempre.

### Memória entre sessões

A skill mantém um `memoria-copy.md` (criado a partir de `memoria-copy.template.md`) com produto e avatar, **fatos verificados com origem e data**, voz da marca e resultados de teste. Existe por um motivo prático: como a skill nunca inventa número, depoimento, prazo ou credencial, ela precisa pedir esses fatos a você — e sem memória ela pede os mesmos fatos do mesmo produto em toda sessão. Cada fato é marcado `[FORNECIDO]` (você afirmou; pode ir para a copy) ou `[PRESUMIDO]` (ela inferiu; continua como placeholder). Fato perecível — preço, vagas, prazo de turma — é reconfirmado antes de voltar para a copy, porque escassez que era real na sessão passada é escassez falsa nesta.

### Headlines saem em variantes

Headline, subject line e CTA são entregues em **3 variantes**, cada uma rotulada com uma das 3 classes de apelo de Caples (interesse próprio, novidade ou curiosidade), o que aposta e a recomendação. A skill tem Caples no painel perguntando "você acha ou você testou?" — entregar uma versão única removia justamente a possibilidade de responder.

## Aviso legal

Esta skill oferece orientação de **boas práticas de escrita** alinhadas ao espírito da Lei 15.211/2025, mas não substitui aconselhamento jurídico. Para decisões de compliance, consulte um advogado.

## Licença

O conteúdo original deste repositório (destilações, diretrizes e estrutura da skill) está sob licença MIT — ver [LICENSE](LICENSE). O texto da Lei 15.211/2025 é de domínio público. Nenhum conteúdo dos livros-fonte está incluído neste repositório.
