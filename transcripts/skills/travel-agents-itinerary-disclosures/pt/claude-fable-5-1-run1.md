# Transcript — skill travel-agents-itinerary-disclosures [pt] — claude-fable-5-1 — run 1

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-21T05:47:03+00:00
- duration_s: 85.2
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: a913eedbbb4ac40828e54ffd415b38d62511be1abe3e245840e8ca7582468a39
- skill_sha256: 73cf1e9fd3483a1fb7410bf40a99551edf68bfd04df5fa81dbcb27838ab3bd26

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: travel-agents-itinerary-disclosures
description: "Use quando você colar perfil dos viajantes, datas, destinos, restrições e condições da agência para receber um roteiro diário com condições de reserva e pendências."
---

# Roteiro de viagem + condições de reserva

## O que faz

Redige um roteiro para o cliente com base nos dados da viagem e nas condições da agência. Distribui os dias e as noites informados, identifica deslocamentos e mostra como as restrições foram consideradas. Reproduz as condições de reserva sem alterações e separa o que precisa ser reservado ou confirmado.

## O que ela precisa

- Perfil sem identificação pessoal: quantidade de viajantes, idades das crianças, necessidades de mobilidade, dieta e alergias.
- Datas de início e fim, destinos, sequência das cidades e divisão das noites.
- Origem, destino e meio de transporte dos deslocamentos, inclusive chegada e retorno.
- Preferências e restrições: carro alugado permitido ou não, ritmo, descanso e atividades desejadas.
- Texto original das condições da agência, incluindo sinal, pagamento final e aceite ou recusa do seguro viagem.
- Reservas existentes e informações fornecidas sobre preços, funcionamento, trajetos e acesso.
- O que faltar será marcado como [NÃO INFORMADO] e listado no final, sem perguntas prévias. Premissas só podem organizar sugestões; nunca substituem dados ausentes da viagem ou condições comerciais.

## Procedimento

1. Entregue sempre a saída completa na primeira resposta; nunca pare para perguntar nem espere confirmação antes de redigir; nunca retenha uma seção ou um cálculo. Diante de informação ausente ou ambígua, use [NÃO INFORMADO] ou uma hipótese de organização claramente marcada como “Premissa: …”. Reúna todas as perguntas na última seção, “A reservar / a confirmar”.
2. Copie exatamente cada número, data, horário e quantidade da entrada, preservando sua grafia e os valores em reais. Para números derivados, mostre a conta e identifique o resultado como cálculo. Não abrevie datas fornecidas nem altere valores para fazer as contas fecharem.
3. Confira o período e as noites: mostre data final − data inicial = total de noites e a soma das noites por destino. Identifique cada pernoite no dia correspondente; o último dia não ganha pernoite sem previsão expressa. Se houver noite em trânsito, use somente a informação fornecida.
4. Se datas, sequência ou noites divergirem, mantenha os dados originais, mostre a diferença calculável e registre a incompatibilidade. Não redistribua noites nem altere datas por conta própria. Se faltarem datas, entregue a seção diária com [NÃO INFORMADO], sem inventar um calendário; se faltarem operandos, mostre o cálculo como pendente.
5. Havendo datas, faça um bloco para cada data, inclusive chegada e retorno, sem omitir ou acrescentar dias. Marque “Dia de deslocamento” em cada transferência, chegada ou retorno informado, com origem, destino e meio. Use [NÃO INFORMADO] nos trechos incompletos; transporte sugerido deve ser identificado como sugestão a confirmar.
6. Aplique as restrições em cada dia e acrescente “Pedidos aplicados: …”. Para mobilidade, proponha alternativas compatíveis sem garantir acessibilidade; para dieta, indique refeições a buscar; para crianças, considere cada idade informada. Sem carro alugado, não proponha locação nem atividades que dependam dela. Para ritmo, declare um limite de atividades como premissa quando não houver limite fornecido.
7. Havendo alergia informada, sinalize cada refeição, passeio com alimentação e hospedagem: “ALERGIA: [alérgeno] — confirmar com o fornecedor”. Inclua a confirmação na lista final. Nunca afirme que um estabelecimento é seguro nem que uma adaptação alimentar está garantida.
8. Não apresente preços, horários de funcionamento, tempos de transporte, limites de idade ou altura e regras de entrada como fatos verificados. Marque cada ocorrência com [confirm], inclusive quando vier da entrada; nesse caso, indique que é informação fornecida. Não invente estimativas para preencher lacunas. Idades dos viajantes não são limites de acesso.
9. Em “Sobre os seus pedidos”, relacione cada restrição à solução proposta e aos dias correspondentes. Informe pedidos não atendidos e dependências de confirmação, inclusive acessibilidade, alimentação e adequação às crianças.
10. Em “Condições de reserva”, copie integralmente o texto recebido, sem corrigir, resumir, reorganizar ou inserir marcadores dentro dele. Fora da transcrição, liste sinal, pagamento final ou manifestação sobre seguro ausentes como [NÃO INFORMADO]. Se o texto contiver itens sujeitos a [confirm], repita cada item em uma nota separada com o marcador e esclareça que a transcrição não comprova sua validade.
11. Em “A reservar / a confirmar”, liste reservas pendentes, cada item [confirm], alergias, lacunas, divergências e perguntas sobre premissas. Encaminhe o cliente às fontes oficiais do governo para passaporte, visto e requisitos de entrada, e à própria seguradora para cobertura. Não forneça endereços ou requisitos não recebidos.
12. A saída não cita lei, artigo, orientação de órgão, jurisprudência nem fonte, salvo quando constarem do material colado; não acrescente referências além das autorizadas em “Limites”. Uma identificação obrigatória fornecida é conteúdo, não citação. O encaminhamento genérico do passo anterior não é uma citação. A linha de limites da saída diz apenas: “O profissional responsável confere as regras aplicáveis.”
13. Inclua em “A viagem em resumo”: “Lembrete ao agente: anonimize os dados dos passageiros e use apenas ferramenta aprovada pela agência.” Não reproduza identificadores desnecessários. Privacidade é lembrete, não pré-condição: nunca recuse nem pause a redação por esse motivo.
14. Antes de entregar, confira as cinco seções na ordem, todas as datas e pernoites, cálculos, restrições e marcadores. Compare as condições palavra por palavra com a entrada. Confira que nenhuma pendência foi omitida e que todas as perguntas estão na última seção, sem texto posterior a ela.

