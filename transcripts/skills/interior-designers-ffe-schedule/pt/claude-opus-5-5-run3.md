# Transcript — skill interior-designers-ffe-schedule [pt] — claude-opus-5-5 — run 3

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T07:07:07+00:00
- duration_s: 86.3
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
Sala de estar e jantar integrada, para o casal e dois gatos que arranham. Preferências: madeira clara e linho. Não há estilo nem paleta definidos além disso.

Dados recebidos: ambiente de 4,0 m × 6,0 m; pé-direito de 2,70 m; uma janela de 2,0 m de largura; tapete com 40 cm de piso aparente em cada lado; mesa de jantar para 6; 6 cadeiras; 2 luminárias de piso; aparador existente de madeira de demolição, a manter. Orçamento: R$ 85.000 com frete e montagem. Montagem: 1º de março de 2027. Prazo de fabricação dos estofados: 6 a 8 semanas. Localização: Recife.

Moradores e animais considerados: casal (2 adultos) e dois gatos que arranham. Requisitos derivados: tecidos de trama fechada e fácil limpeza, capas removíveis quando possível, estabilidade das peças altas e fixação do aparador. Todos esses pontos devem ser confirmados com o fabricante ou no projeto, sem garantia de resistência a unhas.

Excluído por preferência do cliente: branco puro; veludo.

Premissas:
- A largura de 4,0 m corresponde ao lado menor e o comprimento de 6,0 m ao lado maior.
- A divisão entre a zona de estar e a de jantar não foi informada.
- "Semanas" são semanas corridas de 7 dias.

## Lista de mobiliário e equipamentos
| Código | Item | Quantidade | Medida-alvo e conta | Material e desempenho a verificar | Verba estimada por linha | Pedir até / verificação de prazo | Situação |
|---|---|---|---|---|---|---|---|
| MOB-01 | Sofá de 3 lugares com chaise | 1 | [NÃO INFORMADO]. Lado da chaise, encaixe na zona de estar e circulação a verificar no projeto. Acesso (porta, escada, elevador) a verificar. | Sem veludo e sem branco puro. Linho é preferido, mas há conflito potencial com gatos que arranham (pendência): verificar com o fabricante trama, abrasão e capas removíveis. | Premissa de alocação: R$ 25.500,00 (total da linha = unitário) | 21/12/2026 (ver Controle de prazos) | nova |
| MOB-02 | Tapete | 1 | (4,0 m − 2 × 0,40 m) × (6,0 m − 2 × 0,40 m) = 3,2 m × 5,2 m. Dimensão calculada, não tamanho comercial: disponibilidade ou confecção sob medida a verificar. Pendência: a conta cobre o ambiente inteiro, incluindo a zona de jantar (cadeiras arrastando sobre o tapete). Confirmar se é um tapete único ou só para a zona de estar. | Sem veludo e sem branco puro. Verificar com o fabricante: fibra ou trama sem laçadas (gatos), facilidade de limpeza, base antiderrapante. | Premissa de alocação: R$ 10.200,00 | prazo [NÃO INFORMADO] | nova |
| MOB-03 | Mesa de centro | 1 | [NÃO INFORMADO]. Proporção com o sofá e circulação a verificar no projeto. | Madeira clara (preferência). Cantos arredondados e estabilidade a verificar. | Premissa de alocação: R$ 4.250,00 | prazo [NÃO INFORMADO] | nova |
| MOB-04 | Mesa de jantar para 6 | 1 | 6 lugares (dado recebido). Formato e dimensões [NÃO INFORMADO]. Encaixe e circulação ao redor a verificar no projeto. | Madeira clara (preferência). Acabamento resistente a riscos e de fácil limpeza a verificar com o fabricante. | Premissa de alocação: R$ 11.050,00 | prazo [NÃO INFORMADO] | nova |
| MOB-05 | Cadeiras de jantar | 6 | [NÃO INFORMADO]. Compatibilidade de altura com MOB-04 a verificar. | Madeira clara (preferência). Se estofadas: sem veludo e sem branco puro, assento com tecido de fácil limpeza e capa removível a verificar. | Premissa: R$ 15.300,00 total; R$ 15.300,00 ÷ 6 = R$ 2.550,00 por unidade | Se estofadas: 21/12/2026. Se não: prazo [NÃO INFORMADO] | nova |
| ILU-01 | Luminárias de piso | 2 | [NÃO INFORMADO]. Altura compatível com pé-direito de 2,70 m. Posição de tomadas a verificar no projeto. | Base pesada ou fixação contra tombamento por gatos a verificar com o fabricante. Cúpula sem branco puro. | Premissa: R$ 4.250,00 total; R$ 4.250,00 ÷ 2 = R$ 2.125,00 por unidade | prazo [NÃO INFORMADO] | nova |
| COR-01 | Cortina para a janela (com trilho ou varão) | 1 | Premissa: transpasse de 0,20 m por lado → 2,0 m + 2 × 0,20 m = 2,40 m de trilho. Premissa: instalação no teto → altura até 2,70 m (pé-direito), descontando a folga do piso, a verificar no local. Premissa: franzido 2× → 2,40 m × 2 = 4,80 m de largura de tecido. | Linho (preferência), cor que não seja branco puro. Sem veludo. Comportamento ao fogo, encolhimento e lavagem a verificar com o fabricante. Altura da barra fora do alcance de gatos a verificar no projeto. | Premissa de alocação: R$ 5.950,00 (inclui instalação, a confirmar) | prazo [NÃO INFORMADO] | nova |
| MOB-06 | Aparador de madeira de demolição | 1 | Medidas [NÃO INFORMADO]. Posição e encaixe a verificar no local. | Estado de conservação [NÃO INFORMADO]. Fixação à parede a verificar no projeto. Convivência com madeira clara a confirmar com o cliente. | Sem aquisição. Serviços (limpeza, reparo, transporte) [NÃO INFORMADO]. Premissa de alocação: R$ 1.700,00 | Prazo dos serviços [NÃO INFORMADO] | existente-reaproveitar |

