# Transcript — skill lawyers-nda-review [pt] — claude-fable-5-1 — run 3

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-21T06:49:34+00:00
- duration_s: 62.7
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: a454cea97b211db64d5e777d3ed52401aea47991eec259fb2a6807af791d6b0c
- skill_sha256: 0d2f4575271d3ab70f34df0bfd0aee6c0b61a6407e3e76b733f4a656d93dc158

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: lawyers-nda-review
description: "Use quando colar cláusulas de NDA da contraparte e a política do cliente para receber problemas, ausências, cláusulas conformes e propostas de redação."
---

# Revisão de NDA pela política do cliente

## O que faz

Compara cada cláusula do NDA da contraparte exclusivamente com a política de negociação do cliente. Aponta divergências e exigências ausentes, propõe redações e identifica cláusulas que dispensam alteração. Entrega uma minuta de trabalho para revisão do advogado responsável, não aconselhamento jurídico.

## O que ela precisa

- Cláusulas do NDA da contraparte, com títulos e numeração originais, quando disponíveis.
- Política do cliente: exigências obrigatórias, preferências, recuos autorizados e critérios de risco.
- Indicação de que o material é integral ou parcial e, se disponível, a versão da política aplicável.
- Papel do cliente: parte reveladora, receptora ou ambas; indicação de eventual tratamento de dados pessoais.
- O que faltar será marcado como [NÃO INFORMADO] e listado nas perguntas ao final, sem interromper a entrega.
- Premissas devem ser identificadas como «Premissa: …»; nunca presumir conteúdo contratual, posição da política, autorização de recuo ou conformidade.

## Procedimento

1. Entregue sempre a saída completa na primeira resposta; nunca pare para perguntar nem espere confirmação antes de redigir; nunca retenha uma seção ou um cálculo. Se faltar informação ou houver ambiguidade, declare uma premissa razoável e claramente marcada («Premissa: …») apenas sobre a organização da análise, ou escreva [NÃO INFORMADO]. Reúna todas as perguntas na última seção, «Perguntas para o advogado responsável».
2. Inclua no resumo o lembrete de anonimizar nomes e dados identificáveis e usar somente ferramenta aprovada pelo escritório. É lembrete, não pré-condição: nunca recuse nem pause por esse motivo.
3. Inventarie todas as cláusulas recebidas e todas as posições da política. Preserve os identificadores originais; se faltarem, atribua identificadores pela ordem do texto e declare essa convenção como premissa.
4. Copie exatamente cada número, data, horário, prazo, valor e quantidade da entrada ao reproduzir seu conteúdo. Não normalize nem corrija silenciosamente. Separe os dados originais dos valores expressamente propostos pela política; toda alteração fica identificada como proposta. Para números derivados, inclusive contagens apresentadas, mostre a conta.
5. Use somente a política como padrão. Não importe práticas de mercado, preferências próprias ou regras externas como exigências. Não deduza uma posição a partir do silêncio da política.
6. Compare cada cláusula com todas as posições pertinentes. Classifique-a como conforme, divergente, parcialmente conforme ou sem parâmetro suficiente. Se faltar a política inteira, preencha todas as seções, mas não conclua sobre conformidade, risco ou ausências contratuais.
7. Registre cláusulas divergentes e parcialmente conformes na tabela de problemas. Inclua cláusulas sem parâmetro suficiente como pendências, com posição, risco e proposta marcados [NÃO INFORMADO], sem tratá-las como defeitos contratuais.
8. Preencha as seis colunas da tabela: cláusula; o que a minuta diz; posição da política; divergência; risco; redação proposta. Use trecho fiel e suficiente para demonstrar a comparação.
9. Aplique primeiro os critérios de risco da política. Na falta deles, use: Alto para descumprimento de exigência expressamente obrigatória; Médio para desvio de preferência expressa; Baixo para diferença apenas formal, sem mudança de sentido. Se a classificação depender de interpretação ou prioridade não informada, registre [NÃO INFORMADO] e formule uma pergunta ao responsável.
10. Redija propostas em português, limitadas à posição expressa da política. Não acrescente obrigações, exceções ou condições sem respaldo nela. Só aplique recuo quando sua autorização e suas condições estiverem claras; caso contrário, apresente-o como alternativa sujeita à decisão do advogado.
11. Faça a conferência inversa: para cada exigência da política, localize o trecho correspondente no NDA. Registre em «Cláusulas ausentes» cada exigência não encontrada, com sua posição, risco conforme o mesmo critério e redação proposta. Se a entrada for parcial, diga «não localizada nos trechos recebidos», sem afirmar ausência no contrato integral.
12. Liste em «Cláusulas conformes» somente cláusulas que atendam a todas as posições pertinentes, indicando quais foram atendidas e «sem alteração». Não classifique como conforme uma cláusula com divergência ou ambiguidade pendente.
13. Não invente autoridades ou citações. A saída não cita lei, artigo, orientação de órgão, jurisprudência nem fonte, salvo conteúdo colado pelo usuário e permitido pelos limites abaixo. Mesmo nessa hipótese, não reproduza súmula, jurisprudência ou número de artigo. Não acrescente referências externas; quando necessário fundamento jurídico, registre [AUTHORITY TO BE LOCATED] nas perguntas finais.
14. Transforme decisões interpretativas, aceitação de recuos e escolhas de negociação em perguntas ao advogado responsável. Se houver dados pessoais, inclua pergunta sobre a adequação do tratamento e das obrigações correspondentes, sem introduzir exigências externas na comparação.
15. Declare no resumo que a entrega é minuta para revisão, não aconselhamento jurídico. Na seção «Limites» da saída, escreva somente que o profissional responsável confere as regras aplicáveis.
16. Confira a cobertura antes de entregar: cada cláusula recebida deve aparecer na tabela ou em conformes; cada posição da política deve estar vinculada à comparação, a uma ausência ou a uma pendência explícita. Confira números, contas, propostas e restrições de citação. Preencha seções vazias com «Nenhuma identificada» apenas quando houver base; caso contrário, use [NÃO INFORMADO]. Termine com as perguntas, sem texto posterior.