## Formato de saída

Preencha o modelo sem manter instruções entre colchetes, exceto os marcadores obrigatórios. Repita o bloco diário para cada data; não crie seções adicionais.

```markdown
## A viagem em resumo
Viajantes: [perfil sem identificação pessoal; quantidades e idades fornecidas].
Período: [datas exatas]. Noites: [data final] − [data inicial] = [total].
Distribuição: [noites por destino ou trânsito] = [soma]; divergência: [se houver].
Premissa: [somente se necessária; lacunas factuais recebem [NÃO INFORMADO]].
Lembrete ao agente: anonimize os dados dos passageiros e use apenas ferramenta aprovada pela agência.
O profissional responsável confere as regras aplicáveis.

## Dia a dia
[data] — [destino; Dia de deslocamento: origem → destino, meio, quando aplicável].
Proposta: [atividades compatíveis; itens sujeitos a confirmação com [confirm]].
Pernoite: [local informado ou [NÃO INFORMADO]; no encerramento, indicar sem pernoite previsto].
Pedidos aplicados: [restrições atendidas e dependências].
ALERGIA: [alérgeno informado] — confirmar com o fornecedor [quando aplicável].

## Sobre os seus pedidos
- [Pedido]: [solução e dias; limitação ou confirmação pendente].

## Condições de reserva
[Transcrição integral e literal das condições recebidas, ou [NÃO INFORMADO].]
Fora da transcrição — lacunas: [sinal, pagamento final ou seguro ausentes].
Fora da transcrição — itens não verificados: [cada ocorrência pertinente] [confirm].

## A reservar / a confirmar
- [ ] Reservar: [serviços ainda não contratados].
- [ ] Confirmar: [cada item [confirm], alergia e dependência de fornecedor].
- [ ] Passaporte, visto e requisitos de entrada: consulte as fontes oficiais do governo.
- [ ] Cobertura do seguro: confirme com a sua seguradora.
- [ ] Perguntas ao agente: [todas as lacunas, divergências e premissas].
```

## Limites

