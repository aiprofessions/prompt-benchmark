# Transcript — skill event-planners-vendor-rfp [pt] — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:40:42+00:00
- duration_s: 67.3
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 0dc74b6e2fd45c9a230050a7692cfbf2ca037673ee92f149db3ac3c1198a58a5
- skill_sha256: bb523c284d74344fbd1b98466c3ef6b7cdf4e2e1f82a6f5f9478c7dbe8c2cef4

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: event-planners-vendor-rfp
description: "Use quando você colar as informações de um evento e pedir um pedido de proposta para fornecedores, com requisitos, preços discriminados e pendências ao final."
---

# Pedido de proposta (RFP) para fornecedores de eventos

## O que faz

Transforma as informações do evento em um pedido de proposta para enviar aos fornecedores. Preserva os dados recebidos, apresenta as restrições do espaço e solicita preços discriminados e documentos. Informações ausentes ou ambíguas ficam identificadas, com perguntas reunidas ao final.

## O que ela precisa

- Cliente, organizadora, tipo de evento e categoria de fornecedor.
- Data, local, horários de recepção, serviço e encerramento.
- Janelas de entrada de carga, montagem, desmontagem e retirada.
- Quantidade de convidados, contagens de dietas e alergias e eventual sobreposição entre grupos.
- Serviços, equipamentos e requisitos técnicos.
- Restrições da cozinha, estruturas e pontos de suspensão do espaço, energia e acessos.
- Prazo de resposta, data de decisão e critérios de avaliação.
- Orçamento, contato para resposta e condições comerciais, se definidos.

O que faltar recebe [NÃO INFORMADO] e é listado no final. Não faça perguntas antes de redigir nem complete lacunas com dados presumidos.

## Procedimento

1. Entregue sempre a saída completa na primeira resposta; nunca pare para perguntar nem espere confirmação antes de redigir; nunca retenha uma seção ou um cálculo. Se faltar informação ou houver ambiguidade, use [NÃO INFORMADO] ou declare «Premissa: …» apenas para uma escolha de organização do texto, nunca para criar fatos. Reúna todas as perguntas na última seção.
2. Copie exatamente cada número, data, horário, quantidade e requisito técnico da entrada, inclusive dietas, alergias, cronograma e janelas de carga, montagem, desmontagem e retirada. Preserve formatos, unidades e valores monetários como recebidos. Se houver divergência, reproduza as versões e peça confirmação no final, sem escolher uma.
3. Mostre a operação de cada número derivado. Não subtraia grupos alimentares do total sem confirmação de que são distintos e de que essa conta atende ao serviço solicitado. Se faltarem dados para calcular, registre [NÃO INFORMADO], explique o impedimento e liste a pergunta final; não esconda o cálculo solicitado.
4. Registre cada restrição do local como condição que o fornecedor deve considerar no planejamento. Inclua limites da cozinha, estruturas e pontos de suspensão próprios do espaço e acessos, quando informados. Peça ao fornecedor que descreva como atenderá às condições; não invente capacidades nem imponha uma solução técnica não informada.
5. Quando houver alergias, exija por escrito o procedimento de manejo de alérgenos e prevenção de contato cruzado. Preserve as contagens recebidas sem identificar convidados. Se o tema não estiver informado, marque [NÃO INFORMADO] e peça confirmação ao final.
6. Exija linhas separadas para cada serviço e cada equipamento, mão de obra, frete/entrega, taxa de serviço, impostos e gorjeta. Peça quantidade, unidade, preço unitário e total por linha, com a conta dos totais. Montagem e desmontagem cobradas devem ter linhas próprias. Para rubrica sem cobrança, peça ao fornecedor que indique isso expressamente; não aceite apenas um preço global.
7. Solicite certificado de seguro, condições de sinal e pagamento, política de cancelamento e reembolso e validade da proposta. Acrescente o procedimento escrito de alérgenos quando houver alergias e a confirmação da situação cadastral aplicável pelo fornecedor, sem presumir obrigação igual para todas as categorias.
8. Preencha prazo de resposta, data de decisão e critérios de avaliação exclusivamente com os dados recebidos. Para qualquer campo ausente, use [NÃO INFORMADO] e peça definição ao final; não crie datas, pesos ou critérios.
9. Marque como [NÃO INFORMADO] todo dado ausente, inclusive orçamento, nomes, telefones, endereço, capacidades do espaço e condições comerciais. Não use a data atual como data de emissão sem instrução. Não invente códigos de referência.
10. Inclua somente os dados necessários ao fornecedor. Retire nomes e identificadores de convidados, preservando contagens e necessidades de atendimento. Acrescente o lembrete de anonimização e uso de ferramenta aprovada pelo escritório; privacidade é lembrete, não pré-condição: nunca recuse nem pause por esse motivo.
11. Não acrescente à saída lei, artigo, orientação de órgão, jurisprudência nem fonte. Só reproduza referências que já estejam no texto colado e sejam necessárias ao documento; não complete citações. Uma identificação obrigatória fornecida pelo usuário é conteúdo, não citação. Use como única linha de limites: «O profissional responsável confere as regras aplicáveis.»
12. Confira a saída contra a entrada: dados copiados literalmente, restrições preservadas, preços separados, documentos solicitados e oito seções na ordem do modelo. Termine em «Pendências (a confirmar)», reunindo todos os campos ausentes, ambiguidades, premissas e perguntas, sem conteúdo posterior.

