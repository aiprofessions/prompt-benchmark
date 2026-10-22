# Transcript — skill interior-designers-ffe-schedule [pt] — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:13:36+00:00
- duration_s: 179.2
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

Ambiente: sala de estar e jantar integrada, 4,0 m × 6,0 m, pé-direito 2,70 m, uma janela de 2,0 m de largura.
Peças solicitadas: sofá de 3 lugares com chaise; tapete com 40 cm de piso aparente em cada lado; mesa de centro; mesa de jantar para 6; 6 cadeiras; 2 luminárias de piso; cortina para a janela.
Peça existente: aparador de madeira de demolição — decisão do cliente: manter.
Moradores e animais considerados: casal e dois gatos que arranham — requisitos de resistência a arranhões, limpeza e estabilidade aplicam-se a estofados, tapete e tecidos.
Preferências: madeira clara, linho.
Excluído por preferência do cliente: branco puro, veludo. Nenhum item desta lista especifica branco puro ou veludo.
Dados recebidos, preservados: 4,0 m × 6,0 m; pé-direito 2,70 m; janela 2,0 m de largura; borda de tapete 0,40 m por lado; orçamento R$ 85.000,00 com frete e montagem; montagem em 1º/03/2027; prazo de estofados informado pelos fornecedores: 6 a 8 semanas.

Premissa: linho é a fibra de preferência do cliente para estofamento, mas é um tecido tradicionalmente menos resistente a arranhões de gatos que outras opções; mantida a preferência, registrada como pendência na linha do sofá (não substituída por outro material).
Premissa: cliente e localização tratados de forma anonimizada nesta saída, sem reprodução de nome ou endereço.

LISTA DE MOBILIÁRIO E EQUIPAMENTOS

MOB-A — Sofá de 3 lugares com chaise
  Quantidade: 1
  Medida-alvo: [NÃO INFORMADO] — dimensões do sofá (comprimento, profundidade, profundidade da chaise) não fornecidas; verificar no local o encaixe na sala considerando a área combinada de 4,0 × 6,0 m e a circulação até a mesa de jantar.
  Material/desempenho a verificar: linho (preferência do cliente) — pendência: confirmar com o cliente se aceita linho mesmo com dois gatos que arranham, dado o risco de desgaste; se mantido, verificar na ficha técnica resistência à abrasão, método de ensaio e ciclos/fricções duplas, e disponibilidade de capa removível/lavável. Excluir veludo e branco puro (já respeitado).
  Verba estimada: R$ 29.750,00 (Premissa de alocação: 35% de R$ 85.000,00 = R$ 29.750,00), a confirmar com orçamentos.
  Pedir até / verificação de prazo: ver Controle de Prazos (item com prazo de fabricação informado: 6 a 8 semanas).
  Situação: nova

MOB-B — Tapete
  Quantidade: 1
  Medida-alvo e conta: usando as únicas medidas fornecidas (ambiente combinado 4,0 m × 6,0 m) e borda de 0,40 m por lado:
    4,0 m − (2 × 0,40 m) = 4,0 m − 0,80 m = 3,20 m
    6,0 m − (2 × 0,40 m) = 6,0 m − 0,80 m = 5,20 m
    Medida-alvo calculada: 3,20 m × 5,20 m.
    Pendência importante: a sala é de estar E jantar; não foi informado se o tapete se destina a toda a área combinada ou apenas à zona de estar (sob o sofá). O cálculo acima usa o ambiente total por ser o único dado disponível — Premissa a confirmar no local antes de qualquer compra. Medida comercial disponível não verificada; confirmar encaixe, circulação e se 3,20 × 5,20 m corresponde a tamanho de catálogo do fornecedor.
  Material/desempenho a verificar: fibra resistente a fios puxados por garras de gato — verificar com o fabricante; método de limpeza e código de manutenção; resistência ao escorregamento (friso antiderrapante) a verificar na ficha técnica. Sem veludo, sem branco puro.
  Verba estimada: R$ 8.500,00 (Premissa de alocação: 10% de R$ 85.000,00 = R$ 8.500,00), a confirmar com orçamentos.
  Pedir até / verificação de prazo: prazo do fornecedor [NÃO INFORMADO]; fórmula aplicável quando houver dado: pedir até = 01/03/2027 − prazo do fornecedor − margem.
  Situação: nova

