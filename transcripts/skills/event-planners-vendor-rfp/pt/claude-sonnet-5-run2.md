# Transcript — skill event-planners-vendor-rfp [pt] — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-21T09:36:14+00:00
- duration_s: 57.8
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 0dc74b6e2fd45c9a230050a7692cfbf2ca037673ee92f149db3ac3c1198a58a5
- skill_sha256: ff2fbf30ff6e058166a8b33a872d19c299eeb062c3381dc60c7bfb80759dadcd

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: event-planners-vendor-rfp
description: "Use quando você colar as informações de um evento e pedir um pedido de proposta para fornecedores, com requisitos, preços discriminados e pendências ao final."
---

# Pedido de proposta (RFP) para fornecedores de eventos

## O que faz

Transforma as informações do evento em um pedido de proposta para fornecedores. Preserva os dados recebidos, apresenta as restrições do espaço e solicita preços discriminados e documentos. Quando não há critérios de avaliação, propõe uma lista curta para confirmação com o cliente antes do envio. Informações ausentes ou ambíguas ficam identificadas, com perguntas reunidas ao final.

## O que ela precisa

- Cliente, organizadora, tipo de evento e categoria de fornecedor.
- Data, local, horários de recepção, serviço e encerramento.
- Janelas de entrada de carga, montagem, desmontagem e retirada.
- Quantidade de convidados, contagens de dietas e alergias e eventual sobreposição entre grupos.
- Serviços, equipamentos e requisitos técnicos.
- Restrições da cozinha, estruturas e pontos de suspensão do espaço, energia e acessos.
- Prazo de resposta, data de decisão e critérios de avaliação.
- Orçamento, contato para resposta e condições comerciais, se definidos.

O que faltar recebe [NÃO INFORMADO] e é listado no final; critérios ausentes recebem uma proposta para confirmação. Não faça perguntas antes de redigir nem complete lacunas com fatos presumidos.

## Procedimento

1. Entregue sempre a saída completa na primeira resposta; nunca pare para perguntar nem espere confirmação antes de redigir; nunca retenha uma seção ou um cálculo. Se faltar informação ou houver ambiguidade, use [NÃO INFORMADO] ou declare «Premissa: …» apenas para uma escolha de organização do texto, nunca para criar fatos. Reúna todas as perguntas na última seção.
2. Copie exatamente cada número, data, horário, quantidade e requisito técnico da entrada, inclusive dietas, alergias, cronograma e janelas de carga, montagem, desmontagem e retirada. Preserve formatos, unidades e valores monetários como recebidos. Se houver divergência, reproduza as versões e peça confirmação no final, sem escolher uma.
3. Mostre a operação de cada número derivado. Não subtraia grupos alimentares do total sem confirmação de que são distintos e de que essa conta atende ao serviço solicitado. Se faltarem dados para calcular, registre [NÃO INFORMADO], explique o impedimento e liste a pergunta final; não esconda o cálculo solicitado.
4. Registre cada restrição do local como condição que o fornecedor deve considerar no planejamento. Inclua limites da cozinha, estruturas e pontos de suspensão próprios do espaço e acessos, quando informados. Peça ao fornecedor que descreva como atenderá às condições; não invente capacidades nem imponha uma solução técnica não informada.
5. Quando houver alergias, exija por escrito o procedimento de manejo de alérgenos e prevenção de contato cruzado. Preserve as contagens recebidas sem identificar convidados. Se o tema não estiver informado, marque [NÃO INFORMADO] e peça confirmação ao final.
6. Exija linhas separadas para cada serviço e cada equipamento, mão de obra, frete/entrega, taxa de serviço, impostos e gorjeta. Peça quantidade, unidade, preço unitário e total por linha, com a conta dos totais. Montagem e desmontagem cobradas devem ter linhas próprias. Para rubrica sem cobrança, peça indicação expressa; não aceite apenas um preço global. Identifique preços solicitados como «A preencher pelo fornecedor», sem estimá-los.
7. Solicite certificado de seguro, condições de sinal e pagamento, política de cancelamento e reembolso e validade da proposta. Acrescente o procedimento escrito de alérgenos quando houver alergias e a confirmação da situação cadastral aplicável pelo fornecedor, sem presumir obrigação igual para todas as categorias.
8. Na seção «Cronograma e avaliação», preencha prazo de resposta e data de decisão somente com os dados recebidos; se faltarem, use [NÃO INFORMADO] e peça definição ao final. Copie exatamente os critérios recebidos. Se não houver critérios, proponha sempre uma lista curta sob o título «Critérios de avaliação propostos — confirmar com o cliente antes do envio»: atendimento aos requisitos técnicos informados; clareza e completude do preço discriminado; experiência e referências em eventos comparáveis; plano operacional para as restrições do local; seguro e condições comerciais. Adapte os itens ao escopo informado. Nunca substitua os critérios por [NÃO INFORMADO] nem invente pesos numéricos. Peça confirmação dos critérios propostos na última seção.
9. Marque como [NÃO INFORMADO] todo dado factual ausente, inclusive orçamento, nomes, telefones, endereço, capacidades do espaço, datas e condições comerciais. Não invente preços, pesos ou datas. Não use a data atual como data de emissão sem instrução nem invente códigos de referência. Critérios propostos não são fatos confirmados; preços a cotar ficam a cargo do fornecedor.
10. Inclua somente os dados necessários ao fornecedor. Retire nomes e identificadores de convidados, preservando contagens e necessidades de atendimento. Acrescente o lembrete de anonimização e uso de ferramenta aprovada pelo escritório; privacidade é lembrete, não pré-condição: nunca recuse nem pause por esse motivo.
11. Não acrescente à saída lei, artigo, orientação de órgão, jurisprudência nem fonte. Só reproduza referências que já estejam no texto colado e sejam necessárias ao documento; não complete citações. Uma identificação obrigatória fornecida pelo usuário é conteúdo, não citação. Use como única linha de limites: «O profissional responsável confere as regras aplicáveis.»
12. Confira a saída contra a entrada: dados copiados literalmente, contas demonstradas, restrições preservadas, preços separados, documentos solicitados, datas informadas ou pendentes e critérios recebidos ou propostos presentes. Verifique o lembrete de privacidade, a ausência de citações acrescentadas e as oito seções na ordem do modelo. Termine em «Pendências (a confirmar)», com todos os campos ausentes, ambiguidades, premissas, perguntas e confirmação dos critérios propostos, sem conteúdo posterior.