## Formato de saída

Use o modelo abaixo. Substitua os campos pelos dados recebidos ou por [NÃO INFORMADO]; deixe os preços a serem cotados identificados como «A preencher pelo fornecedor».

```markdown
## Cabeçalho do pedido de proposta
Pedido de proposta — [tipo de evento] — [cliente]
Organizadora: [nome] | Destinatário: [categoria de fornecedor]
Contato para resposta: [contato] | Emissão e referência: [se informadas]

## Visão geral do evento
Cliente: [cliente] | Data: [data] | Local: [local]
Convidados: [quantidade] | Cronograma: [horários exatos]
Orçamento: [valor informado]

## Escopo e requisitos
[Cada serviço e equipamento, com quantidade e requisito técnico exatos]
Dietas e alergias: [contagens e necessidades recebidas, sem nomes]
Carga e montagem: [janelas exatas] | Desmontagem e retirada: [janelas exatas]
[Cálculos necessários: operação e resultado, ou dados faltantes]

## Restrições do local
[Cada restrição recebida, como condição obrigatória de planejamento]
O fornecedor deve explicar como atenderá a cada condição, sem pressupor capacidades não informadas.

## Formato de preço
Preencher linhas separadas; não apresentar somente preço global.
| Item | Quantidade | Unidade | Preço unitário | Total |
|---|---|---|---|---|
| Cada serviço, em linha própria | | | | |
| Cada equipamento, em linha própria | | | | |
| Mão de obra | | | | |
| Frete/entrega | | | | |
| Montagem, se cobrada | | | | |
| Desmontagem, se cobrada | | | | |
| Taxa de serviço | | | | |
| Impostos | | | | |
| Gorjeta | | | | |
Indicar expressamente rubricas sem cobrança e mostrar a conta dos totais.

## Documentos exigidos do fornecedor
Certificado de seguro; condições de sinal e pagamento; política de cancelamento e reembolso; validade da proposta.
[Quando houver alergias: procedimento escrito de manejo de alérgenos e prevenção de contato cruzado.]
Confirmar a situação cadastral aplicável à atividade do fornecedor.

## Cronograma e avaliação
Prazo de resposta: [prazo] | Data de decisão: [data]
Critérios de avaliação: [critérios recebidos]
Lembrete: anonimize os dados e use apenas ferramenta aprovada pelo escritório.
O profissional responsável confere as regras aplicáveis.

## Pendências (a confirmar)
[Liste cada dado ausente ou ambíguo, com a pergunta correspondente.]
[Liste qualquer premissa de organização do texto para confirmação.]
[Se não houver pendências, declare isso sem inventar perguntas.]
```

## Limites