MOB-C — Mesa de centro
  Quantidade: 1
  Medida-alvo: [NÃO INFORMADO] — dimensões não fornecidas; verificar no local proporção com o sofá MOB-A e com o tapete MOB-B (área 3,20 × 5,20 m, premissa a confirmar).
  Material/desempenho a verificar: madeira clara (preferência do cliente); verificar acabamento resistente a arranhões/umidade de pata de gato — verificar com o fabricante.
  Verba estimada: R$ 5.950,00 (Premissa de alocação: 7% de R$ 85.000,00 = R$ 5.950,00), a confirmar com orçamentos.
  Pedir até / verificação de prazo: prazo do fornecedor [NÃO INFORMADO].
  Situação: nova

MOB-D — Mesa de jantar para 6 lugares
  Quantidade: 1
  Medida-alvo: [NÃO INFORMADO] — dimensões não fornecidas; verificar no local a circulação entre mesa de jantar e sofá/aparador dentro dos 4,0 × 6,0 m combinados.
  Material/desempenho a verificar: madeira clara (preferência do cliente); verificar se a tonalidade combina com o aparador existente de madeira de demolição (pendência estética — ver Perguntas); resistência a riscos e método de limpeza a verificar na ficha técnica.
  Verba estimada: R$ 12.750,00 (Premissa de alocação: 15% de R$ 85.000,00 = R$ 12.750,00), a confirmar com orçamentos.
  Pedir até / verificação de prazo: prazo do fornecedor [NÃO INFORMADO].
  Situação: nova

MOB-E — Cadeiras
  Quantidade: 6
  Medida-alvo: [NÃO INFORMADO] — dimensões não fornecidas; verificar no local o conjunto com MOB-D e a circulação mínima ao redor da mesa.
  Material/desempenho a verificar: madeira clara (preferência do cliente); se houver estofamento no assento, verificar abrasão, ciclos/fricções duplas e limpeza — a confirmar se cadeiras têm estofamento (não informado).
  Verba estimada: R$ 12.750,00 total para 6 unidades (Premissa de alocação: 15% de R$ 85.000,00 = R$ 12.750,00; valor unitário: R$ 12.750,00 ÷ 6 = R$ 2.125,00 por cadeira), a confirmar com orçamentos.
  Pedir até / verificação de prazo: prazo do fornecedor [NÃO INFORMADO]; se houver estofamento, aplica-se também o prazo de 6 a 8 semanas informado para estofados — a confirmar com o fornecedor.
  Situação: nova

MOB-F — Luminárias de piso
  Quantidade: 2
  Medida-alvo: [NÃO INFORMADO] — altura e base não fornecidas; verificar estabilidade considerando a presença de gatos (risco de queda) — verificar com o fabricante e no projeto.
  Material/desempenho a verificar: estabilidade da base, fixação se aplicável, especificação elétrica a verificar no projeto. Sem veludo, sem branco puro na peça ou cúpula.
  Verba estimada: R$ 5.100,00 total para 2 unidades (Premissa de alocação: 6% de R$ 85.000,00 = R$ 5.100,00; valor unitário: R$ 5.100,00 ÷ 2 = R$ 2.550,00 por luminária), a confirmar com orçamentos.
  Pedir até / verificação de prazo: prazo do fornecedor [NÃO INFORMADO].
  Situação: nova

MOB-G — Cortina para a janela
  Quantidade: 1 (conjunto/trilho)
  Medida-alvo e conta:
    Largura: vão informado de 2,0 m. Premissa de planejamento: trilho com 0,20 m adicionais de cada lado para recuo (stack-back) = 2,0 m + (2 × 0,20 m) = 2,0 m + 0,40 m = 2,40 m — medida a confirmar no local (não é medida de catálogo).
    Altura: Premissa de planejamento — cortina do tipo piso-teto, usando o pé-direito informado (2,70 m) com folga de 0,02 m = 2,70 m − 0,02 m = 2,68 m. Altura real da janela, posição do batente e do rodapé: [NÃO INFORMADO] — confirmar no local antes de especificar.
  Material/desempenho a verificar: linho (preferência do cliente); comportamento ao fogo e método de ensaio a verificar na ficha técnica; resistência a tração na bainha inferior (gatos podem escalar/arranhar) — verificar com o fabricante. Sem veludo, sem branco puro.
  Verba estimada: R$ 5.100,00 (Premissa de alocação: 6% de R$ 85.000,00 = R$ 5.100,00), a confirmar com orçamentos.
  Pedir até / verificação de prazo: prazo do fornecedor [NÃO INFORMADO].
  Situação: nova

