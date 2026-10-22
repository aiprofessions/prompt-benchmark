# Transcript — skill interior-designers-ffe-schedule [pt] — claude-fable-5-1 — run 1

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-21T05:50:34+00:00
- duration_s: 125.9
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

## Conceito
Sala de estar e jantar integradas para um casal com dois gatos que arranham. Preferências informadas: madeira clara, linho. Uso: estar e refeições para 6 pessoas. Nenhum estilo ou paleta além do informado.
Dados recebidos: ambiente 4,0 m × 6,0 m; pé-direito 2,70 m; uma janela de 2,0 m de largura; tapete com 40 cm de piso aparente em cada lado; orçamento R$ 85.000 com frete e montagem; montagem 1º de março de 2027; prazo de fabricação dos estofados 6 a 8 semanas (fornecedores do escritório). Altura da janela, posição das aberturas, portas, acessos e circulação: [NÃO INFORMADO]. Medidas e estado do aparador existente: [NÃO INFORMADO].
Moradores e animais considerados: casal (2 adultos) e 2 gatos que arranham.
Excluído por preferência do cliente: branco puro; veludo.
Premissa: como o pedido não indica zoneamento, assume-se que a janela de 2,0 m está na zona de estar e que estar e jantar dividem o comprimento de 6,0 m; a confirmar no levantamento.
Premissa: "40 cm de piso aparente em cada lado" foi lido como borda em relação às quatro paredes do ambiente; se o tapete for apenas da zona de estar, a conta muda (ver Perguntas).

## Lista de mobiliário e equipamentos
| Código | Item | Quantidade | Medida-alvo e conta | Material e desempenho a verificar | Verba estimada por linha | Pedir até / verificação de prazo | Situação |
|---|---|---|---|---|---|---|---|
| MOB-A | Sofá de 3 lugares com chaise | 1 | Premissa de planejamento: 2,60 m a 2,80 m de comprimento × 1,00 m de profundidade no corpo e 1,60 m na chaise; verificar encaixe na zona de estar (largura 4,0 m) e acesso pelos vãos [NÃO INFORMADO] | Revestimento sem veludo e sem branco puro; cliente gosta de linho: verificar com o fabricante o comportamento do linho frente a gatos que arranham e alternativas de trama fechada; capas removíveis e laváveis; estrutura e pés em madeira clara, se desejado; abrasão e limpeza na ficha técnica | Premissa de alocação: 25% × R$ 85.000 = R$ 21.250,00 (verba estimada, a confirmar com orçamentos) | Pedir até 21/12/2026 (1º/03/2027 − 8 semanas − 2 semanas de margem); conta no Controle de prazos | nova |
| MOB-B | Tapete | 1 | (4,0 m − 2 × 0,40 m) × (6,0 m − 2 × 0,40 m) = 3,20 m × 5,20 m. Dimensão calculada, não tamanho comercial: verificar disponibilidade sob medida ou tamanho padrão mais próximo | Sem veludo; sem branco puro; fibra e trama a verificar com o fabricante quanto a arranhões e pelos (gatos); facilidade de limpeza; resistência ao escorregamento ou base antiderrapante | Premissa de alocação: 8% × R$ 85.000 = R$ 6.800,00 (verba estimada, a confirmar) | Prazo do fornecedor [NÃO INFORMADO]; fórmula: 1º/03/2027 − prazo − margem; não confirmado | nova |
| MOB-C | Mesa de centro | 1 | Premissa de planejamento: 1,00 m × 0,60 m × 0,40 m de altura; manter circulação de aprox. 0,45 m até o sofá — verificar no projeto | Madeira clara (preferência); cantos arredondados e estabilidade (gatos); acabamento resistente a arranhões a verificar com o fabricante | Premissa de alocação: 5% × R$ 85.000 = R$ 4.250,00 (a confirmar) | Prazo [NÃO INFORMADO]; não confirmado | nova |
| MOB-D | Mesa de jantar para 6 | 1 | Premissa de planejamento: 1,80 m × 0,90 m × 0,75 m de altura; verificar no projeto afastamento de aprox. 0,90 m das paredes para recuo das cadeiras dentro da largura de 4,0 m | Madeira clara (preferência); sem branco puro; acabamento, estabilidade e carga a verificar na ficha técnica | Premissa de alocação: 14% × R$ 85.000 = R$ 11.900,00 (a confirmar) | Prazo [NÃO INFORMADO]; não confirmado | nova |
| MOB-E | Cadeiras de jantar | 6 | Premissa de planejamento: 0,45 m a 0,50 m de largura cada; 6 × 0,50 m = 3,00 m de frente total, compatível com a mesa de 1,80 m em dois lados longos + duas cabeceiras — verificar no projeto | Madeira clara (preferência); se estofadas, sem veludo, sem branco puro, assento removível ou revestimento lavável; se estofadas, aplica-se o prazo de 6 a 8 semanas dos estofados | Premissa de alocação: 15% × R$ 85.000 = R$ 12.750,00 por linha; unitária R$ 12.750,00 ÷ 6 = R$ 2.125,00 (a confirmar) | Se estofadas: pedir até 21/12/2026 (mesma conta de MOB-A); se não estofadas: prazo [NÃO INFORMADO] | nova |
| MOB-F | Luminárias de piso | 2 | Premissa de planejamento: altura 1,50 m a 1,70 m, compatível com pé-direito 2,70 m; base com diâmetro ≥ 0,30 m — verificar com o fabricante | Base pesada e baixo centro de gravidade (gatos); cabo protegido; sem acabamento branco puro; sem veludo em cúpulas; verificar pontos de tomada no local [NÃO INFORMADO] | Premissa de alocação: 7% × R$ 85.000 = R$ 5.950,00 por linha; unitária R$ 5.950,00 ÷ 2 = R$ 2.975,00 (a confirmar) | Prazo [NÃO INFORMADO]; não confirmado | nova |
| MOB-G | Cortina para a janela | 1 conjunto | Largura do vão 2,0 m. Premissa de planejamento: trilho/varão = 2,0 m + 2 × 0,25 m = 2,50 m; altura: do trilho ao piso, pé-direito 2,70 m menos cota do trilho [NÃO INFORMADO] | Tecido tipo linho (preferência) — verificar com o fabricante trama, encolhimento e comportamento com gatos; sem veludo, sem branco puro; fixação do trilho na laje/parede (gatos podem puxar); comportamento ao fogo e limpeza na ficha técnica | Premissa de alocação: 8% × R$ 85.000 = R$ 6.800,00 (a confirmar; inclui confecção e trilho) | Prazo de confecção e instalação [NÃO INFORMADO]; não confirmado | nova |
| MOB-H | Aparador de madeira de demolição | 1 | Medidas [NÃO INFORMADO]; posição no layout a definir no projeto (estar ou jantar) | Estado de conservação [NÃO INFORMADO]; verificar necessidade de limpeza, revisão de ferragens, nivelamento e fixação (gatos) | Sem aquisição; serviços [NÃO INFORMADO]. Premissa de alocação para eventual limpeza/revisão/transporte: 2% × R$ 85.000 = R$ 1.700,00 (a confirmar) | Prazo de serviços/transporte [NÃO INFORMADO]; não confirmado | existente-reaproveitar |