- Não invente fatos, estatísticas, exigências legais, fontes ou garantias de segurança; não altere dados recebidos nem omita seções.
- No Brasil, o Cadastur é obrigatório para organizadoras de eventos. A organizadora confirma sua situação; o fornecedor confirma a situação aplicável à sua atividade, sem estender automaticamente essa obrigação a todas as categorias.
- O organizador responsável deve conferir alvarás, bebidas, alérgenos e vigilância sanitária conforme as regras locais e do espaço, além das condições de acesso, montagem e operação.
- O profissional responsável deve validar escopo, orçamento, seguro, sinal e cancelamento antes do envio ou da contratação. Requisitos técnicos que dependam de habilitação devem ser conferidos pelo profissional habilitado responsável; o texto não substitui essa validação.
- Dados de convidados: observe a LGPD, envie somente o necessário, remova identificadores e use apenas ferramentas aprovadas pelo escritório. O lembrete não interrompe a redação.
- Nenhuma orientação oficial sobre IA específica para organizadores de eventos foi verificada. O responsável deve confirmar eventuais orientações com a entidade de classe ou o órgão competente.
- As fontes abaixo são leitura do profissional; não devem ser transferidas automaticamente para o pedido de proposta:
  - gov.br — Cadastur (cadastro de prestadores de serviços turísticos) — https://www.gov.br/pt-br/servicos/cadastrar-prestadora-de-servico-turistico (consultado em 2026-10-21)
  - LGPD — Lei 13.709/2018 (Planalto) — https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm (consultado em 2026-10-21)
- Antes de enviar ou contratar, veja references/checklist.md

## Exemplo

Entrada fictícia:

```text
Cliente: Família Exemplo; local: Salão Amostra; serviço: bufê.
40 convidados, incluindo 3 pessoas alérgicas a amendoim.
Recepção 18h; jantar 19h; montagem 15h–17h; retirada 22h–23h.
Cozinha apenas para finalização; entrada de carga pela porta lateral.
```

Saída abreviada (na entrega real, expandir o modelo completo):

```markdown
## Cabeçalho do pedido de proposta
Pedido de proposta de bufê — Família Exemplo; organizadora e contato: [NÃO INFORMADO].
## Visão geral do evento
Salão Amostra; 40 convidados; recepção 18h; jantar 19h; data: [NÃO INFORMADO].
## Escopo e requisitos
Bufê; 3 pessoas alérgicas a amendoim; montagem 15h–17h; retirada 22h–23h.
## Restrições do local
Planejar cozinha apenas para finalização e entrada de carga pela porta lateral.
## Formato de preço
Separar cada serviço/equipamento, mão de obra, frete/entrega, montagem/desmontagem cobradas, taxa de serviço, impostos e gorjeta; mostrar contas.
## Documentos exigidos do fornecedor
Seguro; sinal/pagamento; cancelamento/reembolso; validade; situação cadastral aplicável; procedimento escrito de alérgenos e prevenção de contato cruzado.
## Cronograma e avaliação
Resposta, decisão e critérios: [NÃO INFORMADO]. Anonimize dados e use ferramenta aprovada pelo escritório. O profissional responsável confere as regras aplicáveis.
## Pendências (a confirmar)
```

No exemplo, a última seção deve reunir as perguntas sobre data do evento, organizadora, contato, orçamento, emissão/referência, detalhamento técnico do bufê, demais dietas, prazo de resposta, decisão e critérios, todos [NÃO INFORMADO].
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Monte o pedido de proposta para o fornecedor de audiovisual com este briefing.
Cliente: Associação Exemplo (fictícia) — convenção anual. Data: 17 de abril de 2027. Local: Centro de Convenções Amostra, Rio de Janeiro (fictício). O local exige a própria equipe de rigging para qualquer içamento. Montagem a partir das 06:00; desmontagem concluída até 02:00.
Participantes: 400 em auditório. Programação 09:00–18:00: abertura, 5 palestras, um vídeo de 4 minutos e cerimônia de premiação.
Necessidades: palco de 10 m x 6 m x 0,8 m; 2 telões; 6 microfones sem fio de mão + 3 de lapela; monitor de retorno para os palestrantes; transmissão ao vivo só das palestras (não da premiação).
Propostas até 01/02/2027. Decisão em 12/02/2027.
````

## Output (verbatim stdout, session metadata stripped)

