# Transcript — skill interior-designers-ffe-schedule [pt] — claude-fable-5-1 — run 2

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-21T06:26:30+00:00
- duration_s: 122.8
- exit_code: 0
- attempts: 2
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
Sala de estar e jantar integrada, uso pelo casal, com dois gatos que arranham. Preferências: madeira clara, linho.
Dados recebidos: ambiente 4,0 m × 6,0 m; pé-direito 2,70 m; uma janela de 2,0 m de largura; tapete com 40 cm de piso aparente em cada lado; mesa de jantar para 6; 6 cadeiras; 2 luminárias de piso; orçamento R$ 85.000 com frete e montagem; montagem em 1º de março de 2027; prazo de fabricação dos estofados: 6 a 8 semanas.
Moradores e animais considerados: casal; dois gatos que arranham (prioridade: tecidos e superfícies de fácil limpeza, capas removíveis, estabilidade de peças altas, comportamento ao arranhão a verificar com o fabricante).
Excluído por preferência do cliente: branco puro; veludo.
Premissa: o tapete é calculado sobre o ambiente inteiro, conforme o briefing; como a sala reúne estar e jantar, a medida resultante passaria sob a mesa de jantar — a confirmar se o tapete deve cobrir apenas a área de estar.
Premissa: aberturas (portas), acessos, pontos elétricos e distribuição estar/jantar não informados; medidas-alvo abaixo são de planejamento, a verificar no projeto e no local.

LISTA DE MOBILIÁRIO E EQUIPAMENTOS

Código | Item | Quantidade | Medida-alvo e conta | Material e desempenho a verificar | Verba estimada por linha | Pedir até / verificação de prazo | Situação
MOB-A | Sofá de 3 lugares com chaise | 1 | Medida [NÃO INFORMADO]. Premissa de planejamento: 2,40 a 2,80 m de comprimento × 1,60 a 1,80 m na chaise; lado da chaise a definir; conferir encaixe e circulação no projeto | Sem veludo. Linho (preferência) — comportamento ao arranhão de gatos e facilidade de limpeza: verificar com o fabricante; capas removíveis; estrutura em madeira clara se aparente | R$ 23.800,00 (85.000 × 28%), verba estimada, a confirmar com orçamentos | Montagem 01/03/2027 − 8 semanas − margem 2 semanas = 21/12/2026 (premissa: semanas corridas a partir da confirmação do pedido) | nova
MOB-B | Tapete | 1 | (4,0 m − 2 × 0,40 m) × (6,0 m − 2 × 0,40 m) = 3,2 m × 5,2 m; dimensão calculada, não tamanho comercial — verificar disponibilidade, encaixe e cobertura estar/jantar | Sem veludo, sem branco puro; facilidade de limpeza, pelos de gato e aderência ao piso: verificar com o fabricante | R$ 8.500,00 (85.000 × 10%), verba estimada, a confirmar | Prazo do fornecedor [NÃO INFORMADO]; pedir até = 01/03/2027 − prazo − margem | nova
MOB-C | Mesa de centro | 1 | Medida [NÃO INFORMADO]. Premissa de planejamento: proporcional ao sofá, com passagem livre ao redor — verificar no projeto | Madeira clara (preferência); cantos arredondados e estabilidade pela presença dos gatos: verificar | R$ 5.100,00 (85.000 × 6%), verba estimada, a confirmar | Prazo [NÃO INFORMADO]; mesma fórmula | nova
MOB-D | Mesa de jantar para 6 | 1 | Medida [NÃO INFORMADO]. Premissa de planejamento: 1,60 a 1,80 m × 0,90 m; verificar circulação com cadeiras afastadas | Madeira clara (preferência); facilidade de limpeza do tampo: verificar | R$ 11.900,00 (85.000 × 14%), verba estimada, a confirmar | Prazo [NÃO INFORMADO]; mesma fórmula | nova
MOB-E | Cadeiras de jantar | 6 | Medida [NÃO INFORMADO]; compatibilizar altura do assento com a mesa MOB-D | Sem veludo; se estofadas, tecido e comportamento ao arranhão a verificar com o fabricante; madeira clara (preferência) | R$ 15.300,00 no total (85.000 × 18%); unitária R$ 2.550,00 (15.300 ÷ 6), verba estimada, a confirmar | Se estofadas: 01/03/2027 − 8 semanas − 2 semanas = 21/12/2026 (premissa); se não, prazo [NÃO INFORMADO] | nova
MOB-F | Luminárias de piso | 2 | Altura [NÃO INFORMADO]; pé-direito 2,70 m como limite; posição depende dos pontos elétricos [NÃO INFORMADO] | Estabilidade da base e risco de tombamento pelos gatos; cabos: verificar com o fabricante e no projeto | R$ 5.100,00 no total (85.000 × 6%); unitária R$ 2.550,00 (5.100 ÷ 2), verba estimada, a confirmar | Prazo [NÃO INFORMADO]; mesma fórmula | nova
MOB-G | Cortina para a janela | 1 | Largura da janela 2,0 m. Premissa de planejamento: trilho 2,0 m + 2 × 0,30 m de transpasse = 2,60 m; altura até 2,70 m (pé-direito), descontando folgas a medir no local; posição e altura da janela [NÃO INFORMADO] | Sem branco puro; linho (preferência) — comportamento ao arranhão, facilidade de lavagem e fixação do trilho/suporte: verificar | R$ 6.800,00 (85.000 × 8%), verba estimada, a confirmar | Prazo [NÃO INFORMADO]; mesma fórmula | nova
MOB-H | Aparador de madeira de demolição | 1 | Medidas [NÃO INFORMADO]; posição a verificar no projeto | Estado de conservação [NÃO INFORMADO]; tonalidade a conferir frente à preferência por madeira clara | sem aquisição; serviços (limpeza, reparo, transporte) [NÃO INFORMADO] | Se houver serviços ou transporte: prazo [NÃO INFORMADO]; mesma fórmula | existente-reaproveitar
RES-1 | Reserva para frete, montagem e imprevistos | — | — | — | R$ 8.500,00 (85.000 × 10%), premissa de alocação | — | —