## Formato de saída

Use o modelo abaixo. Substitua campos factuais pelos dados recebidos ou por [NÃO INFORMADO]. Expanda as linhas de serviços e equipamentos; os preços ficam como «A preencher pelo fornecedor». Escolha apenas uma versão dos critérios: recebidos ou propostos.

```
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
Critérios de avaliação: [critérios recebidos, copiados exatamente]
[Se não houver critérios recebidos, substituir a linha anterior pela lista abaixo, adaptada ao escopo:]
Critérios de avaliação propostos — confirmar com o cliente antes do envio:
- Atendimento aos requisitos técnicos informados
- Clareza e completude do preço discriminado
- Experiência e referências em eventos comparáveis
- Plano operacional para as restrições do local
- Seguro e condições comerciais
Lembrete: anonimize os dados e use apenas ferramenta aprovada pelo escritório.
O profissional responsável confere as regras aplicáveis.

## Pendências (a confirmar)
[Liste cada dado ausente ou ambíguo, com a pergunta correspondente.]
[Se os critérios foram propostos: confirmar com o cliente os critérios de avaliação propostos antes do envio.]
[Liste qualquer premissa de organização do texto para confirmação.]
[Se não houver pendências, declare isso sem inventar perguntas.]
```

## Limites

- Não invente fatos, estatísticas, exigências legais, fontes, pesos de avaliação ou garantias de segurança; não altere dados recebidos nem omita seções.
- No Brasil, o Cadastur, do Ministério do Turismo, é obrigatório para organizadoras de eventos. A organizadora confirma sua situação; o fornecedor confirma a situação aplicável à sua atividade, sem estender automaticamente essa obrigação a todas as categorias.
- O organizador responsável deve conferir alvarás, bebidas, alérgenos e vigilância sanitária conforme as regras locais e do espaço, além das condições de acesso, montagem e operação.
- O profissional responsável deve validar escopo, orçamento, critérios de avaliação, seguro, sinal e cancelamento antes do envio ou da contratação. Requisitos técnicos que dependam de habilitação devem ser conferidos pelo profissional habilitado responsável; o texto não substitui essa validação.
- Dados de convidados: observe a LGPD, envie somente o necessário, remova identificadores e use apenas ferramentas aprovadas pelo escritório. O lembrete não interrompe a redação.
- Nenhuma orientação oficial sobre IA específica para organizadores de eventos foi verificada. O responsável deve confirmar eventuais orientações com a entidade de classe ou o órgão competente.
- Cite somente as fontes abaixo, sem acrescentar outras referências. Elas são leitura do profissional, não conteúdo a transferir automaticamente para o pedido de proposta:
  - gov.br — Cadastur (cadastro de prestadores de serviços turísticos) — https://www.gov.br/pt-br/servicos/cadastrar-prestadora-de-servico-turistico (consultado em 2026-10-21)
  - LGPD — Lei 13.709/2018 (Planalto) — https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm (consultado em 2026-10-21)