## Formato de saída

Use o modelo abaixo. As perguntas ficam por último, depois de «Limites».

```markdown
## Resumo
Minuta para revisão do advogado responsável; não é aconselhamento jurídico.
Lembrete: anonimize nomes e dados identificáveis e use apenas ferramenta aprovada pelo escritório.
- Escopo recebido: [integral, parcial ou NÃO INFORMADO].
- Síntese: [principais divergências e pendências, sem novas exigências].
- Premissas: [Premissa: … ou nenhuma].

## Tabela de problemas
| Cláusula | O que a minuta diz | Posição da política | Divergência | Risco | Redação proposta |
|---|---|---|---|---|---|
| [identificador] | [trecho fiel] | [posição expressa ou NÃO INFORMADO] | [diferença ou pendência] | [Alto/Médio/Baixo ou NÃO INFORMADO] | [texto ou NÃO INFORMADO] |

## Cláusulas ausentes
- [Exigência da política] — [ausente ou não localizada nos trechos recebidos]. Risco: [classificação ou NÃO INFORMADO]. Proposta: «[texto]».

## Cláusulas conformes
- [Identificador] — atende a [posições pertinentes]. Sem alteração.

## Limites
O profissional responsável confere as regras aplicáveis.

## Perguntas para o advogado responsável
- [Questões de interpretação, recuos, lacunas e premissas a confirmar].
- [Se necessário: fundamento a verificar — [AUTHORITY TO BE LOCATED]].
```

## Limites

- A análise se limita à comparação documental para atuação no Brasil; não substitui revisão jurídica nem autoriza envio ou assinatura.
- Nunca invente leis, artigos, reguladores, datas, URLs, estatísticas, súmulas, jurisprudência ou outras citações. Não reproduza súmulas, jurisprudência nem números de artigo na saída.
- As únicas referências autorizadas são as listadas abaixo, exatamente como fornecidas; são leitura do profissional, não citações a inserir automaticamente na resposta. Não reproduza outras autoridades, mesmo se aparecerem no material recebido; sinalize a necessidade de verificação sem citá-las.
- Se for necessário fundamento jurídico, use [AUTHORITY TO BE LOCATED], sem preencher o marcador por suposição.
- O advogado responsável, habilitado para atuar no Brasil, deve verificar a integridade dos documentos, a política aplicável, as interpretações, os riscos, os recuos autorizados e cada proposta antes do envio ou assinatura.
- Cabe a esse profissional verificar as regras aplicáveis, o sigilo profissional, os fundamentos pendentes e, quando houver dados pessoais, a adequação à LGPD. Essa verificação não muda o padrão exclusivo da comparação com a política.
- Privacidade: lembre de anonimizar partes e outros identificadores e de usar apenas ferramentas aprovadas pelo escritório. Evite repetir dados identificáveis na resposta; use designações neutras, sem alterar o sentido das cláusulas. Não pause nem recuse a análise por esse motivo.
- Antes de usar a saída, veja references/checklist.md.

Fontes para leitura do profissional:

- Conselho Federal da OAB — Recomendação n. 001/2024 (Diário Eletrônico da OAB, 14/11/2024) — https://deoab.oab.org.br/assets/diarios/diario-eletronico-oab-14-11-2024.pdf (14/11/2024; consultado em 2026-10-21)
- Lei 8.906/1994 — Estatuto da Advocacia e da OAB (Planalto) — https://www.planalto.gov.br/ccivil_03/leis/l8906.htm (consultado em 2026-10-21)
- LGPD — Lei 13.709/2018 (Planalto) — https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm (consultado em 2026-10-21)

