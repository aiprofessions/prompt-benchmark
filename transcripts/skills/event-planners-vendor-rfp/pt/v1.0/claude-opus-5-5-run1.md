# Transcript — skill event-planners-vendor-rfp [pt] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T05:56:39+00:00
- duration_s: 47.8
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

Cabeçalho do pedido de proposta

  Pedido de proposta — convenção anual — Associação Exemplo (fictícia)
  Organizadora: [NÃO INFORMADO] | Destinatário: fornecedor de audiovisual
  Contato para resposta: [NÃO INFORMADO] | Emissão e referência: [NÃO INFORMADO]


Visão geral do evento

  Cliente: Associação Exemplo (fictícia)
  Data: 17 de abril de 2027
  Local: Centro de Convenções Amostra, Rio de Janeiro (fictício)
  Participantes: 400 em auditório
  Cronograma: programação 09:00–18:00: abertura, 5 palestras, um vídeo de 4 minutos e cerimônia de premiação
    Horários de cada bloco (abertura, palestras, vídeo, premiação): [NÃO INFORMADO]
  Orçamento: [NÃO INFORMADO]


Escopo e requisitos

  Itens solicitados (quantidades e medidas conforme recebidas):
    - Palco de 10 m x 6 m x 0,8 m
    - 2 telões (dimensões, tecnologia, resolução e posicionamento: [NÃO INFORMADO])
    - 6 microfones sem fio de mão
    - 3 microfones de lapela
    - Monitor de retorno para os palestrantes (tipo e quantidade: [NÃO INFORMADO])
    - Transmissão ao vivo só das palestras (não da premiação)
      Plataforma, destino, formato e inclusão ou não da abertura e do vídeo: [NÃO INFORMADO]
    - Reprodução do vídeo de 4 minutos (formato do arquivo e responsável pela entrega: [NÃO INFORMADO])
  Sistema de sonorização (PA), iluminação, operação técnica e equipe em cabine: [NÃO INFORMADO]

  Dietas e alergias: [NÃO INFORMADO]. Premissa: tema não tratado neste pedido por se tratar de fornecimento de audiovisual.

  Carga e montagem: montagem a partir das 06:00 | janela de entrada de carga: [NÃO INFORMADO]
  Desmontagem e retirada: desmontagem concluída até 02:00 | janela de retirada: [NÃO INFORMADO]

  Cálculos:
    - Total de microfones sem fio: 6 de mão + 3 de lapela = 9 microfones
    - Área do palco: 10 m x 6 m = 60 m² (altura 0,8 m)
    - Duração da programação: 18:00 − 09:00 = 9 horas
    - Tempo entre o início da montagem e o início da programação: 09:00 − 06:00 = 3 horas,
      desde que a montagem ocorra em 17/04/2027. A data da montagem não foi informada.
    - Tempo para desmontagem: se 02:00 se referir à madrugada de 18/04/2027,
      de 18:00 a 02:00 = 8 horas. A data não foi informada; cálculo condicionado à confirmação.


Restrições do local

  Condição obrigatória de planejamento:
    - O local exige a própria equipe de rigging para qualquer içamento.
      Toda estrutura, telão, sistema de som ou iluminação que precise ser suspenso deverá
      considerar essa equipe do local.
  Pontos de suspensão, capacidade de carga, energia disponível, acessos, elevadores de carga
  e docas: [NÃO INFORMADO]

  O fornecedor deve explicar como atenderá a cada condição, sem pressupor capacidades não
  informadas, e indicar quais itens da proposta dependem de içamento.


Formato de preço

  Preencher linhas separadas; não apresentar somente preço global.
  Colunas: Item | Quantidade | Unidade | Preço unitário | Total
  Preços: A preencher pelo fornecedor.

    Palco 10 m x 6 m x 0,8 m
    Telão (2)
    Microfone sem fio de mão (6)
    Microfone de lapela (3)
    Monitor de retorno para palestrantes
    Transmissão ao vivo das palestras
    Reprodução do vídeo de 4 minutos
    Cada equipamento adicional proposto, em linha própria
    Mão de obra (técnicos e operadores)
    Frete/entrega
    Montagem, se cobrada
    Desmontagem, se cobrada
    Coordenação com a equipe de rigging do local, se cobrada
    Taxa de serviço
    Impostos
    Gorjeta

  Indicar expressamente rubricas sem cobrança e mostrar a conta dos totais
  (quantidade x preço unitário por linha e soma das linhas no total geral).


Documentos exigidos do fornecedor

  - Certificado de seguro
  - Condições de sinal e pagamento
  - Política de cancelamento e reembolso
  - Validade da proposta
  - Confirmação da situação cadastral aplicável à atividade do fornecedor


Cronograma e avaliação

  Prazo de resposta: propostas até 01/02/2027
  Data de decisão: 12/02/2027
  Critérios de avaliação: [NÃO INFORMADO]

  Lembrete: anonimize os dados e use apenas ferramenta aprovada pelo escritório.
  O profissional responsável confere as regras aplicáveis.


Pendências (a confirmar)

  Dados ausentes:
    1. Organizadora: qual o nome?
    2. Contato para resposta: qual o nome, e-mail ou telefone?
    3. Emissão e referência: há data de emissão e código do pedido?
    4. Orçamento: há valor de referência?
    5. Horários de cada bloco da programação: quais são?
    6. Telões: quais as dimensões, a tecnologia (projeção ou LED), a resolução e o posicionamento?
    7. Monitor de retorno: é retorno de áudio ou monitor de vídeo para os palestrantes? Qual a quantidade?
    8. Transmissão ao vivo: qual a plataforma, o destino e o formato? A abertura e o vídeo de 4 minutos entram na transmissão?
    9. Vídeo de 4 minutos: qual o formato do arquivo e quem o fornece?
    10. Sonorização, iluminação e operação técnica: fazem parte do escopo?
    11. Entrada de carga e retirada: quais são as janelas?
    12. Espaço: quais os pontos de suspensão, a capacidade de carga, a energia disponível e os acessos?
    13. Critérios de avaliação: quais serão usados?

  Ambiguidades:
    14. Montagem a partir das 06:00: ocorre em 17/04/2027 ou em data anterior?
    15. Desmontagem concluída até 02:00: refere-se a 18/04/2027?
    16. Palco 10 m x 6 m x 0,8 m: faz parte do escopo do fornecedor de audiovisual ou será contratado à parte?
    17. Rigging do local: o custo da equipe é contratado e pago pelo fornecedor, pela organizadora ou pelo cliente?

  Premissas para confirmação:
    18. Dietas e alergias ficaram fora deste pedido por se tratar de audiovisual. Confirmar se há algo a incluir.
    19. Foi incluída uma linha de preço para coordenação com a equipe de rigging do local, a ser marcada como sem cobrança se não for aplicável.
    20. Os cálculos de 3 horas e 8 horas dependem das confirmações dos itens 14 e 15.