- Não invente preços, disponibilidade, horários, trajetos, condições comerciais, requisitos de acesso ou estatísticas. Uma sugestão de atividade não equivale a reserva nem a confirmação de atendimento.
- Não garanta segurança alimentar, acessibilidade ou adequação de uma atividade à criança sem confirmação do fornecedor. Não interprete cobertura de seguro como garantida.
- O profissional responsável pela agência deve verificar datas, noites, viabilidade dos deslocamentos, fornecedores, atendimento das restrições, condições comerciais vigentes e registro do aceite ou recusa do seguro antes do envio.
- No Brasil, o Cadastur é obrigatório para agências de turismo; o responsável deve conferir a regularidade da agência. O CDC protege contra publicidade enganosa: o responsável deve validar informações comerciais e operacionais antes de apresentá-las como confirmadas.
- Documentos, vistos e requisitos de entrada devem ser verificados nas fontes oficiais pelo responsável e pelo viajante; cobertura deve ser confirmada com a seguradora.
- Dados dos passageiros: observe a LGPD. Anonimize os dados e use apenas ferramentas aprovadas pela agência; não solicite nem reproduza documentos, contatos ou dados de saúde além do necessário para organizar o atendimento. O lembrete não interrompe a entrega.
- Nenhuma fonte oficial sobre IA foi verificada para agências de turismo. O responsável deve conferir as regras aplicáveis à sua atuação, sem presumir aprovação do uso de IA.
- Fontes exclusivas para leitura do profissional, não para inclusão automática no roteiro:
  - gov.br — Cadastur (cadastro de prestadores de serviços turísticos) — https://www.gov.br/pt-br/servicos/cadastrar-prestadora-de-servico-turistico (consultado em 2026-10-21)
  - Código de Defesa do Consumidor — Lei 8.078/1990 (Planalto) — https://www.planalto.gov.br/ccivil_03/leis/l8078compilado.htm (consultado em 2026-10-21)
  - LGPD — Lei 13.709/2018 (Planalto) — https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm (consultado em 2026-10-21)
- Antes do envio, veja references/checklist.md.

## Exemplo

Entrada fictícia:
```text
Viajante: Exemplo, 1 adulto; sem carro alugado; ritmo tranquilo.
Datas: 12/05/2027 a 13/05/2027; Santos, 1 noite.
Deslocamentos: São Paulo → Santos na chegada; Santos → São Paulo no retorno; ônibus.
Condições: Sinal e saldo a combinar. Seguro viagem: aceite pendente.
```

