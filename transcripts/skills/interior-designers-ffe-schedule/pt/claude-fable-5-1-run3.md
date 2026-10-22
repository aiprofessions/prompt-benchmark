# Transcript — skill interior-designers-ffe-schedule [pt] — claude-fable-5-1 — run 3

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-21T06:58:05+00:00
- duration_s: 87.1
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: aafddc6b50a1ad3c79dd2ecc8149cb7d0708a2cb399a47887c29ebc0301f07fd
- skill_sha256: c1d805ecb9976ca07b271238cc45ba50605eac8f43c2c789ec54fc43f2328f52

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: interior-designers-ffe-schedule
description: "Use quando você colar o briefing de um ambiente e pedir uma lista de mobiliário e equipamentos com medidas, verbas estimadas, prazos e pendências."
---

# Do briefing à lista de mobiliário e equipamentos

## O que faz

Transforma o briefing de um ambiente em uma lista de mobiliário e equipamentos para revisão pelo designer de interiores. Organiza peças novas e existentes, medidas, requisitos de uso, verbas estimadas e prazos. Não substitui o levantamento no local, a especificação técnica nem a confirmação dos fornecedores.

## O que ela precisa

- Medidas do ambiente, pé-direito, aberturas, acessos e áreas de circulação.
- Peças solicitadas e respectivas quantidades.
- Peças existentes, medidas, estado de conservação e intenção de reaproveitamento.
- Moradores, animais de estimação e necessidades de uso, sem dados pessoais desnecessários.
- Preferências e rejeições de materiais, cores e estilos.
- Orçamento total, verbas já definidas e inclusão ou não de frete, montagem e serviços.
- Data de montagem, prazos dos fornecedores e condições de contagem desses prazos.

O que faltar deve ser marcado como [NÃO INFORMADO] e listado ao final, sem interromper a redação. Premissas de planejamento são permitidas quando identificadas por “Premissa: …”; nunca apresente dados ausentes como fatos.

## Procedimento