Cobertura:
- Sofá → MOB-01
- Tapete → MOB-02
- Mesa de centro → MOB-03
- Mesa de jantar → MOB-04
- 6 cadeiras → MOB-05
- 2 luminárias de piso → ILU-01
- Cortina → COR-01
- Aparador existente → MOB-06

São 8 linhas, sem duplicidade. Conflitos registrados:
- Linho preferido versus gatos que arranham (MOB-01, COR-01).
- Tapete calculado sobre o ambiente inteiro versus zona de jantar (MOB-02).

## Controle de orçamento
Total informado pelo cliente: R$ 85.000.

Escopo do orçamento: com frete e montagem.

Premissa de alocação (cada parcela é verba estimada, a confirmar com orçamentos):
| Código | Conta | Verba |
|---|---|---|
| MOB-01 | R$ 85.000 × 30% | R$ 25.500,00 |
| MOB-02 | R$ 85.000 × 12% | R$ 10.200,00 |
| MOB-03 | R$ 85.000 × 5% | R$ 4.250,00 |
| MOB-04 | R$ 85.000 × 13% | R$ 11.050,00 |
| MOB-05 | R$ 85.000 × 18% | R$ 15.300,00 (R$ 2.550,00 por unidade × 6) |
| ILU-01 | R$ 85.000 × 5% | R$ 4.250,00 (R$ 2.125,00 por unidade × 2) |
| COR-01 | R$ 85.000 × 7% | R$ 5.950,00 |
| MOB-06 (serviços) | R$ 85.000 × 2% | R$ 1.700,00 |
| Frete e montagem (geral) | R$ 85.000 × 5% | R$ 4.250,00 |

Soma das verbas conhecidas:
R$ 25.500,00 + R$ 10.200,00 + R$ 4.250,00 + R$ 11.050,00 + R$ 15.300,00 + R$ 4.250,00 + R$ 5.950,00 + R$ 1.700,00 + R$ 4.250,00 = R$ 82.450,00 (97%).

Saldo: R$ 85.000,00 − R$ 82.450,00 = R$ 2.550,00. Este é um saldo provisório, não uma reserva disponível.

Custos ainda não incluídos ou desconhecidos:
- Preços reais de todas as peças.
- Frete e montagem reais por fornecedor.
- Serviços efetivos no aparador.
- Instalação elétrica ou tomadas para ILU-01, se necessárias.
- Confecção sob medida do tapete, se o tamanho comercial não atender.

Todas as verbas estimadas dependem de confirmação por orçamentos.

## Controle de prazos
Data de montagem: 1º de março de 2027.

Data de referência para a comparação: 21/10/2026 (data atual).