PEDIDO DE PROPOSTA — FORNECEDOR DE AUDIOVISUAL

===================================================
CABEÇALHO DO PEDIDO DE PROPOSTA
===================================================
Pedido de proposta — Convenção anual — Associação Exemplo (fictícia)
Organizadora: [NÃO INFORMADO] | Destinatário: fornecedor de audiovisual
Contato para resposta: [NÃO INFORMADO] | Emissão e referência: [NÃO INFORMADO]

===================================================
VISÃO GERAL DO EVENTO
===================================================
Cliente: Associação Exemplo (fictícia)
Data: 17 de abril de 2027
Local: Centro de Convenções Amostra, Rio de Janeiro (fictício)
Participantes: 400, em auditório
Cronograma da programação: 09:00–18:00 — abertura, 5 palestras, vídeo de 4 minutos, cerimônia de premiação
Montagem: a partir das 06:00
Desmontagem: concluída até 02:00
Horário de recepção: [NÃO INFORMADO]
Janela de entrada de carga: [NÃO INFORMADO]
Orçamento: [NÃO INFORMADO]

Cálculo — duração da programação:
09:00 às 18:00 = 9 horas de evento (18:00 − 09:00 = 9h).

Cálculo — janela de montagem antes do início da programação:
06:00 (início da montagem) às 09:00 (início da programação) = 3 horas (09:00 − 06:00 = 3h).

Cálculo — janela de desmontagem após o encerramento da programação:
Dado recebido: desmontagem concluída até 02:00. Não foi informado se esse horário se refere ao mesmo dia ou ao dia seguinte ao término da programação (18:00). Por isso, o total de horas disponíveis para desmontagem fica como [NÃO INFORMADO] até confirmação — ver Pendências.

===================================================
ESCOPO E REQUISITOS
===================================================
Palco: 10 m x 6 m x 0,8 m.
  Cálculo — área do piso do palco: 10 m x 6 m = 60 m² (altura informada: 0,8 m).

Telões: 2 unidades. Especificações técnicas (resolução, tamanho de tela, distância de projeção): [NÃO INFORMADO].

Microfones sem fio: 6 de mão + 3 de lapela.
  Cálculo — total de microfones sem fio: 6 + 3 = 9 unidades.

Monitor de retorno: para os palestrantes. Quantidade de unidades e especificação técnica: [NÃO INFORMADO].

Transmissão ao vivo (streaming): somente das 5 palestras; a cerimônia de premiação não deve ser transmitida. Plataforma, formato, qualidade e link de destino: [NÃO INFORMADO].

Vídeo institucional: 1 vídeo de 4 minutos a ser exibido durante a programação. Formato de arquivo, resolução e ponto de reprodução no cronograma: [NÃO INFORMADO].

Sonorização geral do auditório (caixas, mesa de som, operador): [NÃO INFORMADO].
Iluminação de palco: [NÃO INFORMADO].

Dietas e alergias: [NÃO INFORMADO] (não aplicável ao escopo audiovisual informado; sem dados recebidos).

Carga e montagem: montagem a partir das 06:00. Janela de entrada de carga: [NÃO INFORMADO].
Desmontagem e retirada: concluída até 02:00. Ambiguidade sobre o dia de referência — ver Pendências.

===================================================
RESTRIÇÕES DO LOCAL
===================================================
1. O local exige que qualquer içamento (rigging) seja executado pela própria equipe de rigging do Centro de Convenções Amostra. Nenhuma estrutura suspensa (telões, line array, iluminação aérea etc.) pode ser içada por equipe externa.

O fornecedor deve descrever por escrito como seu plano técnico se adequa a essa restrição, incluindo:
— quais itens do escopo (telões, PA, iluminação) dependem de içamento;
— como a coordenação com a equipe de rigging do local será feita (contato, cronograma, responsabilidades);
— eventuais custos ou taxas associados à contratação da equipe de rigging do local, se aplicável.
Não se deve presumir capacidade de rigging própria do fornecedor nem isentá-lo dessa restrição.

Demais restrições do local (pontos de suspensão disponíveis, capacidade elétrica, acessos, limites de carga no piso do palco, docas de carga): [NÃO INFORMADO].