Cobertura: sofá → MOB-A; tapete → MOB-B; mesa de centro → MOB-C; mesa de jantar para 6 → MOB-D; 6 cadeiras → MOB-E; 2 luminárias de piso → MOB-F; cortina → MOB-G; aparador existente → MOB-H. Nenhum conflito direto com as rejeições. Pendência em MOB-A, MOB-E e MOB-G: a preferência por linho precisa ser confirmada frente aos gatos que arranham, sem prometer resistência. Pendência em MOB-B: interpretação da borda (ambiente inteiro ou zona de estar).

## Controle de orçamento
Total informado pelo cliente: R$ 85.000, com frete e montagem.
Escopo do orçamento: aquisição + frete + montagem. Inclusão de serviços no aparador, instalação de cortina e eventual ponto elétrico para luminárias: [NÃO INFORMADO].
Verbas fornecidas ou premissa de alocação: nenhuma verba por item foi fornecida. Premissa de alocação (percentuais sobre R$ 85.000):
- MOB-A sofá: 25% → R$ 21.250,00
- MOB-B tapete: 8% → R$ 6.800,00
- MOB-C mesa de centro: 5% → R$ 4.250,00
- MOB-D mesa de jantar: 14% → R$ 11.900,00
- MOB-E 6 cadeiras: 15% → R$ 12.750,00 (R$ 2.125,00 cada)
- MOB-F 2 luminárias: 7% → R$ 5.950,00 (R$ 2.975,00 cada)
- MOB-G cortina: 8% → R$ 6.800,00
- MOB-H aparador (serviços): 2% → R$ 1.700,00
- Frete e montagem (todas as linhas): 10% → R$ 8.500,00
- Reserva de contingência: 6% → R$ 5.100,00
Soma das verbas conhecidas: 21.250 + 6.800 + 4.250 + 11.900 + 12.750 + 5.950 + 6.800 + 1.700 + 8.500 + 5.100 = R$ 85.000,00.
Saldo ou excedente: R$ 85.000,00 − R$ 85.000,00 = R$ 0,00 (saldo provisório; a alocação é premissa e toda parcela depende de orçamentos reais).
Custos ainda não incluídos ou desconhecidos: instalação de trilho de cortina; eventual ponto elétrico/tomada para as luminárias; transporte e revisão do aparador (se existirem); descarte de embalagens; variação de frete para Recife conforme origem dos fornecedores.
Todas as verbas estimadas dependem de confirmação por orçamentos.

