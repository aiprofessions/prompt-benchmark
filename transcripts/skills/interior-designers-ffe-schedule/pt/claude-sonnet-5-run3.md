# Transcript — skill interior-designers-ffe-schedule [pt] — claude-sonnet-5 — run 3

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-21T07:18:24+00:00
- duration_s: 188.0
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

Cliente: casal (dados fictícios), Recife.
Ambiente: sala de estar e jantar integrada, 4,0 m × 6,0 m, pé-direito 2,70 m, uma janela de 2,0 m de largura.

Dados recebidos (preservados como informados):
- Sofá de 3 lugares com chaise — 1 un.
- Tapete, deixando 0,40 m de piso aparente em cada lado.
- Mesa de centro — 1 un.
- Mesa de jantar para 6 — 1 un.
- 6 cadeiras.
- 2 luminárias de piso.
- Cortina para a janela (largura do vão: 2,0 m).
- Existente: aparador de madeira de demolição — manter.
- Orçamento: R$ 85.000,00, incluindo frete e montagem.
- Montagem: 1º de março de 2027.
- Prazo de fabricação dos estofados (segundo fornecedores do escritório): 6 a 8 semanas.

Moradores e animais considerados: casal e dois gatos que arranham — relevante para resistência do estofado do sofá (e das cadeiras, se estofadas), fibra do tapete e altura/fixação da cortina.

Excluído por preferência do cliente: branco puro; veludo. Nenhuma linha abaixo propõe esses materiais/cores.

Preferências a observar (sem inventar especificação): madeira clara; linho.

Premissa: para efeito de cálculo de prazo (seção "Controle de prazos"), adoto margem de segurança de 2 semanas entre o prazo do fornecedor e a data de montagem — premissa de planejamento, a confirmar.

Premissa: para a cortina, considero premissa de planejamento que trilhos/varões costumam exceder a largura do vão em cerca de 0,20 m de cada lado para permitir abertura total — não é dado confirmado, apenas prática comum de projeto, a validar com o fornecedor.

LISTA DE MOBILIÁRIO E EQUIPAMENTOS

Código | Item | Quantidade | Medida-alvo e conta | Material e desempenho a verificar | Verba estimada por linha | Pedir até / verificação de prazo | Situação
---|---|---|---|---|---|---|---
MOB-A | Sofá 3 lugares com chaise | 1 | [NÃO INFORMADO] — dimensões do sofá não recebidas; verificar encaixe no ambiente de 4,0 m × 6,0 m e circulação ao redor no projeto | Sem veludo; tecido com preferência por linho (a confirmar); resistência ao uso com gatos — verificar com fabricante; sem branco puro | R$ 23.800,00 (85.000 × 0,28), premissa de alocação, a confirmar com orçamentos | Prazo de estofados 6–8 semanas (dado do fornecedor); ver tabela de prazos | nova
MOB-B | Tapete | 1 | Ambiente total 4,0 m × 6,0 m; borda de 0,40 m por lado: (4,0 − 2×0,40) × (6,0 − 2×0,40) = 3,20 m × 5,20 m (resultado teórico sobre o ambiente total). Ressalva: ambiente reúne estar e jantar; subdimensão da área de estar não informada — tamanho final pode ser menor | Sem veludo; fibra resistente a arranhões e fácil limpeza — verificar com fabricante; resistência ao escorregamento a verificar na ficha técnica | R$ 8.500,00 (85.000 × 0,10), premissa de alocação | Prazo do fornecedor [NÃO INFORMADO] | nova
MOB-C | Mesa de centro | 1 | [NÃO INFORMADO] — depende das dimensões do sofá (não informadas) | Madeira clara (preferência do cliente); sem branco puro, sem veludo; cantos a verificar dado uso com gatos | R$ 4.250,00 (85.000 × 0,05), premissa de alocação | Prazo do fornecedor [NÃO INFORMADO] | nova
MOB-D | Mesa de jantar para 6 | 1 | [NÃO INFORMADO] — dimensão comercial não recebida; verificar circulação para 6 cadeiras no projeto | Madeira clara (preferência); carga e estabilidade — verificar ficha técnica | R$ 10.200,00 (85.000 × 0,12), premissa de alocação | Prazo do fornecedor [NÃO INFORMADO] | nova
MOB-E | Cadeiras | 6 | [NÃO INFORMADO] — dimensão e revestimento não informados | Se estofadas: sem veludo, resistência a gatos a verificar; se não estofadas: madeira clara (preferência); estabilidade e carga — verificar ficha técnica | R$ 12.750,00 total (85.000 × 0,15); R$ 2.125,00 por unidade (12.750 ÷ 6), premissa de alocação | Se estofadas, pode seguir prazo 6–8 semanas dos estofados — a confirmar; senão [NÃO INFORMADO] | nova
MOB-F | Luminárias de piso | 2 | [NÃO INFORMADO] — altura compatível com pé-direito de 2,70 m a verificar no projeto | Estabilidade/tombamento (uso com gatos) — verificar fixação e base na ficha técnica; comportamento ao fogo a verificar | R$ 5.100,00 total (85.000 × 0,06); R$ 2.550,00 por unidade (5.100 ÷ 2), premissa de alocação | Prazo do fornecedor [NÃO INFORMADO] | nova
MOB-G | Cortina (janela de 2,0 m) | 1 (jogo) | Largura do vão: 2,0 m (dado). Premissa de planejamento: folga lateral de ~0,20 m por lado para trilho → 2,0 + 0,40 = 2,40 m de trilho (estimativa, a confirmar). Altura: pé-direito 2,70 m é referência, mas altura da janela e decisão piso-teto ou só vão não foram informadas — altura final [NÃO INFORMADO] | Sem veludo; preferência por linho (a confirmar); bainha/altura a verificar quanto ao acesso dos gatos; comportamento ao fogo a verificar | R$ 5.100,00 (85.000 × 0,06), premissa de alocação | Prazo do fornecedor [NÃO INFORMADO] | nova
MOB-H | Aparador de madeira de demolição (existente) | 1 | [NÃO INFORMADO] — medidas e estado de conservação não informados | Estabilidade; verificar presença de cupim/pragas na madeira de demolição; harmonização com preferência por "madeira clara" das peças novas — pendência de compatibilidade estética, não é rejeição explícita do cliente | R$ 2.550,00 (85.000 × 0,03) reservado para eventuais serviços (transporte/limpeza/restauro), premissa de alocação; sem aquisição | Prazo de serviços [NÃO INFORMADO] | existente-reaproveitar (decisão do cliente: manter)