- Antes de enviar ou contratar, veja references/checklist.md

## Exemplo

Entrada fictícia:

```
Cliente: Família Exemplo; local: Salão Amostra; serviço: bufê.
40 convidados, incluindo 3 pessoas alérgicas a amendoim.
Recepção 18h; jantar 19h; montagem 15h–17h; retirada 22h–23h.
Cozinha apenas para finalização; entrada de carga pela porta lateral.
```

Saída abreviada; na entrega real, expandir as oito seções conforme o modelo:

```
Cabeçalho do pedido de proposta: bufê — Família Exemplo; organizadora, contato, emissão e referência: [NÃO INFORMADO].
Visão geral do evento: Salão Amostra; 40 convidados; recepção 18h; jantar 19h; data e orçamento: [NÃO INFORMADO].
Escopo e requisitos: bufê; 3 pessoas alérgicas a amendoim; montagem 15h–17h; retirada 22h–23h; demais dietas, detalhamento técnico, carga e desmontagem: [NÃO INFORMADO].
Restrições do local: planejar cozinha apenas para finalização e entrada de carga pela porta lateral; explicar como atenderá às condições.
Formato de preço: linhas próprias por serviço, equipamento, mão de obra, frete/entrega, montagem e desmontagem cobradas, taxa de serviço, impostos e gorjeta; quantidade, unidade, preço unitário e total; mostrar contas e indicar rubricas sem cobrança; preços: A preencher pelo fornecedor.
Documentos exigidos do fornecedor: certificado de seguro; condições de sinal e pagamento; cancelamento e reembolso; validade; confirmação cadastral aplicável; procedimento escrito de manejo de alérgenos e prevenção de contato cruzado.
Cronograma e avaliação: resposta e decisão: [NÃO INFORMADO]. Critérios de avaliação propostos — confirmar com o cliente antes do envio: atendimento ao escopo; preço discriminado claro e completo; plano para cozinha, acesso e alergia; seguro e condições comerciais. Anonimize dados e use ferramenta aprovada pelo escritório. O profissional responsável confere as regras aplicáveis.
Pendências (a confirmar): quais são a data, organizadora, contato, orçamento, emissão e referência, detalhamento técnico, demais dietas, janelas de carga e desmontagem, prazo de resposta e data de decisão? O cliente confirma os critérios propostos antes do envio?
```
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

## Cabeçalho do pedido de proposta
Pedido de proposta — convenção anual — Associação Exemplo (fictícia)
Organizadora: [NÃO INFORMADO] | Destinatário: fornecedor de audiovisual
Contato para resposta: [NÃO INFORMADO] | Emissão e referência: [NÃO INFORMADO]

## Visão geral do evento
Cliente: Associação Exemplo (fictícia) | Data: 17 de abril de 2027 | Local: Centro de Convenções Amostra, Rio de Janeiro (fictício)
Convidados: 400, em auditório
Cronograma: programação 09:00–18:00 (abertura, 5 palestras, vídeo de 4 minutos, cerimônia de premiação); montagem a partir das 06:00; desmontagem concluída até 02:00
Horário de recepção e horário de serviço/encerramento do evento (se distintos do início/fim da programação): [NÃO INFORMADO]
Orçamento: [NÃO INFORMADO]

## Escopo e requisitos
- Palco: 10 m x 6 m x 0,8 m
- Telões: 2 unidades
- Microfones sem fio de mão: 6 unidades
- Microfones de lapela: 3 unidades
- Monitor de retorno para os palestrantes (quantidade exata não especificada — ver pendências)
- Transmissão ao vivo: somente das 5 palestras; a cerimônia de premiação não deve ser transmitida
- Conteúdo de vídeo a exibir: 1 vídeo, 4 minutos

Dietas e alergias: [NÃO INFORMADO — não informado se aplicável a fornecimento de audiovisual; confirmar com o cliente]

Carga e montagem: montagem a partir das 06:00; janela específica de entrada de carga (load-in) não informada separadamente do início da montagem
Desmontagem e retirada: desmontagem concluída até 02:00; janela específica de retirada de equipamentos não detalhada além desse horário-limite

