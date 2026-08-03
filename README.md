# Copywriter Skill — ECA Digital

Skill de copywriting especialista, treinada em obras clássicas de copywriting (Claude Hopkins, David Ogilvy, Robert Cialdini, Joseph Sugarman, Andy Maslen, Cashvertising, Great Leads, Ray Edwards, Russell Brunson, Gustavo Ferreira, Ícaro de Carvalho, Dan Ariely, John Caples, Robert W. Bly) e em conformidade com a **Lei nº 15.211/2025 — Estatuto Digital da Criança e do Adolescente (ECA Digital)**.

A skill escreve copy (anúncios, landing pages, e-mails, posts, headlines, CTAs etc.) usando **apenas** o conhecimento contido nos arquivos de `references/` — não pesquisa na internet e não usa conhecimento externo. Antes de escrever, ela sempre pergunta se há limite de caracteres. Quando o público pode incluir adolescentes ou crianças, ela aplica automaticamente as diretrizes de conformidade com o ECA Digital.

## Por que os livros não estão neste repositório

O conhecimento foi **destilado** em resumos originais e paráfrases nos arquivos de `references/` — os livros-fonte são obras protegidas por direitos autorais e não podem ser redistribuídos. Apenas o texto da Lei 15.211/2025 (`references/lei-15211-2025-integra.md`), que é domínio público, está incluído na íntegra.

## Estrutura

```
copywriter-skill/
├── SKILL.md              # skill no formato Anthropic (Claude Code / Claude.ai / plugins)
├── SYSTEM_PROMPT.md       # versão para colar em qualquer outra IA (ChatGPT, Gemini, etc.)
└── references/
    ├── 01-fundamentos.md
    ├── 02-headlines-e-leads.md
    ├── 03-estruturas-e-formulas.md
    ├── 04-psicologia-e-persuasao.md
    ├── 05-funis-e-mercado-br.md
    ├── 06-eca-digital-diretrizes.md
    ├── 07-bly-copywriters-handbook.md
    ├── 08-caples-tested-advertising.md
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

1. Perguntar se há limite de caracteres.
2. Verificar se o público pode incluir menores de 18 anos e, se sim, aplicar as diretrizes do ECA Digital.
3. Escrever a copy usando os frameworks das referências.
4. Justificar brevemente as escolhas feitas.

## Aviso legal

Esta skill oferece orientação de **boas práticas de escrita** alinhadas ao espírito da Lei 15.211/2025, mas não substitui aconselhamento jurídico. Para decisões de compliance, consulte um advogado.

## Licença

O conteúdo original deste repositório (destilações, diretrizes e estrutura da skill) está sob licença MIT — ver [LICENSE](LICENSE). O texto da Lei 15.211/2025 é de domínio público. Nenhum conteúdo dos livros-fonte está incluído neste repositório.