1. Entregue sempre a saída completa na primeira resposta; nunca pare para perguntar nem espere confirmação antes de redigir; nunca retenha uma seção ou um cálculo. Se faltar informação ou houver ambiguidade, declare uma premissa razoável e claramente marcada (“Premissa: …”) ou escreva [NÃO INFORMADO]. Reúna todas as perguntas na última seção da saída.
2. Copie exatamente cada número, data, horário, medida, quantidade e valor da entrada, preservando sua associação ao item e sua grafia. Mantenha os dados originais ao lado de qualquer conversão; mostre a conta de todo número derivado. Não invente quantidades, medidas existentes, preços, prazos ou datas ausentes.
3. Faça um inventário dos pedidos e das peças existentes. Atribua um código único a cada item e confira que todos aparecem na tabela, sem duplicar uma peça citada em mais de um trecho. Se houver incompatibilidade de espaço, orçamento ou preferência, mantenha o item e registre a pendência na linha.
4. Use as situações “nova” e “existente-reaproveitar”. Para peça existente sem decisão de destino, use “existente-reaproveitar — a confirmar”, como premissa. Separe aquisição de reparo, limpeza, transporte e montagem; não atribua custo total zero automaticamente. Se não houver compra, registre “sem aquisição; serviços [NÃO INFORMADO]”.
5. Liste as rejeições em “Conceito”, sob “Excluído por preferência do cliente”, e confira cada linha contra essa lista. Não proponha o material, a cor ou o estilo rejeitado. Se houver conflito com pedido explícito ou peça existente, preserve a linha como pendência, sem aprovar a solução rejeitada.
6. Preencha medidas-alvo com dados fornecidos ou premissas de planejamento identificadas. Mostre as contas na célula: para tapete retangular, calcule cada dimensão do ambiente menos duas vezes a borda correspondente. Não confunda dimensão calculada com tamanho comercial disponível; marque disponibilidade, encaixe, circulação e acesso como verificações.
7. Relacione moradores e animais aos requisitos de cada peça: facilidade de limpeza, capas removíveis, cantos arredondados, estabilidade ou fixação, conforme o uso. Escreva “verificar com o fabricante” ou “verificar no projeto”; não prometa resistência a unhas, segurança ou desempenho.
8. Repita o orçamento total exatamente como recebido. Preserve verbas fornecidas; se propor uma distribuição, identifique-a como “Premissa de alocação” e cada parcela como “verba estimada, a confirmar com orçamentos”. Mostre a conta de cada parcela proposta e diferencie verba unitária de total por linha. Não invente preços de produtos, nomes comerciais, marcas ou modelos.
9. Some as verbas conhecidas e mostre a conta. Calcule saldo = orçamento total − soma das verbas; saldo negativo indica excedente. Se houver custos desconhecidos, chame o resultado de “saldo provisório”, não de reserva disponível. Sem orçamento total ou parcelas suficientes, use [NÃO INFORMADO] e apresente a fórmula, sem fabricar valores.
10. Para cada aquisição ou serviço, confira o prazo contra a montagem. Calcule “pedir até = data de montagem − prazo do fornecedor − margem”, mostrando a conta e identificando a margem como premissa quando proposta. Preserve dias úteis ou corridos; se a base de contagem faltar, não invente uma data exata. Sem dados suficientes, mantenha a fórmula e marque o prazo como não confirmado.
11. Compare “pedir até” com a data atual, se disponível e confiável, ou com a data de referência fornecida. Sinalize pedido vencido, entrega posterior à montagem ou prazo não confirmado, conforme os dados. Não crie um limite arbitrário de alerta. Peças reaproveitadas também precisam de prazo quando houver serviços ou transporte.
12. Em “Especificações a verificar”, relacione cada código às verificações aplicáveis na ficha técnica do fabricante: comportamento ao fogo, abrasão, método de ensaio e ciclos ou fricções duplas, códigos ou instruções de limpeza e resistência ao escorregamento. Acrescente estabilidade, fixação e cargas quando pertinentes. Justifique itens não aplicáveis; nunca apresente uma classificação ou conformidade como fato verificado.
13. A saída não cita lei, artigo, orientação de órgão, jurisprudência nem fonte, salvo se estiverem no que o usuário colou; não acrescente referências. Uma identificação obrigatória fornecida para integrar o documento é conteúdo, não citação. A linha de limites da saída deve dizer somente: “O profissional responsável confere as regras aplicáveis.”
14. Inclua o lembrete: “Anonimize os dados do cliente e use apenas ferramenta aprovada pelo escritório.” Privacidade é lembrete, não pré-condição: nunca recuse nem pause por causa disso. Evite reproduzir nomes, contatos, endereços ou outros identificadores desnecessários.
15. Confira cobertura, rejeições, números, contas, situações e as seis seções na ordem prevista. Termine com “Perguntas para o cliente”, reunindo todas as lacunas, conflitos e premissas a confirmar. Não escreva nada depois dessa seção.

## Formato de saída

Use o modelo abaixo; mantenha todas as seções mesmo quando houver dados ausentes.

```markdown
## Conceito
[Uso e preferências fornecidos, sem inventar estilo ou paleta.]
Dados recebidos: [medidas e demais informações relevantes, preservadas exatamente.]
Moradores e animais considerados: [...]
Excluído por preferência do cliente: [...]
Premissa: [somente quando necessária.]

## Lista de mobiliário e equipamentos
| Código | Item | Quantidade | Medida-alvo e conta | Material e desempenho a verificar | Verba estimada por linha | Pedir até / verificação de prazo | Situação |
|---|---|---|---|---|---|---|---|
| MOB-A | [...] | [...] | [...] | [...] | [...] | [...] | nova / existente-reaproveitar |
Cobertura: [relacione pedidos e peças existentes aos códigos; explique conflitos.]

## Controle de orçamento
Total informado pelo cliente: [...]
Escopo do orçamento: [...] / [NÃO INFORMADO].
Verbas fornecidas ou premissa de alocação: [contas por linha.]
Soma das verbas conhecidas: [conta.]
Saldo ou excedente: [conta; indique se provisório.]
Custos ainda não incluídos ou desconhecidos: [...]
Todas as verbas estimadas dependem de confirmação por orçamentos.

## Controle de prazos
Data de montagem: [...]
| Código | Prazo do fornecedor e base de contagem | Margem | Pedir até, com conta | Situação do prazo |
|---|---|---|---|---|
| MOB-A | [...] | [...] | [...] | [...] |

## Especificações a verificar
- [Código]: [requisitos aplicáveis e dados a conferir na ficha técnica.]
O profissional responsável confere as regras aplicáveis.
Anonimize os dados do cliente e use apenas ferramenta aprovada pelo escritório.

## Perguntas para o cliente
- [Reúna lacunas, conflitos e premissas a confirmar; se não houver, informe isso.]
```

