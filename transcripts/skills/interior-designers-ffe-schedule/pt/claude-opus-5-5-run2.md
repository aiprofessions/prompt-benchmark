# Transcript — skill interior-designers-ffe-schedule [pt] — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:34:27+00:00
- duration_s: 96.1
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
Sala de estar e jantar integradas para um casal com dois gatos que arranham. Preferências informadas: madeira clara e linho. Não foram informados estilo ou paleta além disso.

Dados recebidos:
- Ambiente: 4,0 m × 6,0 m; pé-direito 2,70 m; uma janela de 2,0 m de largura.
- Peças: sofá de 3 lugares com chaise; tapete deixando 40 cm de piso aparente em cada lado; mesa de centro; mesa de jantar para 6; 6 cadeiras; 2 luminárias de piso; cortina para a janela.
- Existente: aparador de madeira de demolição, a manter.
- Orçamento: R$ 85.000 com frete e montagem.
- Montagem: 1º de março de 2027.
- Prazo de fabricação dos estofados, segundo os fornecedores: 6 a 8 semanas.
- Local informado: Recife.
- Não informados: portas, acessos, posição da janela, áreas de circulação e medidas do aparador.

Moradores e animais considerados: casal e dois gatos que arranham. Requisitos: facilidade de limpeza, capas removíveis, tecidos e superfícies de menor vulnerabilidade a unhas e estabilidade das peças leves. Tudo deve ser verificado com o fabricante e no projeto.

Excluído por preferência do cliente: branco puro; veludo.

Premissas:
- O aparador permanece no ambiente. Sua posição e medidas são [NÃO INFORMADO].
- "Estofados" abrange o sofá. As cadeiras só entram nesse prazo se forem estofadas, o que é [NÃO INFORMADO].