Cobertura: sofá com chaise = MOB-A; tapete = MOB-B; mesa de centro = MOB-C; mesa de jantar para 6 = MOB-D; 6 cadeiras = MOB-E; 2 luminárias de piso = MOB-F; cortina = MOB-G; aparador existente = MOB-H. Conflitos: MOB-B cobriria toda a sala, inclusive sob o jantar; MOB-H é madeira de demolição, possivelmente mais escura que a preferência por madeira clara — peça mantida por decisão do cliente.

CONTROLE DE ORÇAMENTO
Total informado pelo cliente: R$ 85.000 com frete e montagem.
Escopo do orçamento: frete e montagem incluídos; serviços no aparador (MOB-H), instalação de trilho de cortina e pontos elétricos para luminárias: [NÃO INFORMADO] se incluídos.
Verbas fornecidas ou premissa de alocação (nenhuma verba foi fornecida; distribuição abaixo é premissa de alocação):
  MOB-A: 85.000 × 28% = R$ 23.800,00
  MOB-B: 85.000 × 10% = R$ 8.500,00
  MOB-C: 85.000 × 6% = R$ 5.100,00
  MOB-D: 85.000 × 14% = R$ 11.900,00
  MOB-E: 85.000 × 18% = R$ 15.300,00
  MOB-F: 85.000 × 6% = R$ 5.100,00
  MOB-G: 85.000 × 8% = R$ 6.800,00
  MOB-H: sem aquisição; serviços [NÃO INFORMADO]
  RES-1: 85.000 × 10% = R$ 8.500,00
Soma das verbas conhecidas: 23.800 + 8.500 + 5.100 + 11.900 + 15.300 + 5.100 + 6.800 + 8.500 = R$ 85.000,00.
Saldo provisório: 85.000 − 85.000 = R$ 0,00 (provisório: serviços de MOB-H e eventuais instalações não estão incluídos).
Custos ainda não incluídos ou desconhecidos: serviços no aparador; instalação elétrica das luminárias; instalação do trilho da cortina; eventual diferença entre tamanho comercial e tamanho calculado do tapete.
Todas as verbas estimadas dependem de confirmação por orçamentos.