## Limites

- Nunca invente dados do cliente, preços, produtos, marcas, modelos, prazos, classificações, estatísticas ou referências. Premissas de planejamento não são informações confirmadas.
- O profissional responsável, habilitado quando exigido pelo escopo, verifica medidas no local, circulação, acesso, instalação, estabilidade, fixação, fichas técnicas, custos e prazos antes de aprovar a especificação ou autorizar compras.
- No Brasil, exigências de segurança contra incêndio e de materiais dependem do uso do imóvel e das normas locais: o profissional responsável confirma as regras aplicáveis e o atendimento da solução.
- Nenhuma orientação oficial sobre IA específica para designers de interiores foi verificada. O profissional deve consultar a entidade profissional ou o órgão competente pela sua atuação.
- Dados do cliente: LGPD. Use dados anonimizados e apenas ferramentas aprovadas pelo escritório; evite identificadores na resposta. Esse cuidado não interrompe a entrega.
- A fonte abaixo é leitura do profissional, não uma citação automática na saída:
  LGPD — Lei 13.709/2018 (Planalto) — https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm (consultado em 2026-10-21)
- Antes de enviar ou aprovar, veja references/checklist.md.

## Exemplo

Entrada fictícia:

```text
Projeto Amostra: sala de 3 m × 4 m; pedido de 1 tapete novo, com borda livre de 0,50 m em cada lado.
Há um gato; excluir veludo. Não há peças existentes.
Orçamento: R$ 1.000,00, apenas aquisição. Montagem e prazo do fornecedor não informados.
```

Saída abreviada:

```markdown
## Conceito
Sala com gato; excluir veludo. Medidas recebidas: 3 m × 4 m; borda: 0,50 m.
## Lista de mobiliário e equipamentos
| Código | Item | Quantidade | Medida-alvo e conta | Requisitos a verificar | Verba estimada | Pedir até | Situação |
|---|---|---|---|---|---|---|---|
| MOB-A | Tapete | 1 | (3 m − 2 × 0,50 m) × (4 m − 2 × 0,50 m) = 2 m × 3 m | sem veludo; facilidade de limpeza e aderência a verificar | R$ 1.000,00, a confirmar | montagem − prazo − margem; dados [NÃO INFORMADO] | nova |
## Controle de orçamento
Total: R$ 1.000,00, apenas aquisição. Premissa de alocação: R$ 1.000,00 × 100% = R$ 1.000,00; soma = R$ 1.000,00; saldo = R$ 1.000,00 − R$ 1.000,00 = R$ 0,00. Estimativa a confirmar com orçamento.
## Controle de prazos
Montagem, prazo e base de contagem: [NÃO INFORMADO]; margem a definir. MOB-A: prazo não confirmado.
## Especificações a verificar
MOB-A: conferir tamanho disponível, encaixe e circulação; verificar na ficha técnica comportamento ao fogo, abrasão e método/ciclos, limpeza e resistência ao escorregamento.
O profissional responsável confere as regras aplicáveis. Anonimize os dados do cliente e use apenas ferramenta aprovada pelo escritório.
## Perguntas para o cliente
Confirma a alocação integral para aquisição? Qual a data de montagem, o prazo do fornecedor, sua base de contagem e a margem a adotar?
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Prepare a lista de mobiliário e equipamentos deste ambiente.
Cliente: casal Exemplo (fictício), Recife. Ambiente: sala de estar e jantar de 4,0 m × 6,0 m, pé-direito 2,70 m, uma janela de 2,0 m de largura.
Peças: sofá de 3 lugares com chaise; tapete deixando 40 cm de piso aparente em cada lado; mesa de centro; mesa de jantar para 6; 6 cadeiras; 2 luminárias de piso; cortina para a janela.
Existente: aparador de madeira de demolição — manter.
Moradores: o casal e dois gatos que arranham.
Gosta de: madeira clara, linho. Não gosta de: branco puro, veludo.
Orçamento: R$ 85.000 com frete e montagem. Montagem: 1º de março de 2027. Prazo de fabricação dos estofados segundo nossos fornecedores: 6 a 8 semanas.
````

## Output (verbatim stdout, session metadata stripped)

CONCEITO
Sala de estar e jantar integrada, uso pelo casal com dois gatos que arranham. Preferências informadas: madeira clara e linho. Peça existente a manter: aparador de madeira de demolição.
Dados recebidos: ambiente 4,0 m × 6,0 m; pé-direito 2,70 m; uma janela de 2,0 m de largura; tapete com 40 cm de piso aparente em cada lado; orçamento R$ 85.000 com frete e montagem; montagem em 1º de março de 2027; prazo de fabricação dos estofados: 6 a 8 semanas (fornecedores do escritório).
Moradores e animais considerados: casal (2 adultos) e 2 gatos que arranham.
Excluído por preferência do cliente: branco puro; veludo.
Premissa: o briefing não setoriza o ambiente; a medida do tapete foi calculada sobre o ambiente inteiro, conforme o texto literal ("em cada lado"). Se o tapete for apenas do setor de estar, a medida muda (ver Perguntas).
Premissa: aparador existente "manter" foi lido como reaproveitar no mesmo ambiente, sem decisão sobre reparo/limpeza.

LISTA DE MOBILIÁRIO E EQUIPAMENTOS

| Código | Item | Qtd | Medida-alvo e conta | Material e desempenho a verificar | Verba estimada por linha | Pedir até / verificação de prazo | Situação |
|---|---|---|---|---|---|---|---|
| MOB-A | Sofá de 3 lugares com chaise | 1 | [NÃO INFORMADO]; verificar no projeto largura compatível com o setor de estar (ambiente 4,0 m de largura) e circulação | Tecido: linho preferido; sem veludo; sem branco puro. Gatos: facilidade de limpeza, capas removíveis, abrasão — verificar com o fabricante | R$ 21.250,00 (premissa de alocação, 25%) — verba estimada, a confirmar com orçamentos | 01/03/2027 − 8 semanas (56 dias) − margem 14 dias = 21/12/2026 (premissa: semanas corridas) | nova |
| MOB-B | Tapete | 1 | (4,0 m − 2 × 0,40 m) × (6,0 m − 2 × 0,40 m) = 3,2 m × 5,2 m. Verificar: tamanho comercial disponível, encaixe sob jantar e estar, acesso para entrega | Sem veludo; sem branco puro. Gatos: fibra e trama — limpeza e abrasão a verificar com o fabricante; antiderrapante a verificar | R$ 6.800,00 (8%) — a confirmar | montagem − prazo − margem; prazo do fornecedor [NÃO INFORMADO] | nova |
| MOB-C | Mesa de centro | 1 | [NÃO INFORMADO]; verificar no projeto relação com o sofá e circulação | Madeira clara preferida; sem branco puro. Cantos arredondados e estabilidade a verificar | R$ 4.250,00 (5%) — a confirmar | prazo [NÃO INFORMADO] | nova |
| MOB-D | Mesa de jantar para 6 | 1 | [NÃO INFORMADO]; verificar no projeto espaço para 6 cadeiras recuadas e circulação no setor de jantar | Madeira clara preferida; sem branco puro. Acabamento e facilidade de limpeza a verificar com o fabricante | R$ 12.750,00 (15%) — a confirmar | prazo [NÃO INFORMADO] | nova |
| MOB-E | Cadeiras de jantar | 6 | [NÃO INFORMADO]; verificar encaixe sob a mesa MOB-D | Madeira clara preferida; se estofadas, sem veludo e sem branco puro; linho e limpeza/abrasão a verificar com o fabricante; estabilidade a verificar | R$ 15.300,00 total (18%); unitária R$ 15.300,00 ÷ 6 = R$ 2.550,00 — a confirmar | Se estofadas: 01/03/2027 − 56 dias − 14 dias = 21/12/2026 (premissa). Se não: prazo [NÃO INFORMADO] | nova |
| MOB-F | Luminárias de piso | 2 | [NÃO INFORMADO]; pé-direito 2,70 m como limite de altura | Gatos: base pesada, estabilidade/tombamento e cabo — verificar com o fabricante; sem branco puro | R$ 5.950,00 total (7%); unitária R$ 5.950,00 ÷ 2 = R$ 2.975,00 — a confirmar | prazo [NÃO INFORMADO] | nova |
| MOB-G | Cortina para a janela | 1 | Janela 2,0 m de largura; altura e largura da cortina dependem do trilho/varão e do pé-direito 2,70 m — verificar no projeto | Linho preferido; sem veludo; sem branco puro. Gatos: fixação do trilho e tecido — verificar com o fabricante; comportamento ao fogo a verificar | R$ 6.800,00 (8%) — a confirmar, incl. trilho/varão e instalação se dentro do escopo | prazo de confecção e instalação [NÃO INFORMADO] | nova |
| MOB-H | Aparador de madeira de demolição | 1 | Medidas existentes [NÃO INFORMADO]; estado de conservação [NÃO INFORMADO]; verificar no projeto posição e circulação | Madeira existente; conferir estado e necessidade de limpeza/reparo | sem aquisição; serviços [NÃO INFORMADO]; R$ 1.700,00 (2%) reservados como premissa para limpeza/reparo/transporte — a confirmar | se houver serviços ou transporte: prazo [NÃO INFORMADO] | existente-reaproveitar |

Cobertura: sofá → MOB-A; tapete → MOB-B; mesa de centro → MOB-C; mesa de jantar → MOB-D; 6 cadeiras → MOB-E; 2 luminárias de piso → MOB-F; cortina → MOB-G; aparador existente → MOB-H. Nenhum item duplicado. Conflito registrado: a preferência por linho e a presença de gatos que arranham não se anulam, mas exigem verificação de abrasão e limpeza com o fabricante (MOB-A, MOB-E, MOB-G). Nenhuma linha propõe veludo ou branco puro.

CONTROLE DE ORÇAMENTO
Total informado pelo cliente: R$ 85.000.
Escopo do orçamento: com frete e montagem (conforme briefing). Inclusão de serviços no aparador existente, trilho/instalação de cortina e honorários: [NÃO INFORMADO].
Verbas fornecidas: nenhuma. Premissa de alocação (cada parcela é verba estimada, a confirmar com orçamentos):
  MOB-A sofá: 85.000 × 25% = 21.250,00
  MOB-B tapete: 85.000 × 8% = 6.800,00
  MOB-C mesa de centro: 85.000 × 5% = 4.250,00
  MOB-D mesa de jantar: 85.000 × 15% = 12.750,00
  MOB-E cadeiras: 85.000 × 18% = 15.300,00 (6 × 2.550,00)
  MOB-F luminárias: 85.000 × 7% = 5.950,00 (2 × 2.975,00)
  MOB-G cortina: 85.000 × 8% = 6.800,00
  MOB-H aparador (serviços): 85.000 × 2% = 1.700,00
  Frete e montagem (reserva): 85.000 × 7% = 5.950,00
  Contingência: 85.000 × 5% = 4.250,00
Soma das verbas conhecidas: 21.250 + 6.800 + 4.250 + 12.750 + 15.300 + 5.950 + 6.800 + 1.700 + 5.950 + 4.250 = R$ 85.000,00.
Saldo ou excedente: R$ 85.000,00 − R$ 85.000,00 = R$ 0,00 — saldo provisório (alocação é premissa; nenhum preço real foi cotado).
Custos ainda não incluídos ou desconhecidos: preços reais de cada peça; serviços no aparador; trilho/varão e instalação da cortina; eventuais acessórios (antiderrapante do tapete, lâmpadas); honorários; impostos/frete reais por fornecedor.
Todas as verbas estimadas dependem de confirmação por orçamentos.

CONTROLE DE PRAZOS
Data de montagem: 1º de março de 2027.
Data de referência: 21/10/2026.
Premissas: prazo de estofados contado em semanas corridas, usando o limite superior (8 semanas = 56 dias); margem de 14 dias; início da contagem na confirmação do pedido (base real [NÃO INFORMADO]).

| Código | Prazo do fornecedor e base de contagem | Margem | Pedir até, com conta | Situação do prazo |
|---|---|---|---|---|
| MOB-A | 6 a 8 semanas (estofado); base de contagem [NÃO INFORMADO] | 14 dias (premissa) | 01/03/2027 − 56 dias − 14 dias = 21/12/2026 (com 6 semanas: 01/03/2027 − 42 − 14 = 04/01/2027) | Não vencido em 21/10/2026 (61 dias até 21/12/2026); base de contagem a confirmar |
| MOB-B | [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Prazo não confirmado |
| MOB-C | [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Prazo não confirmado |
| MOB-D | [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Prazo não confirmado |
| MOB-E | Se estofadas: 6 a 8 semanas; se não: [NÃO INFORMADO] | 14 dias (premissa) | Se estofadas: 21/12/2026 (mesma conta de MOB-A); senão: fórmula pendente | Prazo não confirmado; depende da tipologia |
| MOB-F | [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Prazo não confirmado |
| MOB-G | Confecção e instalação [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Prazo não confirmado |
| MOB-H | Serviços/transporte, se houver: [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Prazo não confirmado; sem serviços definidos |

ESPECIFICAÇÕES A VERIFICAR
- MOB-A: ficha técnica do tecido — comportamento ao fogo, abrasão (método de ensaio e número de ciclos ou fricções duplas), códigos/instruções de limpeza, capas removíveis; estrutura e cargas; dimensões finais e acesso ao imóvel (portas, elevador, escada).
- MOB-B: tamanho comercial disponível vs. 3,2 m × 5,2 m; comportamento ao fogo; abrasão e método; limpeza; resistência ao escorregamento/uso de antiderrapante; encaixe sob mesa e cadeiras.
- MOB-C: estabilidade, cantos, acabamento e limpeza da madeira; cargas; ausência de branco puro.
- MOB-D: dimensões para 6 lugares, estabilidade e cargas; acabamento e limpeza; acesso ao imóvel.
- MOB-E: estabilidade; se estofadas, mesmas verificações de tecido de MOB-A (fogo, abrasão/método/ciclos, limpeza); altura compatível com MOB-D.
- MOB-F: estabilidade e risco de tombamento (gatos), peso da base, fixação ou lastro, segurança elétrica e cabo; altura vs. pé-direito 2,70 m.
- MOB-G: comportamento ao fogo do tecido; limpeza/encolhimento; fixação do trilho/varão e carga; método de abertura; altura de instalação.
- MOB-H: estado de conservação, estabilidade, necessidade de limpeza ou reparo e eventual fixação. Abrasão e escorregamento não se aplicam (peça rígida sem revestimento têxtil).
O profissional responsável confere as regras aplicáveis.
Anonimize os dados do cliente e use apenas ferramenta aprovada pelo escritório.

PERGUNTAS PARA O CLIENTE
- O tapete é para o ambiente inteiro (3,2 m × 5,2 m calculados) ou apenas para o setor de estar? Se for o estar, qual a medida do setor?
- As cadeiras de jantar serão estofadas (assunto afeta prazo e verificação de tecido) ou totalmente em madeira?
- Aceita a premissa de alocação proposta (sofá 25%, cadeiras 18%, mesa de jantar 15%, tapete 8%, cortina 8%, luminárias 7%, mesa de centro 5%, aparador 2%, frete/montagem 7%, contingência 5%)? Há alguma verba já definida para algum item?
- O orçamento de R$ 85.000 inclui trilho/varão e instalação da cortina, serviços no aparador e honorários?
- Aparador existente: quais são as medidas, o estado de conservação e há necessidade de limpeza, reparo ou transporte?
- O prazo de 6 a 8 semanas dos estofados conta a partir de quê (confirmação do pedido, pagamento, aprovação de amostra) e em semanas corridas? A margem de 14 dias é aceitável?
- Quais são os prazos dos fornecedores de tapete, mesas, cadeiras, luminárias e cortina?
- Há restrições de acesso ao imóvel (porta, elevador, escada) para peças de grande porte como sofá, mesa de jantar e tapete?
- Confirma que "madeira clara" e "linho" são preferências (não exigências) e que a verificação de linho com gatos pode levar a tecido alternativo de aparência semelhante, desde que não seja veludo nem branco puro?