## Controle de prazos
Data de montagem: 1º de março de 2027. Data de referência: 21 de outubro de 2026.
Premissa: "6 a 8 semanas" contadas em semanas corridas (8 semanas = 56 dias corridos), adotando o pior caso; base de contagem (a partir do pedido, do pagamento ou da aprovação do tecido) [NÃO INFORMADO].
Premissa: margem de 2 semanas (14 dias corridos) para frete até Recife e contingências.
| Código | Prazo do fornecedor e base de contagem | Margem | Pedir até, com conta | Situação do prazo |
|---|---|---|---|---|
| MOB-A | 6 a 8 semanas (fabricação); base de contagem [NÃO INFORMADO]; adotadas 8 semanas = 56 dias corridos (premissa) | 14 dias (premissa) | 1º/03/2027 − 56 dias = 04/01/2027; 04/01/2027 − 14 dias = 21/12/2026 | Não vencido em 21/10/2026 (faltam 61 dias até 21/12/2026); confirmar base de contagem |
| MOB-B | [NÃO INFORMADO] | a definir | 1º/03/2027 − prazo − margem | Não confirmado |
| MOB-C | [NÃO INFORMADO] | a definir | 1º/03/2027 − prazo − margem | Não confirmado |
| MOB-D | [NÃO INFORMADO] | a definir | 1º/03/2027 − prazo − margem | Não confirmado |
| MOB-E | Se estofadas: 6 a 8 semanas (mesma base de MOB-A); se não estofadas: [NÃO INFORMADO] | 14 dias (premissa) | Se estofadas: 21/12/2026 (mesma conta de MOB-A); caso contrário, fórmula sem data | Não vencido se estofadas; não confirmado se não estofadas |
| MOB-F | [NÃO INFORMADO] | a definir | 1º/03/2027 − prazo − margem | Não confirmado |
| MOB-G | Confecção e instalação [NÃO INFORMADO]; depende de medição no local após fixação do trilho | a definir | 1º/03/2027 − prazo − margem | Não confirmado |
| MOB-H | Serviços/transporte [NÃO INFORMADO] | a definir | 1º/03/2027 − prazo de serviço − margem | Não confirmado; se não houver serviços, sem prazo |

## Especificações a verificar
- MOB-A (sofá): ficha técnica do tecido — comportamento ao fogo, abrasão com método de ensaio e número de ciclos ou fricções duplas, códigos/instruções de limpeza, solidez da cor; capas removíveis; estrutura, densidade de espumas e carga; conferir com o fabricante a adequação a gatos que arranham (sem promessa de resistência); acesso pelos vãos e encaixe no projeto.
- MOB-B (tapete): comportamento ao fogo, abrasão e método/ciclos, limpeza, resistência ao escorregamento ou necessidade de base antiderrapante; tamanho disponível versus 3,20 m × 5,20 m calculado; comportamento a pelos e arranhões a verificar com o fabricante.
- MOB-C (mesa de centro): estabilidade, carga, raio de cantos, acabamento da madeira e instruções de limpeza; abrasão e fogo não aplicáveis como têxtil, exceto se houver tampo estofado.
- MOB-D (mesa de jantar): estabilidade, carga do tampo, acabamento da madeira e limpeza; abrasão e fogo não aplicáveis a peça sem têxtil.
- MOB-E (cadeiras): se estofadas, mesma lista têxtil de MOB-A; estabilidade, carga e empilhamento; acabamento da madeira.
- MOB-F (luminárias): estabilidade e massa da base, ensaio de tombamento se disponível, classe de proteção elétrica, tipo de lâmpada e potência, cúpula sem têxtil rejeitado; comportamento ao fogo da cúpula se têxtil.
- MOB-G (cortina): comportamento ao fogo, encolhimento e instruções de limpeza do tecido; fixação do trilho (carga e tipo de substrato); comprimento até o piso em função da cota do trilho.
- MOB-H (aparador): estado estrutural, ferragens, tratamento da madeira e fixação/nivelamento; sem exigência de ficha têxtil; justificativa: peça existente sem aquisição.
O profissional responsável confere as regras aplicáveis.
Anonimize os dados do cliente e use apenas ferramenta aprovada pelo escritório.

## Perguntas para o cliente
- Tapete: os 40 cm de piso aparente são em relação às paredes do ambiente inteiro (resultando 3,20 m × 5,20 m) ou apenas à zona de estar? Se zona de estar, quais os limites dela?
- Confirma a leitura dos "6 a 8 semanas" como semanas corridas e a partir de qual marco (pedido, pagamento, aprovação de tecido)?
- Aceita a margem de 2 semanas e, portanto, a data-limite de 21/12/2026 para o pedido dos estofados?
- As 6 cadeiras serão estofadas (prazo dos estofados) ou de madeira sem estofado?
- Prazos dos fornecedores de tapete, mesas, luminárias, cortina e eventuais serviços do aparador?
- Medidas, estado de conservação e posição pretendida do aparador de madeira de demolição; haverá limpeza, revisão ou transporte?
- Altura da janela, cota do trilho, posição das portas e aberturas, e trajeto de acesso para peças grandes (sofá, mesa de jantar, tapete enrolado)?
- Pontos de tomada disponíveis para as 2 luminárias de piso?
- Confirma a premissa de alocação por item e a reserva de 6%? O orçamento de R$ 85.000 inclui instalação de cortina e serviços no aparador?
- Linho é preferência, mas os gatos arranham: aceita alternativas de trama fechada com aparência semelhante se o fabricante não recomendar linho? Rejeita apenas branco puro ou também tons off-white?