CONTROLE DE PRAZOS
Data de montagem: 1º de março de 2027. Data de referência: 21/10/2026.

Código | Prazo do fornecedor e base de contagem | Margem | Pedir até, com conta | Situação do prazo
MOB-A | 6 a 8 semanas (base de contagem [NÃO INFORMADO]; premissa: semanas corridas desde a confirmação do pedido) | 2 semanas (premissa) | 01/03/2027 − 8 semanas − 2 semanas = 21/12/2026 (com 6 semanas: 04/01/2027) | Em aberto (21/12/2026 é posterior à referência); base de contagem não confirmada
MOB-B | [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Não confirmado
MOB-C | [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Não confirmado
MOB-D | [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Não confirmado
MOB-E | Se estofadas, 6 a 8 semanas como MOB-A; se não, [NÃO INFORMADO] | 2 semanas (premissa) | Se estofadas: 21/12/2026 (mesma conta de MOB-A) | Não confirmado (depende do tipo de cadeira)
MOB-F | [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Não confirmado
MOB-G | [NÃO INFORMADO]; cortina sob medida depende da medição no local | a definir | 01/03/2027 − prazo − margem | Não confirmado
MOB-H | Serviços e transporte [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Não confirmado

ESPECIFICAÇÕES A VERIFICAR
- MOB-A: ficha técnica do tecido — comportamento ao fogo, abrasão (método de ensaio e ciclos/fricções duplas), códigos de limpeza, capas removíveis; estrutura, densidade das espumas; comportamento ao arranhão: verificar com o fabricante. Medidas, acesso (portas, elevador, escadas) e circulação: verificar no projeto e no local.
- MOB-B: comportamento ao fogo, abrasão (método e ciclos), instruções de limpeza, resistência ao escorregamento/aderência; tamanho comercial disponível versus 3,2 m × 5,2 m calculado.
- MOB-C: estabilidade, cantos, acabamento e limpeza da superfície; cargas não críticas.
- MOB-D: estabilidade, acabamento do tampo e limpeza; cargas de uso; compatibilidade de altura com MOB-E.
- MOB-E: se estofadas, mesmos itens de MOB-A (fogo, abrasão, limpeza); estabilidade e carga.
- MOB-F: estabilidade (peso da base, risco de tombamento), fixação se necessária, certificação elétrica e comprimento de cabo; pontos elétricos no projeto.
- MOB-G: comportamento ao fogo e instruções de lavagem do tecido; carga e fixação do trilho/suportes na alvenaria ou forro.
- MOB-H: estado de conservação, necessidade de reparo ou limpeza, estabilidade; sem ficha técnica de fabricante (peça existente) — verificar no local.
- RES-1: não aplicável (reserva financeira).
O profissional responsável confere as regras aplicáveis.
Anonimize os dados do cliente e use apenas ferramenta aprovada pelo escritório.

PERGUNTAS PARA O CLIENTE
- O tapete deve cobrir todo o ambiente (3,2 m × 5,2 m) ou apenas a área de estar? Qual a divisão prevista entre estar e jantar?
- Confirma a premissa de alocação do orçamento (28/10/6/14/18/6/8/10%) ou há verbas já definidas por peça?
- O orçamento inclui serviços no aparador, instalação elétrica das luminárias e do trilho da cortina?
- Aparador existente: medidas, estado de conservação, necessidade de reparo/limpeza/transporte; a tonalidade da madeira de demolição é aceitável frente à preferência por madeira clara?
- As 6 cadeiras serão estofadas (e portanto sujeitas ao prazo de 6 a 8 semanas)?
- Prazo de 6 a 8 semanas: semanas corridas ou úteis, contadas a partir de quê (confirmação, pagamento, aprovação de tecido)? Confirma a margem de 2 semanas?
- Prazos dos fornecedores de tapete, mesas, luminárias e cortina?
- Posição de portas, acessos, pontos elétricos e altura/posição da janela; condições de acesso para entrega do sofá?
- Lado da chaise e medidas desejadas para sofá, mesa de centro e mesa de jantar?
- Confirma linho como tecido do sofá, mesmo com gatos que arranham, condicionado à verificação com o fabricante?

