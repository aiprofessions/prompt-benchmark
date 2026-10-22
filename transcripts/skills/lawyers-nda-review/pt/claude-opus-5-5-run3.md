# Transcript — skill lawyers-nda-review [pt] — claude-opus-5-5 — run 3

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T07:00:00+00:00
- duration_s: 58.1
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

RESUMO
Minuta para revisão do advogado responsável; não é aconselhamento jurídico.
Lembrete: anonimize nomes e dados identificáveis e use apenas ferramenta aprovada pelo escritório.

  - Escopo recebido: [NÃO INFORMADO]. A numeração tem lacunas (Cl. 2, 4 e 6 não foram recebidas), por isso a análise trata o material como trechos.
  - Síntese:
      (a) Cl. 3 permite uso "para qualquer finalidade relacionada aos seus negócios". A política exige uso exclusivo para o Propósito.
      (b) Cl. 5 fixa vigência de 12 meses. A política prevê 3 anos (36 meses), uma diferença de 36 − 12 = 24 meses. A cláusula também não trata da proteção de segredos comerciais enquanto mantiverem essa condição.
      (c) Cl. 8 permite cópias de arquivo por prazo indeterminado. A política exige devolução ou destruição mediante solicitação, com declaração por escrito.
      (d) Não foram localizadas nos trechos a cláusula de cumprimento da LGPD (condicionada à existência de dados pessoais) nem o aviso imediato em caso de requisição por autoridade.
      (e) A política não classifica as posições como obrigatórias ou preferenciais e não traz critérios de risco. Por isso, os riscos ficaram [NÃO INFORMADO].
  - Premissas:
      Premissa: os identificadores originais (Cl. 1, 3, 5, 7, 8) foram preservados. A política foi organizada em P1 a P7, na ordem do texto: P1 abrangência da informação; P2 uso exclusivo para o Propósito; P3 vigência de 3 anos e segredos comerciais; P4 lei brasileira e foro de São Paulo; P5 devolução ou destruição com declaração escrita; P6 LGPD, se houver dados pessoais; P7 aviso imediato em caso de requisição por autoridade.
      Premissa: como o terminal não exibe tabelas, a tabela de problemas aparece em blocos por cláusula, com as seis colunas do modelo.
      Premissa: o cliente é designado como "Reveladora", sem repetir a razão social.


TABELA DE PROBLEMAS

  [Cl. 3]
    O que a minuta diz:  "A Receptora poderá usar a informação para qualquer finalidade relacionada aos seus negócios."
    Posição da política: P2. Uso exclusivo para o Propósito.
    Divergência:         O uso é amplo ("qualquer finalidade relacionada aos seus negócios"), e não restrito ao Propósito. O termo "Propósito" não foi localizado como definido nos trechos recebidos.
    Risco:               [NÃO INFORMADO]. A política não indica se a posição é obrigatória ou preferencial.
    Redação proposta:    "A Receptora usará a Informação Confidencial exclusivamente para o Propósito."

  [Cl. 5]
    O que a minuta diz:  "Vigência: 12 meses a partir da assinatura."
    Posição da política: P3. Vigência de 3 anos; segredos comerciais protegidos enquanto mantiverem essa condição.
    Divergência:         O prazo é inferior ao da política: 3 anos = 36 meses; 36 − 12 = 24 meses a menos. Os trechos não preveem proteção dos segredos comerciais enquanto mantiverem essa condição.
    Risco:               [NÃO INFORMADO]. Mesmo motivo da Cl. 3.
    Redação proposta:    "Vigência: 3 (três) anos a partir da assinatura. As obrigações relativas a segredos comerciais permanecerão em vigor enquanto essas informações mantiverem a condição de segredo comercial."
                         (O marco inicial "a partir da assinatura" foi mantido da minuta, porque a política não define o marco inicial.)

  [Cl. 8]
    O que a minuta diz:  "A Receptora poderá manter cópias de arquivo por prazo indeterminado."
    Posição da política: P5. Devolução ou destruição mediante solicitação, com declaração por escrito.
    Divergência:         A cláusula autoriza retenção indefinida, o que é incompatível com a devolução ou destruição mediante solicitação. Também não há obrigação de declaração por escrito.
    Risco:               [NÃO INFORMADO]. Mesmo motivo da Cl. 3.
    Redação proposta:    "Mediante solicitação da Reveladora, a Receptora devolverá ou destruirá a Informação Confidencial, inclusive cópias, e declarará por escrito o cumprimento dessa obrigação."
                         (Uma eventual exceção para cópias de arquivo não tem respaldo na política e fica sujeita à decisão do advogado.)


