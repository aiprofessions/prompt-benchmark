# Transcript — skill sales-managers-pipeline-review [pt] — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:43:54+00:00
- duration_s: 76.1
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 4603e1ab240772501442ed5858580fdd19f577f1f107f3a80fd3188c0b396cd4
- skill_sha256: c79e1d4fcb5fa05f49b175ade1d1ae55f4ac0750f77e2c7355332cecfd7b6924

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: sales-managers-pipeline-review
description: "Use quando você colar datas do trimestre, data de hoje, meta restante e negócios para receber previsão ponderada, diferença para a meta, riscos e perguntas para reuniões individuais."
---

# Revisão semanal do pipeline de vendas

## O que faz

Prepara a revisão semanal da previsão de vendas e as reuniões individuais com a equipe. Calcula a previsão ponderada dos negócios com fechamento dentro do trimestre e a diferença para a meta restante, mostrando as contas. Identifica riscos pelas regras descritas abaixo e prepara uma pergunta específica por negócio sinalizado. A previsão é estimativa gerencial, não informação contábil.

## O que ela precisa

- Data de hoje, fim do trimestre e início do trimestre, se disponível; informe se o período é civil ou próprio da empresa.
- Meta restante, no formato monetário fornecido pelo usuário.
- Lista de negócios com identificador anonimizado, valor, estágio, probabilidade declarada para o estágio e data prevista de fechamento.
- Por negócio: situação de assinatura, data da última atividade, próximo passo registrado e responsável.
- Situação do defensor interno ou patrocinador do negócio: permanece, saiu ou não informado.
- Critério da equipe para compatibilidade entre estágio e prazo de fechamento, se houver.
- Somente os dados necessários do CRM, sem nomes completos, telefones, e-mails ou documentos pessoais desnecessários.

Marque o que faltar como [NÃO INFORMADO] e liste as confirmações no final, sem interromper a entrega. Premissas podem tratar da interpretação do período, nunca preencher dados de negócios.

## Procedimento

1. Entregue sempre a saída completa na primeira resposta; nunca pare para perguntar nem espere confirmação antes de redigir; nunca retenha uma seção ou um cálculo possível. Se faltar informação ou houver ambiguidade, declare uma premissa razoável e claramente marcada como “Premissa: …” ou escreva [NÃO INFORMADO]. Reúna todas as perguntas de esclarecimento na última seção, “Dados faltantes”; mantenha as perguntas de coaching na seção própria.
2. Copie exatamente cada número, data, horário e quantidade da entrada, preservando a grafia dos campos preenchidos e o formato monetário. Identifique valores derivados e mostre suas contas; não corrija silenciosamente entradas contraditórias.
3. Não invente valores, probabilidades, contatos, estágios, assinaturas, atividades, datas ou próximos passos. Diferencie ausência explícita (“sem próximo passo”) de campo não fornecido ([NÃO INFORMADO]).
4. Delimite o trimestre com início e fim inclusivos. Se houver apenas o fim de um trimestre civil reconhecível, declare “Premissa: trimestre civil” e explicite o início correspondente. Se o período próprio da empresa estiver indefinido, marque o início como [NÃO INFORMADO]; não confirme a elegibilidade sem os limites.
5. Examine todos os negócios. Inclua no cálculo somente os que tenham fechamento dentro do período e valor e probabilidade utilizáveis. Liste separadamente cada excluído e o motivo: antes do início, após o fim ou dado necessário ausente/inválido. Não exclua apenas por risco ou data já vencida.
6. Use somente a probabilidade declarada para o estágio de cada negócio; não derive probabilidades do nome do estágio. Valor ausente, probabilidade fora de 0% a 100% ou informações contraditórias impedem o cálculo daquele negócio e geram item em “Dados faltantes”.
7. Para cada incluído, mostre valor × probabilidade = valor ponderado. Some os produtos mostrando a soma. Com apenas uma parcela, identifique-a como total; se todos forem comprovadamente externos ao período, informe total zero e o motivo.
8. Se faltarem dados que possam alterar o total, identifique a soma calculável como “subtotal parcial”, não como previsão completa. Se nenhum produto puder ser calculado por falta de dados, escreva [NÃO INFORMADO], nunca zero; ainda assim entregue todas as seções.
9. Calcule a diferença para a meta: meta restante − previsão ponderada = diferença. Resultado negativo significa excedente estimado. Com subtotal parcial, rotule a diferença também como parcial; sem meta ou base calculável, apresente a fórmula e [NÃO INFORMADO].
10. Avalie as quatro regras abaixo em todos os negócios, inclusive excluídos. Para cada alerta confirmado, registre identificador, regra e fato que a acionou. Se um dado impedir a avaliação, registre “não avaliável” e liste o dado no final; não transforme desconhecimento em fato.
    - R1 — Fechamento vencido: data prevista anterior à data de hoje e situação explicitamente não assinada. Sem situação de assinatura, não confirme R1.
    - R2 — Falta de acompanhamento: hoje − data da última atividade > 21 dias corridos, ou ausência explícita de próximo passo. Mostre a subtração das datas e o total de dias; exatamente 21 dias não aciona esse critério. Campo de próximo passo não fornecido exige confirmação, não prova de ausência.
    - R3 — Saída do patrocinador: a entrada informa que o defensor interno ou patrocinador saiu da empresa ou deixou o papel no negócio.
    - R4 — Estágio incompatível com o fechamento: aplique o critério de estágio e prazo fornecido pela equipe e mostre a comparação, com a conta do intervalo de datas. Sem critério, registre “R4 não avaliável — critério não informado”; não invente prazos nem equivalências entre estágios.
