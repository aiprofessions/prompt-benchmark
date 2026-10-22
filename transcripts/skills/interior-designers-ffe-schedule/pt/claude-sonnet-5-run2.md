# Transcript — skill interior-designers-ffe-schedule [pt] — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:44:59+00:00
- duration_s: 233.0
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

Ambiente: sala de estar e jantar integrada, 4,0 m × 6,0 m (área total = 4,0 × 6,0 = 24 m²), pé-direito 2,70 m, uma janela de 2,0 m de largura.

Dados recebidos, preservados exatamente: 4,0 m × 6,0 m; pé-direito 2,70 m; janela 2,0 m de largura; tapete com 40 cm de piso aparente em cada lado; mesa de jantar para 6; 6 cadeiras; 2 luminárias de piso; orçamento R$ 85.000 com frete e montagem; montagem em 1º de março de 2027; prazo de fabricação dos estofados (fornecedores): 6 a 8 semanas.

Moradores e animais considerados: casal (sem outros dados pessoais reproduzidos) e 2 gatos que arranham — isso implica verificar com os fabricantes resistência a arranhões, estabilidade/fixação de peças elevadas (luminárias de piso) e facilidade de limpeza de tecidos.

Excluído por preferência do cliente: branco puro; veludo. Nenhuma linha desta lista propõe esses materiais/cores.

Preferências a buscar: madeira clara; linho.

Premissa: como a divisão interna entre a zona de estar e a zona de jantar dentro dos 24 m² totais não foi informada, as medidas-alvo de sofá, mesa de centro, mesa de jantar e cadeiras dependem de levantamento no local e ficam marcadas como [NÃO INFORMADO] nesta etapa.

Premissa: foi adotada uma margem de segurança de 14 dias entre a entrega dos fornecedores e a data de montagem, para fins de cálculo de "pedir até". A confirmar com o cliente/escritório.


LISTA DE MOBILIÁRIO E EQUIPAMENTOS

MOB-A — Sofá 3 lugares com chaise
  Quantidade: 1
  Medida-alvo: [NÃO INFORMADO] — depende da zona de estar definida dentro dos 24 m² totais (4,0 m × 6,0 m = 24 m²). Verificar no local.
  Material/desempenho a verificar: linho (preferência do cliente) ou outro tecido, excluindo veludo e branco puro; resistência a arranhões de gatos — verificar com o fabricante; facilidade de limpeza/capas removíveis — verificar com o fabricante.
  Verba estimada (Premissa de alocação): 30% × R$ 85.000 = R$ 25.500,00 — verba estimada, a confirmar com orçamentos.
  Pedir até: ver Controle de prazos (prazo de fabricação 6–8 semanas, informado).
  Situação: nova

MOB-B — Tapete
  Quantidade: 1
  Medida-alvo e conta: (4,0 m − 2 × 0,40 m) × (6,0 m − 2 × 0,40 m) = 3,20 m × 5,20 m. Atenção: cálculo aplicado à dimensão total do ambiente combinado, pois a borda foi especificada sem indicar zona; verificar se a intenção é cobrir o ambiente integrado inteiro ou apenas uma das zonas (ver Perguntas). Verificar disponibilidade comercial nesse tamanho ou necessidade de peça sob medida.
  Material: linho ou outro, excluindo veludo e branco puro; resistência a arranhões/desfiamento por gatos — verificar com fabricante; resistência ao escorregamento — verificar com fabricante; facilidade de limpeza.
  Verba estimada (Premissa de alocação): 10% × R$ 85.000 = R$ 8.500,00 — estimada, a confirmar.
  Pedir até: prazo de fabricação/entrega [NÃO INFORMADO].
  Situação: nova

MOB-C — Mesa de centro
  Quantidade: 1
  Medida-alvo: [NÃO INFORMADO] — depende do layout da zona de estar.
  Material: madeira clara (preferência do cliente); evitar acabamento branco puro; estabilidade e cantos — verificar no projeto, considerando os gatos.
  Verba estimada (Premissa de alocação): 5% × R$ 85.000 = R$ 4.250,00.
  Pedir até: prazo [NÃO INFORMADO].
  Situação: nova

MOB-D — Mesa de jantar para 6
  Quantidade: 1
  Medida-alvo: [NÃO INFORMADO] — depende da zona de jantar definida dentro dos 24 m² totais; circulação ao redor da mesa a verificar no projeto pelo profissional responsável.
  Material: madeira clara; evitar branco puro; acabamento e limpeza — verificar com fabricante.
  Verba estimada (Premissa de alocação): 15% × R$ 85.000 = R$ 12.750,00.
  Pedir até: prazo [NÃO INFORMADO].
  Situação: nova

MOB-E — Cadeiras
  Quantidade: 6
  Medida-alvo: [NÃO INFORMADO]. Pendente: confirmar se são estofadas (ver Perguntas).
  Material: estrutura em madeira clara; se estofadas, linho, excluindo veludo e branco puro; resistência a arranhões — verificar com fabricante.
  Verba estimada (Premissa de alocação): 12% × R$ 85.000 = R$ 10.200,00 (total para 6 unidades; conta unitária: R$ 10.200,00 ÷ 6 = R$ 1.700,00/un).
  Pedir até: se estofadas, mesmo prazo do MOB-A (6–8 semanas); se não, prazo [NÃO INFORMADO].
  Situação: nova

