# Limites e contagem de caracteres

> Duas coisas diferentes vivem aqui. **Contagem** é o que conta como caractere — é técnico, é estável e é onde a copy erra sem ninguém perceber. **Limite** é quanto o canal aceita — muda com a plataforma, e por isso entra aqui como default a confirmar, nunca como fonte de verdade.

---

## 1. O que conta como caractere

A pergunta obrigatória da skill é "qual o limite", mas a resposta só é útil se as duas pontas contarem do mesmo jeito. Regras:

- **Espaço conta.** Sempre. "Limite de 30 caracteres" inclui os espaços entre as palavras, em toda plataforma relevante.
- **Quebra de linha conta**, e às vezes conta 2 (quando o sistema grava `CRLF`). Em peça com limite apertado, quebra de linha é caractere gasto.
- **Acento conta 1** em contagem normal — `ção` são três caracteres. A exceção é SMS, no item 3.
- **Emoji quase nunca conta 1.** A maioria dos contadores de plataforma conta em unidades UTF-16, e o emoji comum ocupa **2**. Emoji com tom de pele, bandeira ou família (sequências com ZWJ) ocupa de 4 a 11. Se a peça tem limite duro e emoji, conte o emoji separado e declare: `142 caracteres (2 emoji contados como 2 cada)`.
- **Reticências.** `...` são 3 caracteres; `…` é 1. Em limite apertado, é um caractere de graça.
- **Conte o texto final entregue**, depois da revisão PT-BR do passo 5 — não o rascunho. Toda troca de palavra na revisão muda a conta, e é por isso que o fluxo manda recontar ali.

**Declare a contagem sempre no mesmo formato:** `→ N caracteres (limite: N)`. Quando estourar, não entregue e explique — reescreva até caber, ou diga explicitamente o que teve que sair para caber (é a regra do conselho: objeção que exige texto novo precisa dizer o que sai).

---

## 2. Limite duro versus ponto de truncamento

São coisas diferentes e confundir as duas produz decisão errada:

- **Limite duro** — a plataforma **recusa** o texto acima de N. Aqui N é uma restrição de engenharia: a copy tem que caber, ponto.
- **Ponto de truncamento** — a plataforma aceita o texto todo e **corta na exibição**, com "ver mais" ou reticências. Aqui N não é limite, é o lugar onde a atenção do leitor é interrompida. A copy pode passar, mas **a promessa e o gancho têm que estar antes do corte**.

A consequência prática é oposta em cada caso. Com limite duro, você corta. Com ponto de truncamento, você **reordena**: o benefício vai para antes do corte e o desenvolvimento fica depois. Cortar uma peça que só truncaria é perder argumento de graça; deixar o gancho depois do corte é escrever para quem já clicou em "ver mais", que é uma minoria.

---

## 3. SMS e a armadilha do português

SMS não conta caracteres, conta **segmentos**, e a codificação decide o tamanho do segmento:

- Alfabeto GSM-7: **160 caracteres** por segmento
- Codificação UCS-2: **70 caracteres** por segmento

O alfabeto GSM-7 inclui `é à ç ù ò ì ä ö ñ ü å` — e **não** inclui `ã õ á í ó ú â ê ô`. Ou seja: quase toda frase em português brasileiro natural (`ação`, `você`, `só`, `português`) joga a mensagem inteira para UCS-2 e **corta o espaço pela metade**, de 160 para 70. Um único `ã` no texto faz isso com a mensagem completa.

Na prática, para SMS em PT-BR: assuma 70 caracteres por segmento, ou escreva sem os acentos fora do GSM-7 se o custo por segmento importar — e nesse caso avise o usuário, porque texto sem acento é decisão de marca, não de redação.

---

## 4. Limites por canal — default a confirmar

Esta skill não pesquisa na internet por regra de escopo, e limites de plataforma mudam sem aviso. Portanto: **use a tabela para propor um default no passo 1 e siga adiante, mas nunca a apresente ao usuário como fato verificado.** Se o limite for restrição de campanha real, peça confirmação.

| Canal | Valor de referência | Natureza |
|---|---|---|
| Google Ads — headline (RSA) | 30 | limite duro |
| Google Ads — descrição (RSA) | 90 | limite duro |
| Google Ads — caminho de exibição | 15 por campo | limite duro |
| X/Twitter — post | 280 | limite duro |
| SMS | 160 GSM-7 / 70 UCS-2 por segmento | limite técnico (ver item 3) |
| Meta — texto principal | sem limite prático; truncamento por volta de 125 | ponto de truncamento |
| Meta — título do anúncio | truncamento em torno de 40 | ponto de truncamento |
| E-mail — assunto | sem limite; corte do cliente por volta de 40–50 no celular | ponto de truncamento |
| Meta description (SEO) | corte por volta de 155–160 | ponto de truncamento |
| YouTube — título | 100 | limite duro |

Os valores marcados como ponto de truncamento variam por dispositivo, idioma e teste em curso da própria plataforma — trate-os como "onde a atenção corta", não como número exato.

---

## 5. Quando perguntar e quando propor

O passo 1 do fluxo existe porque escrever sem saber o limite desperdiça a peça inteira. Mas a pergunta não precisa custar um turno quando o canal já a responde:

- **Canal informado e com limite duro conhecido** (headline de RSA, post no X, título de YouTube): declare o limite que vai usar em meia linha e escreva no mesmo turno. `Vou usar 30 caracteres, o limite de headline de RSA — me corrija se o seu caso for outro.`
- **Canal informado, mas o limite é ponto de truncamento** (Meta, e-mail, LinkedIn): não pergunte limite, informe onde está o corte e escreva colocando o gancho antes dele.
- **Canal não informado, ou limite que só o usuário sabe** (grade de mídia, template de CRM, restrição de cliente): **pergunte.** É aqui que a pergunta obrigatória ganha o turno que custa.

Em nenhum dos três casos você inventa o limite e segue calado. Limite assumido é declarado.