Cálculos necessários:
- Duração da programação: 18:00 − 09:00 = 9 horas (dado informativo, derivado diretamente dos horários recebidos).
- Janela de montagem: início 06:00; término não informado, portanto duração total de montagem = [NÃO INFORMADO] (falta horário de término da montagem para calcular).
- Janela de desmontagem: término 02:00; início não informado, portanto duração total de desmontagem = [NÃO INFORMADO] (falta horário de início da desmontagem para calcular).

## Restrições do local
- O local exige que qualquer içamento (rigging) seja realizado pela própria equipe de rigging do espaço; o fornecedor não deve prever içamento com equipe própria.
- Estruturas e pontos de suspensão do espaço disponíveis para telões, PA e demais equipamentos: [NÃO INFORMADO]
- Capacidade e pontos de energia disponíveis no local: [NÃO INFORMADO]
- Condições de acesso (dimensões de portas, docas, elevador de carga) para entrada de equipamentos: [NÃO INFORMADO]

O fornecedor deve explicar como atenderá a cada condição listada acima, incluindo o plano de coordenação com a equipe de rigging do local, sem pressupor capacidades de energia, estrutura ou acesso não informadas.

## Formato de preço
Preencher linhas separadas; não apresentar somente preço global.

| Item | Quantidade | Unidade | Preço unitário | Total |
|---|---|---|---|---|
| Palco (10 m x 6 m x 0,8 m) | 1 | unidade | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Telão | 2 | unidade | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Microfone sem fio de mão | 6 | unidade | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Microfone de lapela | 3 | unidade | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Monitor de retorno para palestrantes | [NÃO INFORMADO — quantidade a confirmar] | unidade | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Transmissão ao vivo (somente das palestras) | 1 | serviço | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Exibição de vídeo (4 minutos) | 1 | serviço | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Mão de obra | | | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Frete/entrega | | | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Montagem, se cobrada | | | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Desmontagem, se cobrada | | | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Taxa de serviço | | | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Impostos | | | A preencher pelo fornecedor | A preencher pelo fornecedor |
| Gorjeta | | | A preencher pelo fornecedor | A preencher pelo fornecedor |

Indicar expressamente qualquer rubrica sem cobrança (ex.: montagem ou desmontagem incluídas sem custo adicional) e demonstrar a conta dos totais (soma de todas as linhas, com indicação separada de impostos e taxas).

## Documentos exigidos do fornecedor
- Certificado de seguro
- Condições de sinal e pagamento
- Política de cancelamento e reembolso
- Validade da proposta
- Confirmar a situação cadastral aplicável à atividade do fornecedor de audiovisual

## Cronograma e avaliação
Prazo de resposta: 01/02/2027 | Data de decisão: 12/02/2027

Critérios de avaliação propostos — confirmar com o cliente antes do envio:
- Atendimento aos requisitos técnicos informados (palco, telões, microfonia, monitor de retorno, transmissão ao vivo das palestras)
- Clareza e completude do preço discriminado
- Experiência e referências em eventos comparáveis de audiovisual para convenções/auditórios de porte similar
- Plano operacional para as restrições do local, incluindo coordenação com a equipe de rigging do espaço
- Seguro e condições comerciais

Lembrete: anonimize os dados e use apenas ferramenta aprovada pelo escritório.
O profissional responsável confere as regras aplicáveis.

## Pendências (a confirmar)
- Nome da organizadora do evento: [NÃO INFORMADO]
- Contato para resposta (nome, e-mail/telefone): [NÃO INFORMADO]
- Dados de emissão e número de referência do pedido de proposta: [NÃO INFORMADO]
- Orçamento disponível: [NÃO INFORMADO]
- Horário de recepção e horário de encerramento do evento, se distintos do início (09:00) e fim (18:00) da programação: confirmar
- Horário de término da montagem (para calcular a duração total da janela de montagem, que começa às 06:00): confirmar
- Horário de início da desmontagem (para calcular a duração total da janela de desmontagem, que termina às 02:00): confirmar
- Janela específica de entrada de carga (load-in), se distinta do início da montagem: confirmar
- Estruturas e pontos de suspensão disponíveis no local para telões e demais equipamentos: confirmar
- Capacidade e pontos de energia disponíveis no local: confirmar
- Condições de acesso (dimensões de portas, docas, elevador de carga) para entrada de equipamentos: confirmar
- Quantidade exata de monitores de retorno necessários (um único monitor compartilhado ou um por palestrante): confirmar
- Se a seção "dietas e alergias" é aplicável a este fornecedor de audiovisual ou pode ser suprimida: confirmar
- Confirmar com o cliente os critérios de avaliação propostos antes do envio ao fornecedor