Cobertura: todos os itens solicitados (sofá, tapete, mesa de centro, mesa de jantar, 6 cadeiras, 2 luminárias, cortina) e a peça existente (aparador) estão relacionados, um código cada, sem duplicação. Pendências de medida afetam MOB-A a MOB-G (nenhuma dimensão de produto foi informada no briefing, apenas as do ambiente e da janela); MOB-B tem cálculo apresentado com ressalva por falta de subdimensão da zona de estar; MOB-H tem decisão de destino definida ("manter"), mas falta medida e estado de conservação.

CONTROLE DE ORÇAMENTO

Total informado pelo cliente: R$ 85.000,00.
Escopo do orçamento: aquisição + frete + montagem (informado explicitamente pelo cliente).

Verbas fornecidas: nenhuma verba por item foi fornecida pelo cliente. Premissa de alocação proposta (estimada, a confirmar com orçamentos):
- MOB-A Sofá: 28% → 85.000 × 0,28 = R$ 23.800,00
- MOB-D Mesa de jantar: 12% → 85.000 × 0,12 = R$ 10.200,00
- MOB-E Cadeiras (6 un): 15% → 85.000 × 0,15 = R$ 12.750,00 (R$ 2.125,00/unidade)
- MOB-B Tapete: 10% → 85.000 × 0,10 = R$ 8.500,00
- MOB-C Mesa de centro: 5% → 85.000 × 0,05 = R$ 4.250,00
- MOB-F Luminárias (2 un): 6% → 85.000 × 0,06 = R$ 5.100,00 (R$ 2.550,00/unidade)
- MOB-G Cortina: 6% → 85.000 × 0,06 = R$ 5.100,00
- Frete e montagem (geral, todos os itens novos): 10% → 85.000 × 0,10 = R$ 8.500,00
- MOB-H Aparador existente (serviços eventuais): 3% → 85.000 × 0,03 = R$ 2.550,00
- Contingência/saldo: 5% → 85.000 × 0,05 = R$ 4.250,00

Soma das verbas conhecidas: 23.800 + 10.200 + 12.750 + 8.500 + 4.250 + 5.100 + 5.100 + 8.500 + 2.550 + 4.250 = R$ 85.000,00.

Saldo ou excedente: 85.000,00 − 85.000,00 = R$ 0,00 (saldo provisório, pois a alocação já reserva 5% de contingência; os valores reais dependem de cotações, já que nenhuma dimensão ou especificação de produto foi confirmada — variações de preço podem consumir ou exceder a contingência).

Custos ainda não incluídos ou desconhecidos: eventual restauro/tratamento contra pragas do aparador de demolição; possíveis acessórios de cortina (trilho, argolas, forro) além do estimado; eventual necessidade de segunda peça de tapete para a área de jantar, caso confirmado que o tapete solicitado é só para a área de estar.

Todas as verbas estimadas dependem de confirmação por orçamentos.

CONTROLE DE PRAZOS

Data de montagem: 1º de março de 2027 (01/03/2027).

