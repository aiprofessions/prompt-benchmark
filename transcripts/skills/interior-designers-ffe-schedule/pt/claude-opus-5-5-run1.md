# Transcript — skill interior-designers-ffe-schedule [pt] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:01:16+00:00
- duration_s: 95.7
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

Uso: sala de estar e jantar integrada para o casal e dois gatos que arranham.
Preferências: madeira clara e linho.
Dados recebidos: ambiente de 4,0 m × 6,0 m (área = 4,0 × 6,0 = 24,0 m²); pé-direito de 2,70 m; uma janela de 2,0 m de largura. Acessos, portas, posição da janela e áreas de circulação: [NÃO INFORMADO].
Moradores e animais considerados: casal; dois gatos que arranham. Isso exige verificar resistência a arranhões e puxões, limpeza, capas removíveis e estabilidade das peças.
Excluído por preferência do cliente: branco puro; veludo.
Premissa: a borda de 40 cm do tapete é medida a partir das paredes do ambiente inteiro (4,0 m × 6,0 m).
Premissa: cada verba por linha inclui frete e montagem do item, porque o orçamento total os inclui.


LISTA DE MOBILIÁRIO E EQUIPAMENTOS

MOB-01  Sofá de 3 lugares com chaise
  Quantidade: 1
  Medida-alvo: [NÃO INFORMADO]. Verificar no projeto a parede de apoio, o lado da chaise, a circulação e a passagem pelo acesso.
  Material e desempenho a verificar: sem veludo e sem branco puro. Se o cliente quiser linho, verificar com o fabricante o comportamento frente a unhas de gatos (pendência). Verificar também capa removível e limpeza.
  Verba: R$ 25.500,00 (premissa de alocação).
  Pedir até: 21/12/2026, como data de planejamento não confirmada (ver Controle de prazos).
  Situação: nova

MOB-02  Tapete
  Quantidade: 1
  Medida-alvo: (4,0 m − 2 × 0,40 m) × (6,0 m − 2 × 0,40 m) = 3,2 m × 5,2 m (16,64 m²). Esta é a dimensão calculada, não um tamanho comercial disponível. Pendência: nessa medida o tapete ocupa também a área de jantar. Confirmar se ele deve cobrir só o estar.
  Material e desempenho a verificar: sem veludo e sem branco puro. Verificar se a trama solta laçadas com as unhas dos gatos, a facilidade de limpeza e a base antiderrapante.
  Verba: R$ 8.500,00 (premissa).
  Pedir até: prazo [NÃO INFORMADO].
  Situação: nova

MOB-03  Mesa de centro
  Quantidade: 1
  Medida-alvo: [NÃO INFORMADO]. Verificar a circulação em relação ao MOB-01.
  Material e desempenho a verificar: madeira clara (preferência). Verificar o acabamento quanto a riscos e a estabilidade.
  Verba: R$ 4.250,00 (premissa).
  Pedir até: prazo [NÃO INFORMADO].
  Situação: nova

MOB-04  Mesa de jantar para 6
  Quantidade: 1
  Medida-alvo: [NÃO INFORMADO]. Verificar no projeto o espaço para 6 lugares com as cadeiras afastadas e a circulação.
  Material e desempenho a verificar: madeira clara (preferência). Verificar o acabamento quanto a riscos e a limpeza.
  Verba: R$ 12.750,00 (premissa).
  Pedir até: prazo [NÃO INFORMADO].
  Situação: nova

MOB-05  Cadeiras de jantar
  Quantidade: 6
  Medida-alvo: [NÃO INFORMADO]. Verificar o encaixe sob o MOB-04.
  Material e desempenho a verificar: se forem estofadas, sem veludo e sem branco puro. Verificar resistência a arranhões e limpeza, ou estofado removível.
  Verba: R$ 12.750,00 total por linha (R$ 12.750,00 ÷ 6 = R$ 2.125,00 por unidade, premissa).
  Pedir até: se forem estofadas, mesma base do MOB-01. Caso contrário, prazo [NÃO INFORMADO].
  Situação: nova

MOB-06  Luminárias de piso
  Quantidade: 2
  Medida-alvo: altura [NÃO INFORMADO], com limite pelo pé-direito de 2,70 m. Verificar a posição em relação às tomadas.
  Material e desempenho a verificar: verificar estabilidade contra tombamento (gatos), base pesada ou fixação e proteção dos cabos.
  Verba: R$ 5.100,00 total por linha (R$ 5.100,00 ÷ 2 = R$ 2.550,00 por unidade, premissa).
  Pedir até: prazo [NÃO INFORMADO].
  Situação: nova