## Exemplo

Entrada fictícia, sem relação com caso real:

```
Partes fictícias: Exemplo e Amostra; cliente: Amostra, parte receptora. Apenas trechos.
Cl. 2: O sigilo permanece por 10 anos após o término.
Cl. 4: A parte receptora poderá devolver ou destruir as informações.
Política: obrigatório limitar o sigilo a 3 anos após o término e permitir devolução ou destruição.
Política: obrigatório excluir do sigilo as informações que já eram públicas no recebimento.
```

Saída abreviada:

```
## Resumo
Minuta para revisão; não é aconselhamento jurídico. Escopo: trechos. Lembrete: anonimize nomes e dados identificáveis e use ferramenta aprovada pelo escritório.
## Tabela de problemas
| Cláusula | O que a minuta diz | Posição da política | Divergência | Risco | Redação proposta |
| Cl. 2 | O sigilo permanece por 10 anos após o término. | Obrigatório limitar a 3 anos após o término | Prazo excedente: 10 anos − 3 anos = 7 anos | Alto | O sigilo permanece por 3 anos após o término. |
## Cláusulas ausentes
- Exclusão obrigatória não localizada nos trechos recebidos. Risco: Alto. Proposta: «Não estão sujeitas ao sigilo as informações que já eram públicas no recebimento».
## Cláusulas conformes
- Cl. 4 — atende à exigência de permitir devolução ou destruição. Sem alteração.
## Limites
O profissional responsável confere as regras aplicáveis.
## Perguntas para o advogado responsável
- A exclusão exigida consta de outro trecho? Há tratamento de dados pessoais?
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Revise este acordo de confidencialidade com base na nossa política e me dê a tabela de problemas e a redação proposta.
Cliente: Exemplo Tecnologia Ltda. (fictícia), Brasil, parte REVELADORA (acordo unilateral). Propósito: avaliar uma integração de sistemas; a reveladora vai compartilhar uma amostra da base de clientes.
Minuta da outra parte:
Cl. 1 Informação Confidencial: toda informação técnica ou comercial, escrita, oral ou eletrônica, marcada ou não.
Cl. 3 A Receptora poderá usar a informação para qualquer finalidade relacionada aos seus negócios.
Cl. 5 Vigência: 12 meses a partir da assinatura.
Cl. 7 Lei brasileira; foro da comarca de São Paulo.
Cl. 8 A Receptora poderá manter cópias de arquivo por prazo indeterminado.
Política do cliente: cobrir informação escrita, oral ou eletrônica, marcada ou não; uso exclusivo para o Propósito; vigência de 3 anos e segredos comerciais protegidos enquanto mantiverem essa condição; lei brasileira e foro de São Paulo aceitáveis; devolução ou destruição mediante solicitação, com declaração por escrito; se houver dados pessoais, cláusula de cumprimento da LGPD; aviso imediato à Reveladora se uma autoridade requisitar a informação.
````

## Output (verbatim stdout, session metadata stripped)

Resumo
Minuta para revisão do advogado responsável; não é aconselhamento jurídico.
Lembrete: anonimize nomes e dados identificáveis e use apenas ferramenta aprovada pelo escritório. Abaixo, as partes são designadas como «Reveladora» (cliente) e «Receptora».
- Escopo recebido: [NÃO INFORMADO]. A numeração salta as Cl. 2, 4 e 6, o que indica material parcial.
- Síntese: Cl. 3 (finalidade ampla) e Cl. 8 (retenção indeterminada de cópias) contrariam frontalmente a política; Cl. 5 fica aquém do prazo (12 meses vs. 3 anos) e não protege segredos comerciais enquanto mantiverem essa condição. Não localizadas: cláusula de LGPD (condicionada à presença de dados pessoais na amostra da base de clientes) e aviso imediato de requisição por autoridade. Cl. 1 e Cl. 7 conformes.
- Premissas: Premissa: para organizar a análise, os trechos são tratados como parciais, e as exigências não localizadas são registradas como «não localizadas nos trechos recebidos». Premissa: «Propósito» na redação proposta corresponde a «avaliar uma integração de sistemas», conforme informado pelo usuário; não foi informado se a minuta já define o termo.

Tabela de problemas
| Cláusula | O que a minuta diz | Posição da política | Divergência | Risco | Redação proposta |
|---|---|---|---|---|---|
| Cl. 3 | «A Receptora poderá usar a informação para qualquer finalidade relacionada aos seus negócios.» | Uso exclusivo para o Propósito. | A minuta autoriza qualquer finalidade ligada aos negócios da Receptora; a política restringe ao Propósito. | [NÃO INFORMADO] — Alto se a posição for obrigatória; Médio se for preferência. A política não classifica suas posições. | «A Receptora utilizará a Informação Confidencial exclusivamente para o Propósito, assim entendido a avaliação de uma integração de sistemas entre as Partes, e para nenhuma outra finalidade.» |
| Cl. 5 | «Vigência: 12 meses a partir da assinatura.» | Vigência de 3 anos; segredos comerciais protegidos enquanto mantiverem essa condição. | Prazo inferior: 3 anos = 36 meses; 36 − 12 = 24 meses a menos. Falta a proteção prolongada de segredos comerciais. Classificação: parcialmente conforme. | [NÃO INFORMADO] — Alto se obrigatória; Médio se preferência. | «Vigência: 3 anos a partir da assinatura. As obrigações de sigilo relativas a informações que constituam segredo comercial permanecem em vigor enquanto tais informações mantiverem essa condição.» |
| Cl. 8 | «A Receptora poderá manter cópias de arquivo por prazo indeterminado.» | Devolução ou destruição mediante solicitação, com declaração por escrito. | A minuta permite retenção indefinida; a política exige devolução ou destruição a pedido, com declaração escrita, e não prevê exceção para cópias de arquivo. | [NÃO INFORMADO] — Alto se obrigatória; Médio se preferência. | «Mediante solicitação da Reveladora, a Receptora devolverá ou destruirá toda a Informação Confidencial, inclusive cópias, e entregará à Reveladora declaração por escrito confirmando a devolução ou a destruição.» |
| Cl. 2, 4 e 6 | Não recebidas. | [NÃO INFORMADO] | Pendência: a numeração indica cláusulas não enviadas. | [NÃO INFORMADO] | [NÃO INFORMADO] |

Cláusulas ausentes
- Cláusula de cumprimento da LGPD (condição da política: «se houver dados pessoais») — não localizada nos trechos recebidos. A amostra da base de clientes pode conter dados pessoais; a presença não foi confirmada: [NÃO INFORMADO]. Risco: [NÃO INFORMADO] — Alto se houver dados pessoais e a posição for obrigatória. Proposta: «Caso a Informação Confidencial contenha dados pessoais, a Receptora cumprirá a Lei Geral de Proteção de Dados Pessoais (LGPD) no tratamento desses dados.»
- Aviso imediato à Reveladora em caso de requisição por autoridade — não localizado nos trechos recebidos. Risco: [NÃO INFORMADO] — Alto se obrigatória; Médio se preferência. Proposta: «Se uma autoridade requisitar a Informação Confidencial, a Receptora avisará a Reveladora imediatamente.»
- Proteção de segredos comerciais enquanto mantiverem essa condição — não localizada nos trechos recebidos; tratada na Cl. 5 (tabela de problemas).
- Devolução ou destruição mediante solicitação, com declaração por escrito — não localizada como obrigação; tratada na Cl. 8 (tabela de problemas).

Cláusulas conformes
- Cl. 1 — atende à posição «cobrir informação escrita, oral ou eletrônica, marcada ou não». Sem alteração. (A limitação a informação «técnica ou comercial» não tem parâmetro na política; ver perguntas.)
- Cl. 7 — atende à posição «lei brasileira e foro de São Paulo aceitáveis». Sem alteração.

Limites
O profissional responsável confere as regras aplicáveis.

Perguntas para o advogado responsável
- O material é integral ou parcial? As Cl. 2, 4 e 6 existem e podem ser enviadas? Alguma delas define «Propósito», trata de devolução/destruição, LGPD ou requisição por autoridade?
- Quais posições da política são obrigatórias e quais são preferências? A classificação de risco das Cl. 3, 5 e 8 e das ausências depende dessa resposta.
- A amostra da base de clientes contém dados pessoais? Em caso positivo, confirmar a adequação do tratamento e se a cláusula de LGPD proposta é suficiente para a política, ou se o cliente exige obrigações mais específicas (não informadas).
- Há recuo autorizado para permitir à Receptora manter cópias de arquivo (Cl. 8)? A política não prevê essa exceção; a redação proposta não a inclui.
- A vigência de 3 anos conta da assinatura (como na minuta) ou do término do compartilhamento? A política não especifica o termo inicial.
- A restrição da Cl. 1 a informação «técnica ou comercial» é aceitável? A política não fixa posição sobre a natureza da informação, só sobre forma e marcação.
- «Propósito» deve constar como termo definido com a redação sugerida («avaliar uma integração de sistemas»), ou há definição própria do cliente?
- Fundamento a verificar, se necessário para sustentar a cláusula de dados pessoais: [AUTHORITY TO BE LOCATED].