## Lista de mobiliário e equipamentos
| Código | Item | Quantidade | Medida-alvo e conta | Material e desempenho a verificar | Verba estimada por linha | Pedir até / verificação de prazo | Situação |
|---|---|---|---|---|---|---|---|
| MOB-01 | Sofá de 3 lugares com chaise | 1 | [NÃO INFORMADO]. Definir no layout. Verificar circulação no ambiente de 4,0 m × 6,0 m, lado da chaise e passagem por portas, elevador e escada. | Sem veludo e sem branco puro. Tecido de trama fechada, sem laçadas, com capas removíveis: verificar com o fabricante. Linho foi pedido, mas o comportamento sob arranhões de gatos é pendência a verificar. Estrutura em madeira clara, se aplicável. | R$ 25.500,00 (premissa de alocação, a confirmar com orçamentos) | Estofado: 6 a 8 semanas. Pedir até 04/01/2027 (cenário de 6 semanas) ou 21/12/2026 (cenário de 8 semanas), com premissas. Ver Controle de prazos. Prazo não confirmado. | nova |
| MOB-02 | Tapete | 1 | 40 cm = 0,40 m. (4,0 m − 2 × 0,40 m) × (6,0 m − 2 × 0,40 m) = 3,2 m × 5,2 m. Dimensão calculada, não tamanho comercial. Pendência: com borda em todos os lados, o tapete cobre estar e jantar ao mesmo tempo. Verificar no projeto se é um tapete único ou se cada área terá o seu. | Sem veludo e sem branco puro. Construção sem laçadas, para reduzir o risco de os gatos puxarem fios: verificar com o fabricante. Limpeza, antiderrapante e altura do pelo sob as cadeiras: verificar. Disponibilidade sob medida a verificar. | R$ 8.500,00 (premissa de alocação, a confirmar) | Prazo [NÃO INFORMADO]. Fórmula: 01/03/2027 − prazo − margem. Prazo não confirmado. | nova |
| MOB-03 | Mesa de centro | 1 | [NÃO INFORMADO]. Definir no layout em relação ao sofá e à chaise. Circulação a verificar no projeto. | Madeira clara (preferência). Sem branco puro. Cantos arredondados: verificar no projeto. Acabamento resistente a riscos: verificar com o fabricante. | R$ 4.250,00 (premissa de alocação, a confirmar) | Prazo [NÃO INFORMADO]. Fórmula: 01/03/2027 − prazo − margem. Não confirmado. | nova |
| MOB-04 | Mesa de jantar para 6 | 1 | [NÃO INFORMADO]. Dimensionar para 6 lugares com afastamento das cadeiras e circulação: verificar no projeto. | Madeira clara (preferência). Sem branco puro. Acabamento do tampo quanto a riscos e limpeza: verificar com o fabricante. | R$ 12.750,00 (premissa de alocação, a confirmar) | Prazo [NÃO INFORMADO]. Fórmula: 01/03/2027 − prazo − margem. Não confirmado. | nova |
| MOB-05 | Cadeiras de jantar | 6 | [NÃO INFORMADO]. Compatibilizar altura e largura com a MOB-04: verificar no projeto. | Madeira clara (preferência). Sem veludo e sem branco puro. Se estofadas: tecido de trama fechada e assento removível ou lavável, a verificar com o fabricante. Deslizamento sobre o tapete: verificar. | R$ 2.125,00 por unidade × 6 = R$ 12.750,00 (premissa de alocação, a confirmar) | Se estofadas: 6 a 8 semanas, ver Controle de prazos. Se não: prazo [NÃO INFORMADO]. Não confirmado. | nova |
| MOB-06 | Luminárias de piso | 2 | [NÃO INFORMADO]. Altura máxima de referência: pé-direito de 2,70 m. Posição e tomadas: verificar no projeto. | Sem branco puro. Base estável ou fixação contra tombamento por gatos, cabos protegidos e cúpula sem tecido de veludo: verificar com o fabricante e no projeto. | R$ 2.125,00 por unidade × 2 = R$ 4.250,00 (premissa de alocação, a confirmar) | Prazo [NÃO INFORMADO]. Fórmula: 01/03/2027 − prazo − margem. Não confirmado. | nova |
| MOB-07 | Cortina para a janela | 1 | Janela: 2,0 m de largura. Altura de referência: pé-direito de 2,70 m. Transpasse lateral, altura do trilho ou varão e distância do piso: [NÃO INFORMADO], a medir no local. | Linho (preferência), sem branco puro e sem veludo. Lavagem e encolhimento, comportamento ao sol e resistência a gatos que se penduram ou arranham: verificar com o fabricante. Fixação e carga do trilho ou varão: verificar no projeto. | R$ 5.100,00, incluindo trilho ou varão e instalação (premissa de alocação, a confirmar) | Prazo de confecção e instalação [NÃO INFORMADO]. Fórmula: 01/03/2027 − prazo − margem. Não confirmado. | nova |
| EX-01 | Aparador de madeira de demolição | 1 | Medidas [NÃO INFORMADO]. Posição no layout a verificar no projeto. | Avaliar estado, limpeza, eventual reparo do acabamento e fixação à parede, considerando os gatos. Harmonia com a madeira clara das demais peças: verificar no projeto. | Sem aquisição; serviços [NÃO INFORMADO]. Sem verba alocada. | Serviços e transporte, se houver: prazo [NÃO INFORMADO]. Não confirmado. | existente-reaproveitar |

Cobertura:
- Sofá: MOB-01. Tapete: MOB-02. Mesa de centro: MOB-03. Mesa de jantar: MOB-04. Cadeiras: MOB-05. Luminárias de piso: MOB-06. Cortina: MOB-07. Aparador existente: EX-01.
- Nenhum item foi duplicado.

Conflitos registrados:
- Linho pedido × gatos que arranham (MOB-01, MOB-07).
- Tapete com borda de 40 cm cobrindo estar e jantar (MOB-02).
- Encaixe do sofá com chaise e da mesa para 6 no ambiente de 4,0 m × 6,0 m sem dados de circulação.

## Controle de orçamento
Total informado pelo cliente: R$ 85.000.

Escopo do orçamento: inclui frete e montagem. A inclusão de instalação da cortina, serviços no aparador e projeto é [NÃO INFORMADO].

