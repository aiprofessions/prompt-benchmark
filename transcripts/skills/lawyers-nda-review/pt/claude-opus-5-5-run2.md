# Transcript — skill lawyers-nda-review [pt] — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:28:15+00:00
- duration_s: 56.1
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
Lembrete: anonimize nomes e dados identificáveis e use apenas ferramenta aprovada pelo escritório. Nesta resposta, as partes aparecem como "Reveladora" (cliente) e "Receptora".

- Escopo recebido: [NÃO INFORMADO]. A numeração salta as Cl. 2, 4 e 6; por isso, as exigências não encontradas aparecem como "não localizadas nos trechos recebidos".
- Síntese: há 3 cláusulas divergentes (Cl. 3, Cl. 5 e Cl. 8) e 2 conformes (Cl. 1 e Cl. 7). Três exigências da política não foram localizadas: proteção de segredos comerciais, cláusula de cumprimento da LGPD (se houver dados pessoais) e aviso imediato em caso de requisição por autoridade. O risco ficou [NÃO INFORMADO] em todos os itens, porque a política não indica quais posições são obrigatórias e quais são preferências.
- Premissas:
  - Premissa: as posições da política foram numeradas de P1 a P8, na ordem do texto: P1 abrangência (escrita, oral ou eletrônica, marcada ou não); P2 uso exclusivo para o Propósito; P3 vigência de 3 anos; P4 segredos comerciais protegidos enquanto mantiverem essa condição; P5 lei brasileira e foro de São Paulo; P6 devolução ou destruição mediante solicitação, com declaração por escrito; P7 cláusula de cumprimento da LGPD, se houver dados pessoais; P8 aviso imediato à Reveladora em caso de requisição por autoridade.
  - Premissa: os identificadores das cláusulas são os originais da minuta.
  - Contagem de cobertura: 5 cláusulas recebidas = 3 na tabela + 2 conformes. 8 posições = 5 vinculadas a cláusulas (P1, P2, P3, P5, P6) + 3 não localizadas (P4, P7, P8).


TABELA DE PROBLEMAS

Os itens estão em blocos porque o terminal não exibe tabelas. Cada bloco traz as seis colunas.

[1] Cláusula: Cl. 3
    O que a minuta diz: "A Receptora poderá usar a informação para qualquer finalidade relacionada aos seus negócios."
    Posição da política: P2, uso exclusivo para o Propósito.
    Divergência: a minuta autoriza qualquer finalidade ligada aos negócios da Receptora. A política restringe o uso ao Propósito.
    Risco: [NÃO INFORMADO]
    Redação proposta: «A Receptora utilizará a Informação Confidencial exclusivamente para o Propósito, qual seja, a avaliação de uma integração de sistemas.»

[2] Cláusula: Cl. 5
    O que a minuta diz: "Vigência: 12 meses a partir da assinatura."
    Posição da política: P3, vigência de 3 anos.
    Divergência: prazo inferior ao da política. Conta: 3 anos = 36 meses; 36 − 12 = 24 meses a menos. A política não define o termo inicial; "a partir da assinatura" foi mantido da minuta original.
    Risco: [NÃO INFORMADO]
    Redação proposta: «Vigência: 3 anos a partir da assinatura.»

[3] Cláusula: Cl. 8
    O que a minuta diz: "A Receptora poderá manter cópias de arquivo por prazo indeterminado."
    Posição da política: P6, devolução ou destruição mediante solicitação, com declaração por escrito.
    Divergência: a minuta permite reter cópias sem limite de prazo e não prevê devolução ou destruição mediante solicitação, nem declaração por escrito. A política não prevê recuo que autorize cópias de arquivo.
    Risco: [NÃO INFORMADO]
    Redação proposta (substitui a Cl. 8): «Mediante solicitação da Reveladora, a Receptora devolverá ou destruirá a Informação Confidencial, inclusive eventuais cópias, e declarará por escrito a devolução ou a destruição.»


CLÁUSULAS AUSENTES

- P4, segredos comerciais protegidos enquanto mantiverem essa condição: não localizada nos trechos recebidos. Risco: [NÃO INFORMADO]. Proposta: «Os segredos comerciais permanecerão protegidos enquanto mantiverem essa condição, inclusive após o término da vigência.»
- P7, cláusula de cumprimento da LGPD, se houver dados pessoais: não localizada nos trechos recebidos. A aplicação depende de a amostra da base de clientes conter dados pessoais [NÃO INFORMADO]. Risco: [NÃO INFORMADO]. Proposta: «Caso a Informação Confidencial inclua dados pessoais, a Receptora cumprirá a LGPD no respectivo tratamento.»
- P8, aviso imediato à Reveladora em caso de requisição por autoridade: não localizada nos trechos recebidos. Risco: [NÃO INFORMADO]. Proposta: «Se uma autoridade requisitar a Informação Confidencial, a Receptora avisará imediatamente a Reveladora.»


CLÁUSULAS CONFORMES

- Cl. 1: atende a P1 (informação escrita, oral ou eletrônica, marcada ou não). Sem alteração. A restrição a informação "técnica ou comercial" não contraria nenhuma posição da política; ver pergunta abaixo.
- Cl. 7: atende a P5 (lei brasileira e foro de São Paulo aceitáveis). Sem alteração.


LIMITES

O profissional responsável confere as regras aplicáveis.


PERGUNTAS PARA O ADVOGADO RESPONSÁVEL

- Prioridade das posições: quais posições da política são obrigatórias e quais são preferências? Pelo critério supletivo, a descumprida obrigatória seria risco Alto e a preferência seria risco Médio. Até essa definição, o risco fica [NÃO INFORMADO].
- Escopo: a minuta recebida está completa? As Cl. 2, 4 e 6 tratam da definição de "Propósito", da proteção de segredos comerciais, da LGPD ou do aviso em caso de requisição por autoridade?
- Propósito: a minuta define "Propósito" em outro trecho? A redação proposta para a Cl. 3 deve remeter a essa definição ou manter a descrição inserida?
- Cl. 1: a amostra da base de clientes se enquadra em informação "técnica ou comercial"? A política exige abrangência por tipo de informação ou apenas pela forma e pela marcação?
- Cl. 5: os "3 anos" da política se referem à vigência do acordo ou à duração da obrigação de sigilo? O termo inicial "a partir da assinatura" é aceitável?
- Cl. 8: existe recuo autorizado para cópias de arquivo, por exemplo por exigência legal ou de backup? A política não prevê nenhum; qualquer concessão depende da sua decisão.
- Cl. 8: a escolha entre devolução e destruição cabe à Reveladora ou à Receptora? A política não define.
- Dados pessoais: a amostra da base de clientes contém dados pessoais? Se contiver, avalie a adequação do tratamento e das obrigações da Receptora, inclusive o compartilhamento em si, além da cláusula exigida pela política. [AUTHORITY TO BE LOCATED]
- Requisição por autoridade: deve-se admitir alguma ressalva ao aviso imediato, por exemplo quando o aviso for vedado? A política não prevê ressalva; qualquer inclusão depende da sua decisão. [AUTHORITY TO BE LOCATED]