11. Produza exatamente uma pergunta de coaching por negócio com alerta confirmado, mesmo que haja várias regras acionadas. Relacione-a a um fato daquele negócio; não apresente uma ação sugerida como próximo passo já registrado.
12. A saída não cita lei, artigo, orientação de órgão, jurisprudência nem fonte, salvo se estiverem no que o usuário colou e forem fontes autorizadas em “Limites”. Menção obrigatória que deva constar do documento é conteúdo, não citação. A linha de limites da saída diz somente: “O profissional responsável confere as regras aplicáveis.”
13. Inclua no resumo o lembrete de minimizar e anonimizar dados pessoais e usar apenas ferramenta aprovada pela empresa ou escritório. Privacidade é lembrete, não pré-condição: nunca recuse nem pause a revisão por esse motivo; evite reproduzir dados pessoais desnecessários.
14. Confira contas, elegibilidade, motivos de exclusão e correspondência entre alertas e perguntas. Termine com “Dados faltantes”, reunindo ausências, contradições, premissas e perguntas de confirmação; escreva “Nenhum” se não houver pendências. Não coloque nada depois dessa seção.

## Formato de saída

Use as seções abaixo nesta ordem. Mantenha todos os negócios na tabela, inclusive os excluídos; registre “Nenhum” onde não houver alertas ou exclusões.

```markdown
## Resumo do forecast
- Período: [início] a [fim] | Hoje: [data] | Meta restante: [valor]
- Previsão ponderada [completa/parcial]: [produtos somados = total, ou impedimento]
- Diferença para a meta [completa/parcial]: [meta − previsão = diferença, ou impedimento]
- Excluídos do cálculo: [identificador — motivo, ou Nenhum]
- A previsão é estimativa gerencial, não informação contábil.
- Privacidade: cole só o necessário, anonimize dados pessoais e use ferramenta aprovada pela empresa ou escritório.
- O profissional responsável confere as regras aplicáveis.

## Tabela de negócios
| Negócio | Responsável | Valor | Estágio | Probabilidade | Fechamento | Assinatura | Última atividade | Próximo passo | Patrocinador | Elegibilidade/motivo | Ponderação |
|---|---|---|---|---|---|---|---|---|---|---|---|
| [identificador] | [dado] | [dado] | [dado] | [dado] | [dado] | [dado] | [dado] | [dado] | [dado] | [situação] | [valor × probabilidade = resultado, ou impedimento] |

## Alertas de risco
- [Negócio — regra — fato e conta que a acionaram; avaliações impedidas identificadas separadamente]

## Perguntas de coaching
- [Negócio — uma pergunta específica, ou Nenhuma]

## Dados faltantes
- [Negócio/campo — ausência ou contradição, ou Nenhum]
- Premissa: [somente se adotada]
- A confirmar: [perguntas de esclarecimento pendentes]
```

## Limites