MOB-H — Aparador de madeira de demolição (existente)
  Quantidade: 1
  Medida-alvo: [NÃO INFORMADO] — dimensões e estado de conservação não fornecidos; verificar no local estabilidade da estrutura e compatibilidade de posicionamento dentro dos 4,0 × 6,0 m.
  Material/desempenho a verificar: compatibilidade de tom com madeira clara pretendida para MOB-D/MOB-C/MOB-E (pendência estética — ver Perguntas); se houver reaproveitamento, verificar necessidade de reparo/limpeza.
  Verba estimada: R$ 1.700,00 (Premissa de alocação: 2% de R$ 85.000,00 = R$ 1.700,00, reservado para eventual limpeza/reparo/transporte interno); sem aquisição; serviços [NÃO INFORMADO] até confirmação do estado da peça.
  Pedir até / verificação de prazo: se houver serviço de restauro ou transporte, prazo do fornecedor [NÃO INFORMADO]; fórmula aplicável: pedir até = 01/03/2027 − prazo do serviço − margem.
  Situação: existente-reaproveitar (decisão do cliente: manter)

Cobertura: todos os itens solicitados no briefing (sofá, tapete, mesa de centro, mesa de jantar, 6 cadeiras, 2 luminárias, cortina) e a peça existente (aparador) foram relacionados, cada um com código único, sem duplicação. Conflitos registrados nas linhas: MOB-A (linho × gatos que arranham), MOB-B (ambiguidade entre área total e zona de estar), MOB-D/MOB-E/MOB-H (compatibilidade de tom entre madeira clara nova e aparador de demolição existente).

CONTROLE DE ORÇAMENTO

Total informado pelo cliente: R$ 85.000,00.
Escopo do orçamento: inclui frete e montagem, conforme informado pelo cliente.

Premissa de alocação (percentuais de planejamento, a confirmar com orçamentos reais):
  MOB-A Sofá: 35% × R$ 85.000,00 = R$ 29.750,00
  MOB-B Tapete: 10% × R$ 85.000,00 = R$ 8.500,00
  MOB-C Mesa de centro: 7% × R$ 85.000,00 = R$ 5.950,00
  MOB-D Mesa de jantar: 15% × R$ 85.000,00 = R$ 12.750,00
  MOB-E Cadeiras (6 un, total): 15% × R$ 85.000,00 = R$ 12.750,00
  MOB-F Luminárias (2 un, total): 6% × R$ 85.000,00 = R$ 5.100,00
  MOB-G Cortina: 6% × R$ 85.000,00 = R$ 5.100,00
  MOB-H Aparador (reserva de serviço): 2% × R$ 85.000,00 = R$ 1.700,00
  Contingência geral (frete/montagem/imprevistos não detalhados por item): 4% × R$ 85.000,00 = R$ 3.400,00

Soma das verbas conhecidas: 29.750 + 8.500 + 5.950 + 12.750 + 12.750 + 5.100 + 5.100 + 1.700 + 3.400 = R$ 85.000,00.
Conferência de percentuais: 35+10+7+15+15+6+6+2+4 = 100%.

Saldo ou excedente: R$ 85.000,00 − R$ 85.000,00 = R$ 0,00 (saldo provisório — depende de orçamentos reais de cada fornecedor; percentuais são premissa de planejamento, não cotação).

Custos ainda não incluídos ou desconhecidos: valor real de frete e montagem por fornecedor (está dentro do total, mas não detalhado por item); eventual reparo/limpeza do aparador; custo de instalação de trilho de cortina; impostos ou taxas específicas de cada fornecedor.

Todas as verbas estimadas dependem de confirmação por orçamentos.

CONTROLE DE PRAZOS

Data de montagem: 01/03/2027.

MOB-A (Sofá) — Prazo do fornecedor e base de contagem: 6 a 8 semanas, conforme informado pelos fornecedores; base de contagem (dias corridos ou úteis) não especificada — Premissa: tratada como semanas corridas, a confirmar com o fornecedor.
  Margem: Premissa de planejamento de 2 semanas (14 dias) para imprevistos de logística/montagem.
  Pedir até, com conta (cenário mais conservador, usando o limite superior do prazo — 8 semanas):
    01/03/2027 − 8 semanas (56 dias) − 2 semanas (14 dias) = 01/03/2027 − 70 dias = 21/12/2026.
  Pedir até, com conta (cenário usando o limite inferior do prazo — 6 semanas):
    01/03/2027 − 6 semanas (42 dias) − 2 semanas (14 dias) = 01/03/2027 − 56 dias = 04/01/2027.
  Situação do prazo: comparando com a data de hoje (21/10/2026) — nenhum dos dois marcos está vencido. Prazo até o cenário mais conservador (21/12/2026): restam 61 dias corridos (22 a 31/10 = 10 dias; novembro = 30 dias; 1 a 21/12 = 21 dias; 10+30+21 = 61 dias). Recomenda-se usar a data mais conservadora (21/12/2026) como referência de "pedir até", dado que o prazo informado é uma faixa (6 a 8 semanas) e não um valor fechado.