CLÁUSULAS AUSENTES

  - P6. Cláusula de cumprimento da LGPD, se houver dados pessoais. Não localizada nos trechos recebidos. A aplicabilidade depende de confirmar se a amostra da base de clientes contém dados pessoais.
    Risco: [NÃO INFORMADO].
    Proposta: «A Receptora cumprirá a LGPD no tratamento de quaisquer dados pessoais contidos na Informação Confidencial.»

  - P7. Aviso imediato à Reveladora se uma autoridade requisitar a informação. Não localizado nos trechos recebidos.
    Risco: [NÃO INFORMADO].
    Proposta: «Caso qualquer autoridade requisite a Informação Confidencial, a Receptora avisará imediatamente a Reveladora.»


CLÁUSULAS CONFORMES

  - Cl. 1. Atende a P1 (informação escrita, oral ou eletrônica, marcada ou não). Sem alteração.
  - Cl. 7. Atende a P4 (lei brasileira; foro de São Paulo). Sem alteração.

  Conferência de cobertura: 5 cláusulas recebidas = 3 na tabela (Cl. 3, 5, 8) + 2 conformes (Cl. 1, 7). Das 7 posições da política, 5 foram vinculadas a cláusulas (P1, P2, P3, P4, P5) e 2 estão em ausentes (P6, P7). 5 + 2 = 7.


LIMITES
O profissional responsável confere as regras aplicáveis.


PERGUNTAS PARA O ADVOGADO RESPONSÁVEL

  - O material é a minuta integral ou apenas trechos? As Cl. 2, 4 e 6 contêm definição de "Propósito", devolução/destruição, LGPD ou aviso de requisição por autoridade?
  - Quais posições da política são obrigatórias e quais são preferenciais? Há critérios de risco do cliente para classificar Cl. 3, 5 e 8 e as ausências P6 e P7?
  - "Propósito" está definido na minuta? Se não estiver, aprova incluir uma definição baseada na finalidade informada (avaliar uma integração de sistemas)? Essa redação seria nossa, não da política.
  - A amostra da base de clientes contém dados pessoais? Se sim, confirmar a adequação do tratamento e das obrigações correspondentes à LGPD e se a redação de P6 basta. [AUTHORITY TO BE LOCATED]
  - A Cl. 1 limita a informação a "técnica ou comercial". A política trata apenas da forma (escrita, oral, eletrônica; marcada ou não). Considera que a amostra da base de clientes está suficientemente coberta, ou deseja ampliar o objeto?
  - Na Cl. 5, a "vigência" da minuta corresponde ao prazo das obrigações de confidencialidade previsto na política? O marco "a partir da assinatura" é aceitável? "Segredo comercial" precisa ser definido no acordo?
  - Na Cl. 8, há recuo autorizado para cópias de arquivo (por exemplo, backups ou exigência regulatória)? Se houver, em que condições e com qual prazo?
  - Em P7, aceita alguma ressalva para hipóteses em que o aviso imediato seja vedado à Receptora? A política não prevê essa ressalva. Fundamento a verificar: [AUTHORITY TO BE LOCATED].
  - "Foro da comarca de São Paulo" (Cl. 7) corresponde ao que a política chama de "foro de São Paulo"?