Premissa de alocação (cada parcela é verba estimada, a confirmar com orçamentos):
- MOB-01: R$ 85.000 × 30% = R$ 25.500,00
- MOB-02: R$ 85.000 × 10% = R$ 8.500,00
- MOB-03: R$ 85.000 × 5% = R$ 4.250,00
- MOB-04: R$ 85.000 × 15% = R$ 12.750,00
- MOB-05: R$ 85.000 × 15% = R$ 12.750,00 total; R$ 12.750,00 ÷ 6 = R$ 2.125,00 por unidade
- MOB-06: R$ 85.000 × 5% = R$ 4.250,00 total; R$ 4.250,00 ÷ 2 = R$ 2.125,00 por unidade
- MOB-07: R$ 85.000 × 6% = R$ 5.100,00
- Frete e montagem gerais: R$ 85.000 × 8% = R$ 6.800,00
- EX-01: sem aquisição; serviços [NÃO INFORMADO], sem verba alocada.

Soma das verbas conhecidas: R$ 25.500 + R$ 8.500 + R$ 4.250 + R$ 12.750 + R$ 12.750 + R$ 4.250 + R$ 5.100 + R$ 6.800 = R$ 79.900,00.

Saldo ou excedente: R$ 85.000 − R$ 79.900 = R$ 5.100,00. É um saldo provisório, não uma reserva disponível, porque há custos desconhecidos.

Custos ainda não incluídos ou desconhecidos:
- Serviços no aparador (limpeza, reparo, fixação, transporte).
- Pontos elétricos para as luminárias.
- Possível tapete adicional, se estar e jantar forem separados.
- Diferença entre frete e montagem reais e a parcela alocada.

Todas as verbas estimadas dependem de confirmação por orçamentos.

## Controle de prazos
Data de montagem: 1º de março de 2027 (01/03/2027).

Data de referência: 21/10/2026 (data atual).

Premissas de prazo:
- As semanas são corridas.
- A contagem começa na confirmação do pedido.
- A fabricação não inclui frete.
- Margem de 2 semanas = 14 dias corridos, para frete e conferência.
- 2027 não é bissexto: fevereiro tem 28 dias.

| Código | Prazo do fornecedor e base de contagem | Margem | Pedir até, com conta | Situação do prazo |
|---|---|---|---|---|
| MOB-01 | 6 a 8 semanas (fabricação dos estofados). Início da contagem [NÃO INFORMADO]; premissa: semanas corridas a partir do pedido. | Premissa: 14 dias | 8 semanas: 8 × 7 = 56 dias; 56 + 14 = 70 dias; 01/03/2027 − 70 dias = 21/12/2026. 6 semanas: 6 × 7 = 42 dias; 42 + 14 = 56 dias; 01/03/2027 − 56 dias = 04/01/2027. | Não vencido: 21/12/2026 está 61 dias após 21/10/2026 (10 + 30 + 21). Prazo não confirmado (base de contagem e frete). Adotar o cenário de 8 semanas até confirmação. |
| MOB-05 | Se estofadas: 6 a 8 semanas, mesma base do MOB-01. Se não: [NÃO INFORMADO]. | Premissa: 14 dias | Se estofadas: 21/12/2026 (8 semanas) ou 04/01/2027 (6 semanas), contas iguais às do MOB-01. Se não: 01/03/2027 − prazo − margem. | Não confirmado |
| MOB-02 | [NÃO INFORMADO] | A definir | 01/03/2027 − prazo − margem | Não confirmado |
| MOB-03 | [NÃO INFORMADO] | A definir | 01/03/2027 − prazo − margem | Não confirmado |
| MOB-04 | [NÃO INFORMADO] | A definir | 01/03/2027 − prazo − margem | Não confirmado |
| MOB-06 | [NÃO INFORMADO] | A definir | 01/03/2027 − prazo − margem | Não confirmado |
| MOB-07 | Confecção e instalação: [NÃO INFORMADO] | A definir | 01/03/2027 − prazo − margem. Instalação possivelmente antes da montagem: verificar. | Não confirmado |
| EX-01 | Serviços e transporte, se houver: [NÃO INFORMADO] | A definir | 01/03/2027 − prazo do serviço − margem | Não confirmado |