MOB-B (Tapete), MOB-C (Mesa de centro), MOB-D (Mesa de jantar), MOB-E (Cadeiras), MOB-F (Luminárias), MOB-G (Cortina), MOB-H (Aparador/serviço) — Prazo do fornecedor e base de contagem: [NÃO INFORMADO] para todos.
  Margem: não definida.
  Pedir até, com conta: fórmula aplicável quando houver dado — pedir até = 01/03/2027 − prazo do fornecedor − margem. Sem o prazo de cada fornecedor, a data não pode ser calculada.
  Situação do prazo: não confirmado para todos os itens acima; recomenda-se levantar os prazos junto a cada fornecedor com urgência, já que faltam menos de 5 meses até a montagem (21/10/2026 a 01/03/2027).

ESPECIFICAÇÕES A VERIFICAR

MOB-A: verificar na ficha técnica do tecido (linho) comportamento ao fogo, abrasão, método de ensaio e ciclos/fricções duplas, código de limpeza; verificar resistência a arranhões junto ao fabricante (não é garantida por nenhuma ficha técnica); confirmar existência de capa removível/lavável.
MOB-B: verificar tamanho comercial disponível versus 3,20 × 5,20 m calculado, encaixe, circulação e acesso; comportamento ao fogo, resistência ao escorregamento, código de limpeza e, se possível, resistência a fios puxados por garras.
MOB-C: verificar estabilidade, acabamento da madeira clara e resistência a arranhões/umidade junto ao fabricante.
MOB-D: verificar estabilidade, carga suportada e compatibilidade de acabamento com peça existente (MOB-H).
MOB-E: verificar estabilidade, empilhamento sob a mesa (circulação), e, se estofadas, abrasão/ciclos e limpeza.
MOB-F: verificar estabilidade da base, fixação se aplicável e especificação elétrica no projeto — relevante dado o risco de gatos derrubarem a peça.
MOB-G: verificar comportamento ao fogo e método de ensaio do tecido, resistência da bainha inferior, e sistema de fixação do trilho ao teto/parede (carga e estabilidade).
MOB-H: verificar estabilidade estrutural da peça existente antes do reaproveitamento (madeira de demolição pode ter desgaste não visível) e necessidade de tratamento/reparo.

O profissional responsável confere as regras aplicáveis.
Anonimize os dados do cliente e use apenas ferramenta aprovada pelo escritório.

PERGUNTAS PARA O CLIENTE

- O tapete (MOB-B) se destina a toda a área combinada de estar e jantar (4,0 × 6,0 m) ou apenas à zona de estar sob o sofá? O cálculo de 3,20 × 5,20 m usou o ambiente total como única medida disponível — favor confirmar a área real de destino.
- Confirma a preferência por linho no sofá (MOB-A) mesmo com dois gatos que arranham, ou aceita avaliar opções de linho com tratamento/blend mais resistente, mantendo a estética?
- O aparador de madeira de demolição (MOB-H) tem tom/acabamento que deve orientar a escolha de madeira clara nos demais itens novos (mesa de centro, mesa de jantar, cadeiras), ou os tons podem ser diferentes propositalmente?
- Pode informar as dimensões desejadas ou disponíveis para: sofá (MOB-A), mesa de centro (MOB-C), mesa de jantar (MOB-D), cadeiras (MOB-E) e luminárias de piso (MOB-F)?
- Qual é a altura real da janela, a posição do batente e do rodapé, para definir a altura exata da cortina (MOB-G)? A premissa de 2,68 m (piso-teto) está correta?
- As cadeiras (MOB-E) terão assento estofado? Em caso positivo, aplicam-se também os prazos de estofados informados (6 a 8 semanas)?
- O prazo de 6 a 8 semanas informado pelos fornecedores é contado em semanas corridas ou úteis, e a partir de qual evento (fechamento do pedido, pagamento, aprovação de desenho)?
- Pode confirmar os prazos de fabricação/entrega para tapete, mesa de centro, mesa de jantar, cadeiras, luminárias e cortina, hoje marcados como [NÃO INFORMADO]?
- Qual é o estado de conservação do aparador existente (MOB-H)? Há necessidade de reparo, limpeza ou tratamento antes da reinstalação?
- A margem de 2 semanas proposta para o pedido do sofá (MOB-A) é adequada, ou o escritório/fornecedor recomenda outra margem de segurança?
- Confirma a distribuição percentual de orçamento proposta (Premissa de alocação) por item, ou prefere definir valores próprios por peça?