MOB-07  Cortina para a janela
  Quantidade: 1 conjunto (premissa)
  Medida-alvo: largura = 2,0 m + transpasses laterais [NÃO INFORMADO]. Altura: premissa de cortina do teto ao piso, até 2,70 m menos as folgas de trilho e piso [NÃO INFORMADO]. Verificar no local.
  Material e desempenho a verificar: sem veludo e sem branco puro. Linho é preferência: verificar com o fabricante o comportamento a puxões e unhas, a limpeza e a fixação do trilho ou varão.
  Verba: R$ 5.950,00, incluindo trilho e instalação (premissa).
  Pedir até: prazo [NÃO INFORMADO].
  Situação: nova

MOB-08  Aparador de madeira de demolição
  Quantidade: 1
  Medida-alvo: medidas da peça [NÃO INFORMADO]. Verificar a parede de destino.
  Material e desempenho a verificar: estado de conservação [NÃO INFORMADO]. Verificar estabilidade e fixação à parede, já que gatos podem subir.
  Verba: sem aquisição; serviços (limpeza, reparo, transporte, fixação) [NÃO INFORMADO].
  Pedir até: serviços e prazo [NÃO INFORMADO].
  Situação: existente-reaproveitar (cliente: "manter")

Cobertura: sofá → MOB-01; tapete → MOB-02; mesa de centro → MOB-03; mesa de jantar → MOB-04; 6 cadeiras → MOB-05; 2 luminárias → MOB-06; cortina → MOB-07; aparador existente → MOB-08. São 8 linhas, sem duplicidade.
Conflitos:
  - MOB-02: a medida calculada cobre também o jantar.
  - MOB-01 e MOB-07: o linho (preferência) precisa ser compatibilizado com os gatos que arranham.
  - MOB-05: não está definido se as cadeiras são estofadas.


CONTROLE DE ORÇAMENTO

Total informado pelo cliente: R$ 85.000.
Escopo do orçamento: com frete e montagem. Inclusão de instalação de cortina e de serviços no aparador: [NÃO INFORMADO].

Premissa de alocação (verba estimada, a confirmar com orçamentos):
  MOB-01: 85.000 × 30% = R$ 25.500,00
  MOB-02: 85.000 × 10% = R$ 8.500,00
  MOB-03: 85.000 × 5% = R$ 4.250,00
  MOB-04: 85.000 × 15% = R$ 12.750,00
  MOB-05: 85.000 × 15% = R$ 12.750,00 (R$ 2.125,00 por unidade)
  MOB-06: 85.000 × 6% = R$ 5.100,00 (R$ 2.550,00 por unidade)
  MOB-07: 85.000 × 7% = R$ 5.950,00
  MOB-08: [NÃO INFORMADO]

Soma das verbas estimadas: 25.500 + 8.500 + 4.250 + 12.750 + 12.750 + 5.100 + 5.950 = R$ 74.800,00 (88%).
Saldo provisório: 85.000,00 − 74.800,00 = R$ 10.200,00 (12%). Não é reserva disponível, porque há custos desconhecidos.
Custos ainda não incluídos ou desconhecidos: serviços do MOB-08; frete e montagem reais de cada item; eventual ponto elétrico para o MOB-06; trilho ou varão do MOB-07, caso excedam a premissa.
Todas as verbas estimadas dependem de confirmação por orçamentos.


CONTROLE DE PRAZOS

Data de montagem: 1º de março de 2027.
Data de referência: 21/10/2026.

MOB-01 (estofado)
  Prazo do fornecedor: 6 a 8 semanas de fabricação. Premissa: semanas corridas, contadas a partir do pedido confirmado, sem incluir a entrega.
  Margem: premissa de 14 dias (entrega, frete, imprevistos).
  Pedir até: 01/03/2027 − 56 dias (8 semanas, pior caso) − 14 dias = 01/03/2027 − 70 dias = 21/12/2026. Sem margem: 01/03/2027 − 56 = 04/01/2027 (8 semanas) e 01/03/2027 − 42 = 18/01/2027 (6 semanas).
  Situação: não vencido em 21/10/2026. Prazo não confirmado, porque o início da contagem, a inclusão da entrega e os recessos não foram confirmados.