## Especificações a verificar
- MOB-01: na ficha técnica do tecido, verificar comportamento ao fogo, abrasão (método de ensaio e ciclos ou fricções duplas), código ou instrução de limpeza e se as capas são removíveis e laváveis. Verificar também a resistência da trama a puxões, sem promessa de resistência a unhas, e a estrutura e o assento quanto a cargas. Resistência ao escorregamento: não aplicável ao estofado; aplicável apenas aos pés sobre o piso, se houver deslizamento.
- MOB-02: verificar comportamento ao fogo, abrasão e método ou ciclos, instruções de limpeza, resistência ao escorregamento ou necessidade de base antiderrapante, construção sem laçadas, tamanho disponível versus 3,2 m × 5,2 m, encaixe e circulação.
- MOB-03: verificar abrasão e resistência do acabamento a riscos, limpeza, cantos e estabilidade. Comportamento ao fogo: conferir se houver revestimento ou tecido. Escorregamento: não aplicável ao tampo.
- MOB-04: verificar abrasão do acabamento do tampo, limpeza, estabilidade e carga. Comportamento ao fogo: conferir se houver revestimento. Escorregamento: não aplicável.
- MOB-05: verificar carga e estabilidade e a limpeza do acabamento. Se estofadas: comportamento ao fogo, abrasão e método ou ciclos, código de limpeza e assento removível. Verificar ponteiras e deslizamento sobre o tapete ou o piso.
- MOB-06: verificar estabilidade da base, eventual fixação, proteção de cabos e dados elétricos. Comportamento ao fogo: conferir para a cúpula, se em tecido. Abrasão e escorregamento: não aplicáveis, salvo base com contato relevante com o piso.
- MOB-07: verificar comportamento ao fogo do tecido, instruções de lavagem e encolhimento, fixação e carga do trilho ou varão. Abrasão: verificar apenas se o fabricante informar, pois o uso não é de assento. Escorregamento: não aplicável.
- EX-01: verificar estado, limpeza e eventual tratamento do acabamento, estabilidade e fixação à parede considerando os gatos, e cargas sobre o tampo. Comportamento ao fogo, abrasão e escorregamento: não aplicáveis, por ser peça existente de madeira sem revestimento têxtil, salvo novo acabamento.

O profissional responsável confere as regras aplicáveis.

Anonimize os dados do cliente e use apenas ferramenta aprovada pelo escritório.

## Perguntas para o cliente

Medidas e layout
- Qual é a posição da janela e das portas, e quais são as áreas de circulação?
- Como se dá o acesso de entrega (elevador, escada, portas)? A resposta é especialmente importante para o sofá com chaise.
- Qual é o lado da chaise? Há medidas desejadas para o sofá, a mesa de centro e a mesa de jantar?
- O tapete de 3,2 m × 5,2 m deve cobrir estar e jantar juntos, ou cada área terá o seu tapete?

Peças e materiais
- As cadeiras serão estofadas?
- Quais são as medidas, o estado e a posição do aparador? Ele precisa de limpeza, reparo, fixação ou transporte?
- O linho continua desejado no sofá e na cortina, considerando os gatos que arranham? Aceitam alternativas de trama fechada, a verificar com o fabricante?
- Que tons substituem o branco puro (por exemplo, para o linho da cortina)?

Orçamento
- Confirmam a premissa de alocação proposta e o saldo provisório de R$ 5.100,00?
- O orçamento de R$ 85.000 inclui instalação da cortina, pontos elétricos e serviços no aparador?

Prazos
- O prazo de 6 a 8 semanas é contado em semanas corridas? Começa no pedido, no pagamento ou na aprovação de amostras? Inclui frete?
- A margem de 14 dias é aceitável?
- Quais são os prazos dos fornecedores do tapete, das mesas, das cadeiras, das luminárias e da cortina?
- Há férias coletivas dos fornecedores entre dezembro e janeiro?
- A cortina deve ser instalada antes da data de montagem?