MOB-F — Luminárias de piso
  Quantidade: 2
  Medida-alvo: altura inferior a 2,70 m (pé-direito do ambiente — limite superior, não medida-alvo exata); medida final [NÃO INFORMADO].
  Material: base estável e fixação — verificar com fabricante devido ao risco de queda com gatos; acabamento evitando branco puro e veludo, se aplicável à cúpula/base.
  Verba estimada (Premissa de alocação): 6% × R$ 85.000 = R$ 5.100,00 (total para 2 unidades; conta unitária: R$ 5.100,00 ÷ 2 = R$ 2.550,00/un).
  Pedir até: prazo [NÃO INFORMADO].
  Situação: nova

MOB-G — Cortina
  Quantidade: 1 conjunto, para a janela de 2,0 m de largura
  Medida-alvo: largura do trilho = 2,0 m (largura informada da janela) + folga para abertura (não informada); altura = altura da janela (não informada) + folga (não informada). Medida final [NÃO INFORMADO] — depende de levantamento no local.
  Material: linho (preferência do cliente); excluindo veludo e branco puro; comportamento ao fogo e código de limpeza — verificar com fabricante; resistência a arranhões se acessível aos gatos; fixação do trilho — verificar carga suportada.
  Verba estimada (Premissa de alocação): 7% × R$ 85.000 = R$ 5.950,00.
  Pedir até: prazo [NÃO INFORMADO].
  Situação: nova

MOB-H — Aparador de madeira de demolição (existente)
  Quantidade: 1
  Medida-alvo/estado: medidas e estado de conservação [NÃO INFORMADO].
  Material: madeira de demolição (tom tipicamente mais escuro/rústico — observação de harmonização com a preferência por madeira clara nas peças novas; não é rejeição explícita, ver Perguntas); estabilidade e fixação — verificar no projeto, considerando os gatos.
  Verba estimada (Premissa de alocação): sem aquisição; serviços (possível reparo/limpeza/transporte): 5% × R$ 85.000 = R$ 4.250,00 — estimativa de alocação, a confirmar com orçamento de restauração/transporte, se necessário.
  Pedir até: prazo de serviços (se houver) [NÃO INFORMADO].
  Situação: existente-reaproveitar (decisão do cliente: manter).

Cobertura: todos os pedidos do briefing (sofá, tapete, mesa de centro, mesa de jantar, 6 cadeiras, 2 luminárias de piso, cortina) e a peça existente (aparador) estão representados, um código cada, sem duplicação. Nenhuma linha propõe veludo ou branco puro. Conflito/observação em aberto: tom do aparador (madeira de demolição) versus preferência por madeira clara nas peças novas — mantido na lista como pendência de harmonização, não como rejeição.


CONTROLE DE ORÇAMENTO

Total informado pelo cliente: R$ 85.000 (com frete e montagem).
Escopo do orçamento: aquisição + frete + montagem, conforme informado pelo cliente.

Verbas por premissa de alocação (percentuais do total, cada uma "verba estimada, a confirmar com orçamentos"):
  MOB-A: 30% × 85.000 = R$ 25.500,00
  MOB-B: 10% × 85.000 = R$ 8.500,00
  MOB-C: 5% × 85.000 = R$ 4.250,00
  MOB-D: 15% × 85.000 = R$ 12.750,00
  MOB-E: 12% × 85.000 = R$ 10.200,00
  MOB-F: 6% × 85.000 = R$ 5.100,00
  MOB-G: 7% × 85.000 = R$ 5.950,00
  MOB-H (serviços): 5% × 85.000 = R$ 4.250,00
  Subtotal itens (90%): 30+10+5+15+12+6+7+5 = 90% → 90% × 85.000 = R$ 76.500,00
  Reserva para frete e montagem (premissa de alocação, não atribuída a um item específico): 10% × 85.000 = R$ 8.500,00, a confirmar com transportadora/equipe de montagem.

Soma das verbas conhecidas: R$ 76.500,00 + R$ 8.500,00 = R$ 85.000,00.
Saldo: R$ 85.000,00 − R$ 85.000,00 = R$ 0,00 (saldo provisório, pois toda a distribuição é uma premissa de alocação, não orçamentos reais de fornecedores).

Custos ainda não incluídos ou desconhecidos: valores reais de fornecedores para todos os itens; eventual reparo/restauração do aparador existente; qualquer custo adicional de instalação da cortina (trilho/motorização, se houver) e das luminárias.

Todas as verbas estimadas dependem de confirmação por orçamentos.


CONTROLE DE PRAZOS

Data de montagem: 1º de março de 2027 (2027-03-01).