| Código | Prazo do fornecedor e base de contagem | Margem | Pedir até, com conta | Situação do prazo |
|---|---|---|---|---|
| MOB-01 | 6 a 8 semanas de fabricação (estofado). Premissa: semanas corridas; pior caso 8 × 7 = 56 dias. Não informado se a contagem começa no pedido, no sinal ou na aprovação do tecido. Frete fora desse prazo. | Premissa: 14 dias (frete, conferência, imprevistos) | 01/03/2027 − 56 − 14 = 01/03/2027 − 70 dias = 21/12/2026. Sem margem: 01/03/2027 − 56 = 04/01/2027. | Não vencido: faltam 61 dias a partir de 21/10/2026. Prazo não confirmado (início da contagem e frete). Tecido e medidas precisam estar aprovados antes. |
| MOB-02 | [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Prazo não confirmado |
| MOB-03 | [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Prazo não confirmado |
| MOB-04 | [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Prazo não confirmado |
| MOB-05 | Se estofadas: mesma regra de MOB-01 (6 a 8 semanas). Se não: [NÃO INFORMADO] | Premissa: 14 dias | Se estofadas: 01/03/2027 − 56 − 14 = 21/12/2026 | Prazo não confirmado (cadeiras estofadas?) |
| ILU-01 | [NÃO INFORMADO] | a definir | 01/03/2027 − prazo − margem | Prazo não confirmado |
| COR-01 | [NÃO INFORMADO] (confecção e instalação) | a definir | 01/03/2027 − prazo − margem | Prazo não confirmado |
| MOB-06 | Serviços e transporte [NÃO INFORMADO] | a definir | 01/03/2027 − prazo dos serviços − margem | Prazo não confirmado |

## Especificações a verificar
- MOB-01: na ficha técnica do tecido, verificar comportamento ao fogo, abrasão (método de ensaio e ciclos ou fricções duplas), código ou instruções de limpeza, capas removíveis e indicação de uso com animais. Verificar também a estrutura e a densidade da espuma. Resistência ao escorregamento não se aplica ao estofado; conferir apenas os pés e o apoio no piso.
- MOB-02: verificar comportamento ao fogo, abrasão (método e ciclos), instruções de limpeza, resistência ao escorregamento ou base antiderrapante, tamanho comercial disponível versus 3,2 m × 5,2 m, encaixe, circulação e acesso.
- MOB-03: verificar acabamento da madeira (riscos e limpeza), cantos arredondados e estabilidade. Abrasão têxtil não se aplica, salvo tampo revestido.
- MOB-04: verificar acabamento (riscos, umidade, limpeza), carga do tampo e estabilidade. Abrasão têxtil e fogo de tecido não se aplicam, salvo componentes estofados.
- MOB-05: verificar estabilidade e carga. Se estofadas: comportamento ao fogo, abrasão (método e ciclos), limpeza e capa removível. Verificar ponteiras que protejam o piso e não escorreguem.
- ILU-01: verificar estabilidade contra tombamento, fixação, carga e especificação elétrica, além do comportamento ao fogo da cúpula. Abrasão e escorregamento não se aplicam, exceto a base.
- COR-01: verificar comportamento ao fogo, instruções de lavagem e encolhimento, fixação e carga do trilho ou varão. Abrasão é secundária (atrito de gatos) e deve ser conferida se disponível. Escorregamento não se aplica.
- MOB-06: verificar estado da peça, tratamento da madeira (pragas, acabamento), fixação à parede e carga sobre o tampo. Fogo, abrasão e escorregamento não se aplicam a peça existente sem revestimento novo.

O profissional responsável confere as regras aplicáveis.
Anonimize os dados do cliente e use apenas ferramenta aprovada pelo escritório.

## Perguntas para o cliente
- O tapete de 3,2 m × 5,2 m (conta sobre o ambiente inteiro) deve cobrir também a zona de jantar, ou a borda de 40 cm vale só para a zona de estar? Nesse caso, quais são as medidas dessa zona?
- O linho continua sendo a escolha para sofá e cortina, considerando os gatos que arranham? Aceita avaliar um tecido de aspecto similar com melhor desempenho, conforme a ficha do fabricante?
- Qual lado é a largura (4,0 m) e qual o comprimento (6,0 m)? Como se dividem as zonas de estar e de jantar? Onde ficam a janela, as portas e as tomadas?
- Quais são as medidas da porta de entrada, do elevador e das escadas para o acesso do sofá?
- Prefere mesa de jantar retangular, redonda ou oval? Há medida desejada?
- As cadeiras serão estofadas? Isso altera o prazo, que passaria a seguir a regra de 6 a 8 semanas.
- O prazo de 6 a 8 semanas começa no pedido, no pagamento do sinal ou na aprovação do tecido? Inclui o frete?
- Aprova a margem de 14 dias e o pedido do sofá até 21/12/2026?
- Quais são os prazos dos fornecedores de tapete, mesas, cadeiras, luminárias e cortina?
- Aprova a premissa de alocação, incluindo R$ 4.250,00 para frete e montagem e o saldo provisório de R$ 2.550,00?
- Quais são as medidas e o estado do aparador? Ele precisa de reparo, limpeza ou transporte? A madeira de demolição combina com a madeira clara desejada?
- Para a cortina, confirma instalação no teto, transpasse de 0,20 m por lado e franzido 2×? Qual a altura da janela e a distância até o teto?
- Há preferência de cor, dado que branco puro está excluído?