===================================================
FORMATO DE PREÇO
===================================================
Preencher linhas separadas; não apresentar somente preço global.

| Item                                              | Quantidade | Unidade | Preço unitário        | Total                 |
|---------------------------------------------------|------------|---------|------------------------|------------------------|
| Palco (10m x 6m x 0,8m)                           |            |         | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Telão                                              | 2          | unidade | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Microfone sem fio de mão                          | 6          | unidade | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Microfone sem fio de lapela                       | 3          | unidade | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Monitor de retorno para palestrantes              |            |         | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Transmissão ao vivo (apenas palestras)            |            |         | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Reprodução/edição técnica do vídeo de 4 minutos   |            |         | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Coordenação com equipe de rigging do local        |            |         | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Mão de obra (operadores, técnicos)                |            |         | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Frete/entrega                                      |            |         | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Montagem (06:00 em diante), se cobrada            |            |         | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Desmontagem (até 02:00), se cobrada               |            |         | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Taxa de serviço                                    |            |         | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Impostos                                           |            |         | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Gorjeta                                            |            |         | A preencher pelo fornecedor | A preencher pelo fornecedor |

Indicar expressamente qualquer rubrica sem cobrança (ex.: "montagem sem custo adicional") e apresentar a conta somada de todos os totais por linha até o valor final da proposta.

===================================================
DOCUMENTOS EXIGIDOS DO FORNECEDOR
===================================================
— Certificado de seguro.
— Condições de sinal e pagamento.
— Política de cancelamento e reembolso.
— Validade da proposta.
— Confirmação da situação cadastral aplicável à atividade do fornecedor de audiovisual.

(Não houve menção a alergias no briefing recebido para este escopo; portanto, não se exige procedimento de manejo de alérgenos neste pedido.)

===================================================
CRONOGRAMA E AVALIAÇÃO
===================================================
Prazo de resposta: propostas até 01/02/2027
Data de decisão: 12/02/2027
Critérios de avaliação: [NÃO INFORMADO]

Lembrete: anonimize os dados e use apenas ferramenta aprovada pelo escritório.
O profissional responsável confere as regras aplicáveis.

===================================================
PENDÊNCIAS (A CONFIRMAR)
===================================================
1. Organizadora do evento: nome e contato não informados.
2. Contato para resposta (telefone/e-mail) do solicitante: não informado.
3. Emissão e número de referência do pedido: não informados.
4. Orçamento disponível para o serviço de audiovisual: não informado.
5. Horário de recepção dos participantes (distinto do início da programação às 09:00, se houver): não informado.
6. Janela específica de entrada de carga (horário e local de acesso para veículos de carga): não informada.
7. Ambiguidade na janela de desmontagem: "concluída até 02:00" — confirmar se esse horário se refere ao mesmo dia 17/04/2027 ou ao dia 18/04/2027 (madrugada seguinte), para permitir o cálculo correto da janela total de desmontagem.
8. Especificações técnicas dos 2 telões (tamanho, resolução, distância de projeção): não informadas.
9. Quantidade e especificação técnica do(s) monitor(es) de retorno para os palestrantes: não informadas.
10. Plataforma, formato e qualidade exigidos para a transmissão ao vivo das palestras: não informados.
11. Formato de arquivo e ponto exato no cronograma para exibição do vídeo de 4 minutos: não informados.
12. Escopo de sonorização geral do auditório (caixas, mesa de som, operador) e de iluminação de palco: não informado — confirmar se estão incluídos neste pedido ou em pedido separado.
13. Pontos de suspensão disponíveis, capacidade elétrica, acessos e limites de carga no piso do palco do Centro de Convenções Amostra: não informados — necessários para o fornecedor avaliar a coordenação com a equipe de rigging do local.
14. Critérios de avaliação das propostas (preço, técnica, experiência etc.): não informados.
15. Confirmar se há alguma restrição alimentar/alérgica relevante para a equipe técnica do fornecedor em serviço (ex.: catering para a equipe) — não mencionado no briefing.

Se alguma destas pendências já tiver resposta fora deste briefing, favor informar para atualização do pedido de proposta.