MOB-05
  Prazo: se as cadeiras forem estofadas, 6 a 8 semanas (mesma premissa). Caso contrário, [NÃO INFORMADO].
  Margem: 14 dias (premissa).
  Pedir até: se estofadas, 21/12/2026 (mesma conta do MOB-01). Caso contrário, montagem − prazo − margem.
  Situação: não confirmado.

MOB-02, MOB-03, MOB-04, MOB-06 e MOB-07
  Prazo e base de contagem: [NÃO INFORMADO].
  Margem: a definir.
  Pedir até: 01/03/2027 − prazo − margem.
  Situação: não confirmado.

MOB-08 (serviços e transporte)
  Prazo e base de contagem: [NÃO INFORMADO].
  Margem: a definir.
  Pedir até: 01/03/2027 − prazo do serviço − margem.
  Situação: não confirmado.


ESPECIFICAÇÕES A VERIFICAR

MOB-01: Verificar na ficha técnica:
  - comportamento ao fogo;
  - abrasão (método de ensaio e ciclos ou fricções duplas);
  - código ou instruções de limpeza;
  - resistência a arranhões, verificando com o fabricante;
  - capa removível;
  - estrutura e cargas.
  Resistência ao escorregamento não se aplica, pois não é superfície de piso.

MOB-02: Verificar:
  - tamanho comercial disponível versus 3,2 m × 5,2 m;
  - comportamento ao fogo;
  - abrasão (método e ciclos);
  - limpeza;
  - resistência ao escorregamento ou base antiderrapante;
  - formação de laçadas com as unhas dos gatos.

MOB-03: Verificar:
  - acabamento da madeira (riscos, limpeza);
  - estabilidade;
  - acabamento das bordas.
  Comportamento ao fogo e abrasão têxtil só se aplicam se houver revestimento têxtil. Escorregamento não se aplica.

MOB-04: Verificar:
  - acabamento (riscos, limpeza);
  - estabilidade;
  - carga do tampo.
  Abrasão têxtil e escorregamento não se aplicam.

MOB-05: Verificar:
  - cargas e estabilidade;
  - sapatas protetoras do piso.
  Se estofadas, verificar também comportamento ao fogo, abrasão (método e ciclos), limpeza e resistência a arranhões com o fabricante.

MOB-06: Verificar:
  - estabilidade contra tombamento;
  - fixação ou base;
  - características elétricas e cabos;
  - limpeza;
  - comportamento ao fogo da cúpula, se for têxtil.
  Abrasão e escorregamento não se aplicam.

MOB-07: Verificar:
  - comportamento ao fogo do tecido;
  - limpeza (lavável ou não);
  - resistência a puxões;
  - cor diferente de branco puro;
  - fixação e carga do trilho ou varão.
  Escorregamento não se aplica.

MOB-08: Verificar:
  - estado, acabamento e tratamento da madeira de demolição;
  - estabilidade e fixação à parede;
  - carga sobre o tampo.
  Comportamento ao fogo têxtil, abrasão e escorregamento não se aplicam, pois é peça existente sem revestimento têxtil informado.

O profissional responsável confere as regras aplicáveis.
Anonimize os dados do cliente e use apenas ferramenta aprovada pelo escritório.


PERGUNTAS PARA O CLIENTE

- O tapete deve cobrir o ambiente inteiro (3,2 m × 5,2 m) ou apenas a área de estar? Nesse caso, quais são as medidas dessa área?
- Considerando os gatos que arranham, o linho continua desejado no sofá e na cortina, ou aceitam outro tecido com desempenho comprovado pelo fabricante?
- As cadeiras de jantar serão estofadas?
- Quais são as medidas, o estado e a posição pretendida do aparador de madeira de demolição? Ele precisa de limpeza, reparo, transporte ou fixação, e há orçamento para isso?
- Medidas desejadas ou limites para o sofá (lado da chaise), a mesa de centro, a mesa de jantar e as luminárias?
- Qual é a posição da janela e das portas e qual o acesso para entrada dos móveis (largura de portas, elevador, escadas)?
- A cortina vai do teto ao piso? Há trilho ou varão existente?
- Confirmam a premissa de alocação do orçamento e que cada verba inclui frete e montagem do item?
- As 6 a 8 semanas dos estofados contam a partir de quê (pedido, pagamento, aprovação do tecido)? Incluem a entrega? Qual margem adotar e há recessos no período?
- Quais são os prazos dos fornecedores para tapete, mesas, cadeiras, luminárias e cortina, e com que base de contagem?
- Há pontos elétricos próximos aos locais previstos para as luminárias de piso?