Código | Prazo do fornecedor e base de contagem | Margem | Pedir até, com conta | Situação do prazo
---|---|---|---|---
MOB-A | 6 a 8 semanas (dado do fornecedor); base de contagem (dias corridos ou úteis) [NÃO INFORMADO] — assumo dias corridos como premissa | 2 semanas (premissa) | Cenário conservador (8 semanas + 2 semanas margem = 10 semanas = 70 dias corridos): 01/03/2027 − 70 dias = 21/12/2026. Cenário mínimo (6 semanas + 2 semanas margem = 8 semanas = 56 dias corridos): 01/03/2027 − 56 dias = 04/01/2027 | Recomenda-se usar a data mais conservadora (21/12/2026) como "pedir até". Hoje (referência: 21/10/2026) é anterior a essa data — pedido ainda não vencido; restam cerca de 61 dias corridos até o limite conservador
MOB-E | Se estofadas, possivelmente mesmo prazo de MOB-A — a confirmar; se não estofadas, prazo [NÃO INFORMADO] | 2 semanas (premissa), se aplicável | Mesma fórmula de MOB-A, condicionada à confirmação do revestimento | Prazo não confirmado até definição do material
MOB-B, MOB-C, MOB-D, MOB-F, MOB-G | Prazo do fornecedor [NÃO INFORMADO] | [NÃO INFORMADO] | Fórmula: pedir até = 01/03/2027 − prazo do fornecedor − margem; não é possível calcular data sem o prazo | Prazo não confirmado
MOB-H | Prazo de serviços (transporte/eventual restauro) [NÃO INFORMADO] | [NÃO INFORMADO] | Mesma fórmula; peça existente também precisa de prazo quando há transporte/serviço associado | Prazo não confirmado

ESPECIFICAÇÕES A VERIFICAR

- MOB-A: verificar na ficha técnica comportamento ao fogo, abrasão (método de ensaio e ciclos/fricções duplas), código de limpeza do tecido e, dado o uso com gatos, resistência ao desfiamento — não garantir resistência a unhas como fato.
- MOB-B: verificar comportamento ao fogo, resistência à abrasão, código de limpeza e resistência ao escorregamento; confirmar disponibilidade comercial do tamanho calculado (3,20 m × 5,20 m é valor teórico sobre o ambiente total, não necessariamente tamanho de catálogo).
- MOB-C: verificar estabilidade, cantos (uso com gatos) e carga suportada; comportamento ao fogo de acabamentos se aplicável.
- MOB-D: verificar estabilidade, carga, comportamento ao fogo de acabamentos e circulação mínima em torno da mesa no projeto.
- MOB-E: verificar estabilidade, carga e, se estofadas, os mesmos itens de tecido do MOB-A.
- MOB-F: verificar estabilidade/tombamento (relevante com gatos), fixação de base, comportamento ao fogo e compatibilidade elétrica (tomada disponível) — não aplicável a classificações de incêndio específicas sem dado do fabricante.
- MOB-G: verificar comportamento ao fogo do tecido, código de limpeza e disponibilidade de trilho na largura calculada; não aplicável resistência à abrasão por fricção dupla tipicamente (verificar se o fabricante classifica).
- MOB-H: verificar estabilidade da peça existente, presença de pragas/cupim na madeira de demolição e compatibilidade estrutural para suportar objetos, se houver essa função.

O profissional responsável confere as regras aplicáveis.
Anonimize os dados do cliente e use apenas ferramenta aprovada pelo escritório.

PERGUNTAS PARA O CLIENTE

- Quais as dimensões do sofá (comprimento total e da chaise)? Sem isso não é possível calcular encaixe no ambiente nem a medida da mesa de centro.
- O tapete solicitado é destinado apenas à área de estar (sob o sofá), ou também à área de jantar? Qual a subdimensão da zona de estar dentro do ambiente de 4,0 m × 6,0 m? O cálculo atual (3,20 m × 5,20 m) usa o ambiente total e pode estar sobredimensionado.
- Quais as dimensões desejadas/comerciais da mesa de jantar e das 6 cadeiras?
- As 6 cadeiras são estofadas? Se sim, aplicam-se o mesmo prazo de 6 a 8 semanas dos estofados do sofá?
- Qual a altura da janela e a decisão de instalação da cortina (do piso ao teto ou apenas no vão)? Sem isso não é possível calcular a altura do tecido, mesmo com o pé-direito de 2,70 m informado.
- Confirma a margem de segurança de 2 semanas adotada como premissa no cálculo de "pedir até" para os estofados? A contagem do prazo de 6–8 semanas é em dias corridos ou úteis?
- Quais os prazos de fabricação/entrega da mesa de centro, mesa de jantar, cadeiras, luminárias, cortina e tapete?
- Confirma a alocação proposta por categoria do orçamento de R$ 85.000,00, ou deseja outra distribuição entre os itens?
- Para o aparador existente: quais as medidas, o estado de conservação e os serviços desejados (apenas transporte, limpeza, ou também restauro)? A tonalidade da madeira de demolição (normalmente mais rústica/escura) deve harmonizar com a preferência por "madeira clara" das peças novas, ou é aceita como contraste proposital?
- Há tomadas disponíveis na posição planejada para as 2 luminárias de piso?
- A parede/teto permite fixação de trilho de cortina considerando a folga lateral estimada (premissa de 0,20 m por lado)?