MOB-A (sofá) — e, se confirmado, MOB-E (cadeiras, se estofadas):
  Prazo do fornecedor: 6 a 8 semanas (informado); base de contagem (a partir do pedido, do pagamento, dias corridos ou úteis) [NÃO INFORMADO].
  Margem: 14 dias (premissa).
  Pedir até — cenário conservador (8 semanas = 56 dias): 2027-03-01 − 56 dias − 14 dias = 2027-03-01 − 70 dias = 2026-12-21.
  Pedir até — cenário otimista (6 semanas = 42 dias): 2027-03-01 − 42 dias − 14 dias = 2027-03-01 − 56 dias = 2027-01-04.
  Recomenda-se usar a data mais conservadora (2026-12-21) para garantir a entrega.
  Situação do prazo: comparando com a data de referência 2026-10-21, a data "pedir até" mais conservadora (2026-12-21) ainda não está vencida — faltam aproximadamente 61 dias corridos (21/10 a 21/11 = 31 dias; 21/11 a 21/12 = 30 dias; total 61 dias). Base de contagem do prazo do fornecedor e margem seguem não confirmadas.

MOB-B, MOB-C, MOB-D, MOB-F, MOB-G: prazo do fornecedor [NÃO INFORMADO]. Fórmula: pedir até = 2027-03-01 − prazo do fornecedor (não informado) − margem (não informada). Situação do prazo: não confirmado.

MOB-H (serviços de reparo/limpeza/transporte, se necessários): prazo [NÃO INFORMADO]. Mesma fórmula acima. Situação do prazo: não confirmado.


ESPECIFICAÇÕES A VERIFICAR

- MOB-A: abrasão (ciclos/fricções duplas — método Martindale ou equivalente, conforme ficha técnica), comportamento ao fogo do estofado, código/instruções de limpeza do tecido, resistência a arranhões (gatos). Resistência ao escorregamento não aplicável (peça elevada, sem contato direto com circulação de piso).
- MOB-B: comportamento ao fogo, resistência ao escorregamento (especialmente sobre piso liso), código/instruções de limpeza, abrasão.
- MOB-C: estabilidade e fixação (risco de tombamento, considerando os gatos), resistência do acabamento a arranhões. Comportamento ao fogo normalmente pouco relevante para madeira maciça, mas confirmar conforme uso do imóvel e acabamento aplicado.
- MOB-D: estabilidade, fixação (especialmente se houver mecanismo extensível), acabamento e código de limpeza.
- MOB-E: estabilidade estrutural e fixação; se estofadas, aplicar os mesmos itens do MOB-A (abrasão, comportamento ao fogo, limpeza, arranhões).
- MOB-F: estabilidade e fixação — prioritário, dado o risco de queda com os gatos; certificação elétrica — verificar com fabricante; comportamento ao fogo da cúpula/tecido, se aplicável.
- MOB-G: comportamento ao fogo do tecido, código de limpeza, resistência a arranhões (acesso dos gatos), fixação do trilho na parede/estrutura (carga suportada).
- MOB-H: estabilidade e fixação (verificar no projeto, considerando peso sobre a peça e proximidade dos gatos); estado de conservação do acabamento, a verificar in loco. Comportamento ao fogo geralmente pouco relevante para mobiliário sólido de madeira, mas confirmar conforme uso do imóvel.

O profissional responsável confere as regras aplicáveis.
Anonimize os dados do cliente e use apenas ferramenta aprovada pelo escritório.


PERGUNTAS PARA O CLIENTE

- Qual é a divisão interna das zonas de estar e jantar dentro dos 4,0 m × 6,0 m (24 m²) totais? Necessário para medidas-alvo do sofá, mesa de centro, mesa de jantar e cadeiras.
- O tapete calculado (3,20 m × 5,20 m, a partir da borda de 0,40 m aplicada à dimensão total do ambiente) deve cobrir o ambiente integrado inteiro ou apenas uma das zonas (estar ou jantar)? Essa medida está disponível comercialmente ou será sob medida?
- As 6 cadeiras são estofadas? Se sim, confirmam tecido em linho (sem veludo) e o mesmo prazo de 6 a 8 semanas informado para os estofados?
- Qual é a altura da janela e a folga desejada em cada lado/acima do trilho para dimensionar a cortina (largura e altura)?
- Quais são as medidas e o estado de conservação do aparador existente? Ele precisará de reparo, limpeza ou transporte?
- O tom do aparador (madeira de demolição) deve ser harmonizado com a preferência por madeira clara nas peças novas, ou permanecerá como peça de contraste proposital?
- O prazo de 6 a 8 semanas dos estofados é em semanas corridas ou úteis, e a contagem começa no pedido, no pagamento ou em outro marco?
- Qual margem de segurança (dias) deve ser considerada entre a entrega dos fornecedores e a montagem? Foi usada a premissa de 14 dias nesta lista — favor confirmar.
- Os 10% do orçamento reservados como premissa para frete e montagem (R$ 8.500,00) são suficientes, ou já há valor contratado?
- Qual é o prazo de fabricação/entrega dos demais itens (tapete, mesas, cadeiras não estofadas, luminárias, cortina)?
- Confirma a alocação percentual proposta entre os itens, ou há orçamentos já obtidos que devem substituir essas estimativas?