Saída abreviada:
```markdown
## A viagem em resumo
Exemplo, 1 adulto; 12/05/2027 a 13/05/2027. Noites: 13/05/2027 − 12/05/2027 = 1; Santos = 1 noite.
Lembrete ao agente: anonimize os dados dos passageiros e use apenas ferramenta aprovada pela agência.
O profissional responsável confere as regras aplicáveis.
## Dia a dia
12/05/2027 — Dia de deslocamento: São Paulo → Santos, ônibus. Descanso; pernoite em Santos. Pedidos aplicados: sem carro alugado; ritmo tranquilo.
13/05/2027 — Dia de deslocamento: Santos → São Paulo, ônibus. Retorno, sem pernoite previsto. Pedidos aplicados: sem carro alugado; ritmo tranquilo.
## Sobre os seus pedidos
Sem carro alugado: ônibus nos dois dias; ritmo tranquilo: sem passeios programados.
## Condições de reserva
Sinal e saldo a combinar. Seguro viagem: aceite pendente.
## A reservar / a confirmar
- [ ] Confirmar reservas de ônibus e hospedagem; combinar sinal e saldo; registrar decisão sobre seguro.
- [ ] Passaporte, visto e requisitos de entrada: consulte as fontes oficiais do governo. Cobertura do seguro: confirme com a sua seguradora.
- [ ] Mobilidade, dieta e alergias: [NÃO INFORMADO]. Há necessidades a considerar?
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Monte o roteiro dos clientes com as nossas condições de reserva.
Viajantes: família de Belo Horizonte (fictícia, "os Exemplo"), crianças de 5 e 8 anos.
Viagem: Buenos Aires 4 noites e Bariloche 3 noites, de 10 a 17 de julho de 2027 (chegam a Buenos Aires em 10/07, voo para Bariloche em 14/07, retorno ao Brasil saindo de Bariloche em 17/07).
O filho mais novo tem alergia grave a amendoim. Sem carro alugado. Ritmo: um passeio principal por dia, tardes livres.
Interesses: neve, doce de leite, um museu para crianças.
Condições da agência: "Sinal de 30% na reserva, não reembolsável. Saldo até 45 dias antes do embarque. O seguro viagem é oferecido; o cliente aceita ou recusa por escrito."
````

## Output (verbatim stdout, session metadata stripped)

## A viagem em resumo
Viajantes: família (perfil fictício "os Exemplo"), com crianças de 5 e 8 anos; quantidade de adultos [NÃO INFORMADO]. Mobilidade: [NÃO INFORMADO]. Dieta: alergia grave a amendoim (filho mais novo, 5 anos). Sem carro alugado. Ritmo: um passeio principal por dia, tardes livres. Interesses: neve, doce de leite, um museu para crianças.
Período: 10 de julho de 2027 a 17 de julho de 2027. Noites: 17/07/2027 − 10/07/2027 = 7 (cálculo).
Distribuição: Buenos Aires 4 noites + Bariloche 3 noites = 7 (cálculo); divergência: nenhuma.
Deslocamentos informados: chegada a Buenos Aires em 10/07; voo Buenos Aires → Bariloche em 14/07; retorno ao Brasil saindo de Bariloche em 17/07.
Premissa: origem do deslocamento de chegada = Belo Horizonte (a família é de Belo Horizonte; a origem do trecho não foi declarada). Meio dos trechos de chegada e de retorno: [NÃO INFORMADO].
Premissa: passeios de neve e Circuito Chico em Bariloche organizados por excursão com transporte incluído, por não haver carro alugado; a confirmar com a agência/fornecedor.
Lembrete ao agente: anonimize os dados dos passageiros e use apenas ferramenta aprovada pela agência.
O profissional responsável confere as regras aplicáveis.

## Dia a dia
10/07/2027 — Buenos Aires; Dia de deslocamento: Belo Horizonte (Premissa) → Buenos Aires, meio [NÃO INFORMADO], horários [NÃO INFORMADO].
Proposta: chegada, traslado aeroporto → hospedagem (sugestão a confirmar: transfer contratado ou táxi/remis, sem locação de carro) [confirm], descanso e jantar leve perto da hospedagem. Sem passeio principal pela chegada.
Pernoite: Buenos Aires (hospedagem [NÃO INFORMADO]).
Pedidos aplicados: sem carro alugado (traslado contratado ou táxi); ritmo (sem passeio no dia de chegada); crianças de 5 e 8 anos (dia curto após o deslocamento).
ALERGIA: amendoim — confirmar com o fornecedor (hospedagem, refeições do trecho de chegada e jantar).

11/07/2027 — Buenos Aires.
Proposta: passeio principal: museu para crianças (sugestão a confirmar: Museo de los Niños, no bairro do Abasto) — horário de funcionamento, ingressos e faixa etária indicada [confirm]. Deslocamento por táxi ou transporte público [confirm]. Tarde livre.
Pernoite: Buenos Aires (hospedagem [NÃO INFORMADO]).
Pedidos aplicados: museu para crianças (interesse atendido como sugestão); ritmo (um passeio, tarde livre); crianças de 5 e 8 anos (adequação do museu a cada idade depende de confirmação do fornecedor); sem carro alugado.
ALERGIA: amendoim — confirmar com o fornecedor (lanchonete do museu e refeições do dia).

12/07/2027 — Buenos Aires.
Proposta: passeio principal: roteiro de doce de leite — visita a uma confeitaria ou café tradicional para degustação (sugestão; estabelecimento, horário e preços [confirm]). Tarde livre.
Pernoite: Buenos Aires (hospedagem [NÃO INFORMADO]).
Pedidos aplicados: doce de leite (interesse atendido como sugestão); ritmo (um passeio, tarde livre); sem carro alugado.
ALERGIA: amendoim — confirmar com o fornecedor (confeitaria/café: ingredientes e contaminação cruzada; não há garantia de segurança sem essa confirmação).

13/07/2027 — Buenos Aires.
Proposta: passeio principal ao ar livre e de baixa exigência física (sugestão a confirmar: Jardim Japonês ou Ecoparque, em Palermo) — funcionamento e ingressos [confirm]. Tarde livre; organização das malas para o voo do dia seguinte.
Pernoite: Buenos Aires (hospedagem [NÃO INFORMADO]).
Pedidos aplicados: ritmo (um passeio, tarde livre); crianças de 5 e 8 anos (passeio de curta duração); sem carro alugado.
ALERGIA: amendoim — confirmar com o fornecedor (refeições e lanches do dia).

14/07/2027 — Bariloche; Dia de deslocamento: Buenos Aires → Bariloche, voo (informado; companhia, horário e aeroporto de partida [NÃO INFORMADO]).
Proposta: traslado hospedagem → aeroporto e, em Bariloche, aeroporto → hospedagem (sugestão a confirmar: transfer contratado ou táxi) [confirm]. Chegada, acomodação e descanso. Sem passeio principal pelo deslocamento.
Pernoite: Bariloche (hospedagem [NÃO INFORMADO]).
Pedidos aplicados: sem carro alugado (traslados contratados); ritmo (dia de deslocamento sem passeio); crianças de 5 e 8 anos (dia leve).
ALERGIA: amendoim — confirmar com o fornecedor (companhia aérea, hospedagem e refeições do dia).

15/07/2027 — Bariloche.
Proposta: passeio principal: dia de neve (sugestão a confirmar: Cerro Catedral ou Cerro Otto, com excursão que inclua transporte ida e volta, já que não há carro alugado). Condições de neve na data, abertura dos meios de elevação, preços, atividades para crianças (trenó, parque de neve) e seus limites de idade ou altura [confirm]. Tarde livre.
Pernoite: Bariloche (hospedagem [NÃO INFORMADO]).
Pedidos aplicados: neve (interesse atendido como sugestão; presença de neve não garantida); sem carro alugado (excursão com transporte); ritmo (um passeio, tarde livre); crianças de 5 e 8 anos (atividades dependem de confirmação do fornecedor para cada idade).
ALERGIA: amendoim — confirmar com o fornecedor (refeições na montanha e lanches da excursão).

16/07/2027 — Bariloche.
Proposta: passeio principal: Circuito Chico por excursão com transporte incluído (sugestão; roteiro, duração e preços [confirm]); parada opcional em chocolataria ou confeitaria para doce de leite [confirm]. Tarde livre; organização das malas para o retorno.
Pernoite: Bariloche (hospedagem [NÃO INFORMADO]).
Pedidos aplicados: sem carro alugado (excursão com transporte); ritmo (um passeio, tarde livre); doce de leite (reforço do interesse, como sugestão); crianças de 5 e 8 anos (excursão em veículo, sem caminhadas longas).
ALERGIA: amendoim — confirmar com o fornecedor (chocolataria/confeitaria e refeições do dia).

17/07/2027 — Dia de deslocamento: Bariloche → Brasil (cidade de destino [NÃO INFORMADO]), meio [NÃO INFORMADO] (sugestão a confirmar: voo, com eventual conexão [NÃO INFORMADO]), horários [NÃO INFORMADO].
Proposta: traslado hospedagem → aeroporto (sugestão a confirmar: transfer contratado ou táxi) [confirm]. Retorno; sem pernoite previsto.
Pernoite: sem pernoite previsto (encerramento).
Pedidos aplicados: sem carro alugado (traslado contratado); ritmo (sem passeio no dia de retorno).
ALERGIA: amendoim — confirmar com o fornecedor (refeições do trecho de retorno).

## Sobre os seus pedidos
- Sem carro alugado: nenhuma locação proposta; traslados nos dias 10/07, 14/07 e 17/07 e passeios de 15/07 e 16/07 organizados com transporte contratado ou excursão com transporte incluído; em Buenos Aires (11 a 13/07), táxi ou transporte público. Todos os transportes são sugestões a confirmar [confirm].
- Ritmo (um passeio principal por dia, tardes livres): aplicado em 11, 12, 13, 15 e 16/07; nos dias de deslocamento (10, 14 e 17/07) não há passeio programado.
- Neve: dia 15/07, Cerro Catedral ou Cerro Otto (sugestão). Presença de neve, abertura e atividades infantis não são garantidas; dependem de confirmação do fornecedor [confirm].
- Doce de leite: dia 12/07 (Buenos Aires) e parada opcional em 16/07 (Bariloche). Estabelecimentos e preços pendentes [confirm].
- Museu para crianças: dia 11/07 (sugestão: Museo de los Niños). Funcionamento, ingressos e adequação às idades de 5 e 8 anos pendentes [confirm].
- Alergia grave a amendoim (criança de 5 anos): sinalizada em todos os dias; nenhuma refeição, hospedagem ou excursão pode ser apresentada como segura sem confirmação do fornecedor. Não atendido ainda: nenhuma confirmação foi obtida.
- Crianças de 5 e 8 anos: passeios curtos e com transporte; limites de idade ou altura das atividades de neve pendentes [confirm].
- Mobilidade: [NÃO INFORMADO]; nenhuma adaptação foi considerada.
- Não atendido: quantidade de adultos, hospedagens, meios e horários dos trechos de chegada e retorno não foram informados, portanto nenhuma reserva está refletida no roteiro.

## Condições de reserva
Sinal de 30% na reserva, não reembolsável. Saldo até 45 dias antes do embarque. O seguro viagem é oferecido; o cliente aceita ou recusa por escrito.
Fora da transcrição — lacunas: sinal informado; pagamento final informado; seguro viagem: manifestação do cliente (aceite ou recusa por escrito) [NÃO INFORMADO] — pendente de registro.
Fora da transcrição — itens não verificados: "Sinal de 30%" — informação fornecida pela agência [confirm]; "não reembolsável" — informação fornecida pela agência [confirm]; "Saldo até 45 dias antes do embarque" — informação fornecida pela agência [confirm]. A transcrição não comprova a validade vigente dessas condições.
Fora da transcrição — cálculo: com Premissa de embarque em 10/07/2027, data-limite do saldo = 10/07/2027 − 45 dias = 26/05/2027 (cálculo; depende da data de embarque confirmada) [confirm].

## A reservar / a confirmar
- [ ] Reservar: trecho de chegada a Buenos Aires em 10/07/2027; voo Buenos Aires → Bariloche em 14/07/2027; trecho de retorno Bariloche → Brasil em 17/07/2027; hospedagem em Buenos Aires (4 noites, 10 a 14/07) e em Bariloche (3 noites, 14 a 17/07); traslados de 10, 14 e 17/07; excursões de neve (15/07) e Circuito Chico (16/07); ingressos do museu (11/07). Nenhuma reserva existente foi informada.
- [ ] Confirmar: traslados e meios de transporte sugeridos [confirm]; museu para crianças: funcionamento, ingressos e faixa etária [confirm]; confeitarias/cafés de doce de leite: estabelecimento e preços [confirm]; passeio ao ar livre de 13/07: funcionamento e ingressos [confirm]; neve em 15/07: condições, abertura, preços, atividades infantis e limites de idade/altura [confirm]; Circuito Chico: roteiro, duração e preços [confirm]; condições comerciais (30%, não reembolsável, 45 dias) e data-limite calculada de 26/05/2027 [confirm].
- [ ] Confirmar com cada fornecedor (hospedagens, companhias aéreas, excursões, restaurantes, confeitarias, museu): ALERGIA: amendoim — ingredientes, contaminação cruzada e procedimento em emergência.
- [ ] Registrar por escrito o aceite ou a recusa do seguro viagem pelo cliente.
- [ ] Passaporte, visto e requisitos de entrada: consulte as fontes oficiais do governo.
- [ ] Cobertura do seguro: confirme com a sua seguradora.
- [ ] Perguntas ao agente: quantos adultos viajam? Há necessidade de mobilidade ou outra restrição alimentar além do amendoim? A origem do trecho de chegada é Belo Horizonte (Premissa) e qual o meio e horário? Qual o meio, horário, eventual conexão e cidade de destino do retorno em 17/07? Qual a companhia e o horário do voo de 14/07? Quais hospedagens em Buenos Aires e Bariloche? A data de embarque para o cálculo dos 45 dias é 10/07/2027 (Premissa)? As excursões com transporte incluído são aceitas como solução para a ausência de carro (Premissa)? A criança de 5 anos leva medicação de emergência para a alergia, a ser informada aos fornecedores?