- Nunca completar lacunas com dados presumidos de negócios nem alterar probabilidades para ajustar a previsão à meta.
- Nunca apresentar a previsão como informação contábil, receita reconhecida ou garantia de fechamento.
- No Brasil, dados de contatos do CRM são dados pessoais (LGPD): cole só o necessário, retire identificadores desnecessários ou use códigos e trabalhe apenas em ferramentas aprovadas pela empresa ou escritório.
- Esse cuidado deve aparecer como lembrete, sem bloquear a entrega; não reproduza contatos pessoais desnecessários na revisão.
- O gerente comercial responsável deve conferir no CRM valores, probabilidades, datas, assinatura, atividades, próximos passos e situação dos patrocinadores.
- O responsável deve validar o período, a meta restante, o critério de compatibilidade entre estágio e prazo, as contas, as exclusões e todas as pendências antes de usar a revisão.
- Se o acompanhamento usar ligações de telemarketing ativo, a Anatel exige o prefixo 0303; o responsável deve verificar o atendimento dessa exigência antes de orientar as ligações.
- As fontes abaixo são leitura para o profissional, não citações automáticas na saída:
  - LGPD — Lei 13.709/2018 (Planalto) — https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm (consultado em 2026-10-21)
  - Anatel — Telemarketing ativo, prefixo 0303 — https://www.gov.br/anatel/pt-br/regulado/numeracao/telemarketing-ativo-prefixo-0303 (consultado em 2026-10-21)
- Antes de usar a revisão, veja references/checklist.md.

## Exemplo

Entrada fictícia, com identificadores inventados:

```text
Trimestre: 01/10/2026 a 31/12/2026 | Hoje: 05/11/2026 | Meta restante: R$ 30.000,00
Negócio Exemplo — responsável Amostra — R$ 10.000,00 — Proposta — 40% — fechamento 30/10/2026 — não assinado
Última atividade: 04/11/2026 — próximo passo: sem próximo passo — patrocinador: permanece — critério de estágio/prazo: não informado
```

Saída abreviada:

```markdown
## Resumo do forecast
Período: 01/10/2026 a 31/12/2026; hoje: 05/11/2026; previsão: R$ 10.000,00 × 40% = R$ 4.000,00 (parcela única); diferença: R$ 30.000,00 − R$ 4.000,00 = R$ 26.000,00; excluídos: Nenhum.
Estimativa gerencial, não informação contábil. Privacidade: cole só o necessário, anonimize dados pessoais e use ferramenta aprovada pela empresa ou escritório.
O profissional responsável confere as regras aplicáveis.
## Tabela de negócios
| Negócio | Responsável | Valor | Estágio/probabilidade | Fechamento/assinatura | Atividade/próximo passo | Patrocinador | Cálculo |
|---|---|---|---|---|---|---|---|
| Exemplo | Amostra | R$ 10.000,00 | Proposta / 40% | 30/10/2026 / não assinado | 04/11/2026 / sem próximo passo | permanece | Dentro do trimestre: R$ 10.000,00 × 40% = R$ 4.000,00 |
## Alertas de risco
Exemplo — R1: 30/10/2026 anterior a 05/11/2026, não assinado; R2: sem próximo passo; atividade: 05/11/2026 − 04/11/2026 = 1 dia, não supera 21 dias; R3 não acionada; R4 não avaliável.
## Perguntas de coaching
Exemplo — O que impediu a assinatura prevista para 30/10/2026?
## Dados faltantes
Critério de estágio/prazo: [NÃO INFORMADO]. A confirmar: qual critério da equipe permite avaliar a compatibilidade entre Proposta e a data de fechamento?
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Prepare a minha revisão semanal do pipeline.
Brasil, valores em R$. O trimestre termina em 31/12/2026. Hoje: 19/10/2026. Meta restante do trimestre: R$ 1.500.000.
1) Exemplo Alimentos — R$ 700.000 — Negociação (70%) — fechamento 10/12 — última atividade 15/10.
2) Amostra Saúde — R$ 400.000 — Proposta (40%) — fechamento 20/11 — última atividade 01/09 — o diretor que patrocinava o projeto saiu da empresa.
3) Teste Logística — R$ 300.000 — Compromisso (90%) — fechamento 05/10 — última atividade 04/10 — sem assinatura.
4) Exemplo Varejo — R$ 500.000 — Descoberta (20%) — fechamento 18/12 — última atividade 16/10.
5) Amostra Agro — R$ 650.000 — Qualificação (10%) — fechamento 15/02/2027 — última atividade 17/10.
````

## Output (verbatim stdout, session metadata stripped)

REVISÃO SEMANAL DO PIPELINE — Q4/2026

================================================
RESUMO DO FORECAST
================================================
Período: 01/10/2026 a 31/12/2026 | Hoje: 19/10/2026 | Meta restante: R$ 1.500.000,00
Premissa: trimestre civil (fim informado 31/12/2026); início inferido 01/10/2026.
Premissa: datas sem ano explícito (10/12, 15/10, 20/11, 01/09, 05/10, 04/10, 18/12, 16/10, 17/10) referem-se a 2026.

Previsão ponderada (completa):
  Exemplo Alimentos: R$ 700.000,00 × 70% = R$ 490.000,00
  Amostra Saúde: R$ 400.000,00 × 40% = R$ 160.000,00
  Teste Logística: R$ 300.000,00 × 90% = R$ 270.000,00
  Exemplo Varejo: R$ 500.000,00 × 20% = R$ 100.000,00
  Soma = 490.000 + 160.000 + 270.000 + 100.000 = R$ 1.020.000,00

Diferença para a meta (completa): R$ 1.500.000,00 − R$ 1.020.000,00 = R$ 480.000,00 (ainda faltam R$ 480.000,00 para a meta)

Excluídos do cálculo:
  Amostra Agro — fechamento 15/02/2027 é posterior ao fim do trimestre (31/12/2026)

A previsão é estimativa gerencial, não informação contábil.
Privacidade: cole só o necessário, anonimize dados pessoais e use ferramenta aprovada pela empresa ou escritório.
O profissional responsável confere as regras aplicáveis.

================================================
TABELA DE NEGÓCIOS
================================================

1) Exemplo Alimentos
   Responsável: [NÃO INFORMADO]
   Valor: R$ 700.000,00 | Estágio: Negociação | Probabilidade: 70%
   Fechamento: 10/12/2026 | Assinatura: [NÃO INFORMADO]
   Última atividade: 15/10/2026 | Próximo passo: [NÃO INFORMADO]
   Patrocinador: [NÃO INFORMADO]
   Elegibilidade: dentro do trimestre (01/10–31/12/2026)
   Ponderação: 700.000 × 70% = 490.000

2) Amostra Saúde
   Responsável: [NÃO INFORMADO]
   Valor: R$ 400.000,00 | Estágio: Proposta | Probabilidade: 40%
   Fechamento: 20/11/2026 | Assinatura: [NÃO INFORMADO]
   Última atividade: 01/09/2026 | Próximo passo: [NÃO INFORMADO]
   Patrocinador: saiu da empresa
   Elegibilidade: dentro do trimestre (01/10–31/12/2026)
   Ponderação: 400.000 × 40% = 160.000

3) Teste Logística
   Responsável: [NÃO INFORMADO]
   Valor: R$ 300.000,00 | Estágio: Compromisso | Probabilidade: 90%
   Fechamento: 05/10/2026 | Assinatura: sem assinatura (não assinado)
   Última atividade: 04/10/2026 | Próximo passo: [NÃO INFORMADO]
   Patrocinador: [NÃO INFORMADO]
   Elegibilidade: dentro do trimestre (01/10–31/12/2026)
   Ponderação: 300.000 × 90% = 270.000

4) Exemplo Varejo
   Responsável: [NÃO INFORMADO]
   Valor: R$ 500.000,00 | Estágio: Descoberta | Probabilidade: 20%
   Fechamento: 18/12/2026 | Assinatura: [NÃO INFORMADO]
   Última atividade: 16/10/2026 | Próximo passo: [NÃO INFORMADO]
   Patrocinador: [NÃO INFORMADO]
   Elegibilidade: dentro do trimestre (01/10–31/12/2026)
   Ponderação: 500.000 × 20% = 100.000

5) Amostra Agro
   Responsável: [NÃO INFORMADO]
   Valor: R$ 650.000,00 | Estágio: Qualificação | Probabilidade: 10%
   Fechamento: 15/02/2027 | Assinatura: [NÃO INFORMADO]
   Última atividade: 17/10/2026 | Próximo passo: [NÃO INFORMADO]
   Patrocinador: [NÃO INFORMADO]
   Elegibilidade: EXCLUÍDO — fechamento após o fim do trimestre (31/12/2026)
   Ponderação: não aplicável (excluído)

================================================
ALERTAS DE RISCO
================================================

Exemplo Alimentos:
  R1 — não acionada: fechamento 10/12/2026 é posterior a hoje (19/10/2026), não vencido.
  R2 — não acionada pela atividade: 19/10/2026 − 15/10/2026 = 4 dias (≤21). Próximo passo não avaliável (campo não informado, não é prova de ausência).
  R3 — não avaliável: patrocinador não informado.
  R4 — não avaliável: critério de estágio/prazo não informado.

Amostra Saúde:
  R1 — não acionada: fechamento 20/11/2026 é posterior a hoje, não vencido (e assinatura não informada).
  R2 — CONFIRMADA: 19/10/2026 − 01/09/2026 = 48 dias (>21).
  R3 — CONFIRMADA: patrocinador saiu da empresa (informado na entrada).
  R4 — não avaliável: critério de estágio/prazo não informado.

Teste Logística:
  R1 — CONFIRMADA: fechamento 05/10/2026 anterior a hoje (19/10/2026) e situação explicitamente "sem assinatura".
  R2 — não acionada pela atividade: 19/10/2026 − 04/10/2026 = 15 dias (≤21). Próximo passo não avaliável (campo não informado).
  R3 — não avaliável: patrocinador não informado.
  R4 — não avaliável: critério de estágio/prazo não informado.

Exemplo Varejo:
  R1 — não acionada: fechamento 18/12/2026 é posterior a hoje, não vencido.
  R2 — não acionada pela atividade: 19/10/2026 − 16/10/2026 = 3 dias (≤21). Próximo passo não avaliável (campo não informado).
  R3 — não avaliável: patrocinador não informado.
  R4 — não avaliável: critério de estágio/prazo não informado.

Amostra Agro (excluído do cálculo, mas avaliado):
  R1 — não acionada: fechamento 15/02/2027 é posterior a hoje, não vencido.
  R2 — não acionada pela atividade: 19/10/2026 − 17/10/2026 = 2 dias (≤21). Próximo passo não avaliável (campo não informado).
  R3 — não avaliável: patrocinador não informado.
  R4 — não avaliável: critério de estágio/prazo não informado.

================================================
PERGUNTAS DE COACHING
================================================

Amostra Saúde — Com a saída do diretor patrocinador e 48 dias sem atividade registrada, quem está assumindo o relacionamento com a conta e qual é o novo plano de engajamento?

Teste Logística — O fechamento estava previsto para 05/10/2026 e o negócio continua sem assinatura; o que especificamente travou a assinatura e qual é a nova data realista?

Exemplo Alimentos, Exemplo Varejo, Amostra Agro — Nenhuma (sem alerta confirmado nos dados informados).

================================================
DADOS FALTANTES
================================================
- Responsável: [NÃO INFORMADO] para todos os 5 negócios.
- Assinatura: [NÃO INFORMADO] para Exemplo Alimentos, Amostra Saúde, Exemplo Varejo e Amostra Agro (somente Teste Logística foi informado explicitamente como "sem assinatura").
- Próximo passo: [NÃO INFORMADO] para todos os 5 negócios — não pode ser tratado como ausência confirmada (R2), apenas como pendência de confirmação.
- Patrocinador: [NÃO INFORMADO] para Exemplo Alimentos, Teste Logística, Exemplo Varejo e Amostra Agro (somente Amostra Saúde foi informado: saiu).
- Critério de estágio/prazo (R4): [NÃO INFORMADO] — R4 não avaliável para todos os 5 negócios.
- Início do trimestre: não informado explicitamente; Premissa: trimestre civil, início 01/10/2026.
- Ano das datas sem ano explícito: Premissa: 2026 (exceto Amostra Agro, cujo fechamento 15/02/2027 foi informado com ano explícito).

A confirmar:
- Qual é o critério da equipe para compatibilidade entre estágio e prazo de fechamento (R4)?
- Qual é o responsável por cada um dos 5 negócios?
- Qual é a situação de assinatura dos negócios Exemplo Alimentos, Amostra Saúde, Exemplo Varejo e Amostra Agro?
- Há de fato próximo passo registrado para cada um dos 5 negócios, ou está ausente?
- Qual é a situação do patrocinador nos negócios Exemplo Alimentos, Teste Logística, Exemplo Varejo e Amostra Agro?

