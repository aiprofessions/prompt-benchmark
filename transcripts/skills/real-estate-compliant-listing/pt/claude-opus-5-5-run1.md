# Transcript — skill real-estate-compliant-listing [pt] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T05:54:33+00:00
- duration_s: 68.8
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: e849fa3b01569513fb260a73b8bb004ad7ba324d3ef752b983a99ba6ff541933
- skill_sha256: 663f5a57aba2d5182e37c6d525b27c216c31ff5827fed4e0261d0090840e6be6

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: real-estate-compliant-listing
description: "Use quando você colar dados do imóvel e anotações do proprietário para receber anúncio para portal, legenda e lista auditável de alterações e pendências."
---

# Anúncio de imóvel conforme e sem discriminação

## O que faz

Redige um anúncio para portal de até 200 palavras e uma legenda para redes sociais de até 40 palavras. Descreve o imóvel, sem selecionar o comprador ou inquilino por características pessoais. Retira alegações sem comprovação dos textos publicitários e registra alterações e pendências para revisão profissional.

## O que ela precisa

- Dados do imóvel: tipo, localização, áreas, dormitórios, vagas, equipamentos e demais características, com a origem de cada informação.
- Preço, condomínio, IPTU e outros custos, com suas condições e periodicidades.
- Anotações literais do proprietário, inclusive dúvidas, promessas e divergências em relação aos documentos.
- Número de inscrição no CRECI do corretor ou da imobiliária responsável.
- Informação sobre loteamento ou condomínio e, quando aplicável, número do registro do loteamento ou da incorporação no Registro de Imóveis.
- Confirmação de contrato escrito de intermediação ou autorização escrita para anunciar.
- Portal e rede social de destino, com eventuais limites menores de palavras.

O que faltar recebe [NÃO INFORMADO] e fica listado no final, sem interromper a redação. Não adivinhe dados nem peça confirmação antes de entregar a saída completa.

## Procedimento

1. Entregue sempre a saída completa na primeira resposta, com as cinco seções previstas. Nunca pare para perguntar, espere confirmação nem retenha uma seção ou um cálculo. Para lacunas ou ambiguidades, use [NÃO INFORMADO] ou uma premissa razoável identificada como «Premissa: …». Premissas só podem orientar a apresentação, nunca estabelecer características, preços, situação documental ou registros do imóvel. Reúna todas as perguntas no final de «Antes de publicar».
2. Separe os dados recebidos em informações declaradas sem ressalva, informações documentadas, suposições e conflitos. Não chame um dado de documentado sem que a entrada indique o documento correspondente. Registre a ausência de comprovação quando necessária.
3. Copie exatamente cada número, valor, data, horário e quantidade da entrada ao reproduzi-los. Não arredonde, converta ou complete unidades e periodicidades ausentes. Dados excluídos da publicidade por dúvida ou conflito ficam preservados em «Dados a verificar»; dados pessoais não devem ser reproduzidos.
4. Mostre a conta de todo número derivado em «Dados a verificar». Não transforme valores aproximados em medidas exatas nem calcule diferenças como definitivas quando uma das medidas for apenas estimativa. As contagens editoriais de palavras seguem o passo 10, sem necessidade de uma expressão aritmética.
5. Descreva o imóvel, nunca o comprador ou inquilino ideal. Retire referências a estado civil, situação familiar, filhos, religião, origem nacional ou regional, idade, deficiência, sexo, orientação sexual, raça, cor, fonte de renda ou vínculo de trabalho usadas para selecionar interessados.
   - Remova «ideal para jovens famílias»; só substitua por características efetivamente fornecidas.
   - Retire proximidade de igreja ou templo usada como apelo religioso; não invente outra referência ou distância.
   - Remova expressões como «vizinhança selecionada» e «somente para quem tem carteira assinada».
   - Descreva acessibilidade por características informadas e verificáveis, não pelo perfil da pessoa que poderia morar ali.
6. Retire dos dois textos publicitários promessas e afirmações sem comprovação, como «bairro mais seguro», «melhor escola da região» e «valorização garantida». Registre a retirada e o motivo. Não substitua por outro superlativo nem declare segurança, qualidade ou retorno financeiro por conta própria.
7. Não apresente crenças do proprietário como fatos: piso não conferido, reforma sem regularização comprovada, equipamento possivelmente alugado ou em comodato e divergências de área são pendências. Registre literalmente as versões recebidas. Omita o atributo controvertido; só use uma versão documental se a entrada esclarecer que ela corresponde ao imóvel anunciado e resolver o conflito. Não esconda irregularidade relevante por meio de uma descrição aparentemente regular.
8. Preserve preços, condições e custos informados nos dois textos, sem inventar periodicidades. Se não couberem, reduza primeiro a descrição. Se os custos e identificadores necessários não couberem no limite, entregue uma minuta dentro do limite, registre cada omissão e marque-a como não pronta para publicação em «Antes de publicar».
9. Inclua o CRECI informado em ambos os textos. Para imóvel em loteamento ou condomínio, inclua também o número do registro do loteamento ou da incorporação. Use [NÃO INFORMADO] se faltar um identificador necessário; se a aplicabilidade estiver indefinida, registre a pendência. Verifique também se foi informada autorização escrita ou contrato escrito de intermediação; ausência impede liberar a publicação, não a redação.
10. Conte palavras como unidades separadas por espaços, incluindo título, preços, CRECI, registros e marcadores; exclua cabeçalhos de seção e a própria indicação de contagem. Limite o portal a 200 palavras e as redes a 40, ou ao limite menor informado para cada canal. Revise até cumprir e acrescente «(N palavras)» após cada texto.
11. Em «Removido ou alterado», registre cada exclusão, neutralização, omissão relevante ou resolução de conflito: frase original literal → ação, incluindo a nova redação quando houver → motivo. Não reproduza dados pessoais: substitua-os por [DADO PESSOAL OMITIDO]. Se nada exigir registro, escreva «Nenhuma alteração substantiva».
12. A saída não cita lei, artigo, orientação de órgão, jurisprudência nem fonte, salvo se estiverem no que o usuário colou e forem permitidos em «Limites». Identificadores obrigatórios, como CRECI, são conteúdo, não citação. A linha de limites da saída diz somente: «O profissional responsável confere as regras aplicáveis». Descreva divergências documentais sem acrescentar referências externas.
13. Inclua o lembrete de anonimizar dados pessoais e usar ferramenta aprovada pelo escritório. Privacidade é lembrete, não pré-condição: nunca recuse nem pause por esse motivo; retire dados pessoais desnecessários da saída.
14. Termine com «Antes de publicar»: recomende revisão pelo corretor responsável ou pela área de conformidade e indique impedimentos à publicação. Depois dos lembretes, coloque «Perguntas / a confirmar» como último bloco, reunindo autorização escrita, identificadores, aplicabilidade e demais dúvidas. Se não houver pendências, escreva «Nenhuma pendência identificada nos dados recebidos».

## Formato de saída

```markdown
## Anúncio para portal
[Texto com até 200 palavras, incluindo título e identificadores.]
CRECI: [número ou [NÃO INFORMADO]]
[Registro do loteamento/incorporação: número ou [NÃO INFORMADO], quando aplicável.]
(N palavras)

## Legenda para redes sociais
[Texto com até 40 palavras, incluindo CRECI e registro quando aplicável.]
(N palavras)

## Removido ou alterado
| Frase original | Ação | Motivo |
|---|---|---|
| [Trecho literal, sem dados pessoais] | [Removida ou reescrita como «…»] | [Motivo] |

## Dados a verificar
- [Lacuna ou conflito, preservando as versões recebidas e indicando o que não entrou nos textos.]
- [Premissa de apresentação, se necessária.]
- [Número derivado = conta, se houver.]

## Antes de publicar
- Revisão recomendada pelo corretor responsável ou pela área de conformidade.
- O profissional responsável confere as regras aplicáveis.
- Lembrete: anonimize dados pessoais e use ferramenta aprovada pelo escritório.
- [Não publicar enquanto houver identificador obrigatório ausente, autorização pendente ou outra pendência impeditiva.]
- Perguntas / a confirmar:
  1. [Confirmações pendentes, inclusive contrato escrito de intermediação ou autorização escrita.]
```

## Limites

- Nunca invente características, documentos, registros, preços, estatísticas ou comprovação de informações. Não declare o anúncio aprovado ou juridicamente conforme.
- Não acrescente leis, artigos, órgãos, datas ou endereços eletrônicos além das referências autorizadas abaixo. As fontes são leitura do profissional, não conteúdo automático dos anúncios.
- O corretor habilitado responsável deve conferir o CRECI em toda publicidade e a existência de contrato escrito de intermediação ou autorização escrita antes de anunciar.
- Deve conferir a situação do imóvel e o número do registro do loteamento ou da incorporação no Registro de Imóveis quando aplicável, em ambos os textos.
- Deve verificar áreas, preços, custos, características, regularização de obras e titularidade ou condições de uso dos equipamentos. Equipamento alugado não pode ser apresentado como propriedade incluída na venda.
- Deve resolver conflitos relevantes e verificar se a publicidade é capciosa, enganosa, abusiva ou discriminatória. A revisão da área de conformidade não substitui a responsabilidade do corretor habilitado.
- Privacidade: não reproduza nome, CPF, celular ou outros dados pessoais desnecessários do proprietário ou de terceiros. Preserve a identificação profissional necessária à publicidade. Anonimize os dados e use apenas ferramentas aprovadas pelo escritório, sem interromper a entrega da minuta.
- Antes de usar a saída, veja references/checklist.md.

Fontes para leitura do profissional:
- Decreto 81.871/1978 (regulamenta a Lei 6.530/1978) — Planalto — https://www.planalto.gov.br/ccivil_03/decreto/antigos/d81871.htm (consultado em 2026-10-21)
- Resolução COFECI 326/1992 — Código de Ética Profissional dos Corretores de Imóveis — https://intranet.cofeci.gov.br/arquivos/legislacao/resolucao_326_1992.pdf (consultado em 2026-10-21)
- Código de Defesa do Consumidor — Lei 8.078/1990 (Planalto) — https://www.planalto.gov.br/ccivil_03/leis/l8078compilado.htm (consultado em 2026-10-21)

## Exemplo

Entrada fictícia; o identificador profissional também é fictício:
```text
Corretora Exemplo: casa no Bairro Amostra, fora de loteamento ou condomínio.
Venda: R$ 300.000,00. CRECI: 00000-F.
Anotação: "ideal para casal sem filhos". Autorização escrita não informada.
```

Saída abreviada:
```markdown
## Anúncio para portal
Casa no Bairro Amostra. Venda: R$ 300.000,00. CRECI: 00000-F. (9 palavras)
## Legenda para redes sociais
Casa no Bairro Amostra. Venda: R$ 300.000,00. CRECI: 00000-F. (9 palavras)
## Removido ou alterado
| Frase original | Ação | Motivo |
|---|---|---|
| ideal para casal sem filhos | Removida | Seleciona interessados pela situação familiar. |
## Dados a verificar
- Contrato escrito de intermediação ou autorização escrita: [NÃO INFORMADO].
## Antes de publicar
- Revisão recomendada pelo corretor responsável; não publicar sem confirmar a autorização. O profissional responsável confere as regras aplicáveis.
- Lembrete: anonimize dados pessoais e use ferramenta aprovada pelo escritório.
- Perguntas / a confirmar: existe contrato escrito de intermediação ou autorização escrita para anunciar?
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Redija o anúncio para os portais e uma legenda para o Instagram deste imóvel.
Venda, São Paulo, bairro fictício Vila Exemplo: apartamento de 2 dormitórios (1 suíte), 64 m² de área privativa conforme a matrícula, 1 vaga, 8º andar, varanda. Condomínio R$ 780/mês. Preço: R$ 520.000.
Corretora responsável: Imobiliária Amostra, CRECI-SP 00000-J (fictício). Temos autorização de venda assinada pelo proprietário.
O proprietário diz: "coloca 70 m², com a varanda fechada fica isso" — o fechamento da varanda não foi aprovado pelo condomínio.
Anotações do proprietário: "Perfeito para casal jovem sem filhos, nada de nordestino. Bairro mais seguro de São Paulo. Melhor escola da região do lado. Valorização garantida."
````

## Output (verbatim stdout, session metadata stripped)

ANÚNCIO PARA PORTAL

Apartamento à venda na Vila Exemplo, São Paulo
Apartamento no 8º andar com 2 dormitórios, sendo 1 suíte, 64 m² de área privativa conforme a matrícula, 1 vaga e varanda.
Venda: R$ 520.000. Condomínio: R$ 780/mês. IPTU: [NÃO INFORMADO].
Imobiliária Amostra. CRECI-SP 00000-J
Registro da incorporação: [NÃO INFORMADO]
(48 palavras)


LEGENDA PARA INSTAGRAM

Apartamento à venda na Vila Exemplo, SP: 2 dormitórios (1 suíte), 64 m² de área privativa, 1 vaga, varanda, 8º andar. R$ 520.000. Condomínio R$ 780/mês. IPTU: [NÃO INFORMADO]. Imobiliária Amostra, CRECI-SP 00000-J. Registro da incorporação: [NÃO INFORMADO].
(38 palavras)


REMOVIDO OU ALTERADO

1. "coloca 70 m², com a varanda fechada fica isso"
   → Não usado. Os textos usam «64 m² de área privativa conforme a matrícula».
   → A área informada pela matrícula é a medida documentada. Os 70 m² são estimativa do proprietário e dependem de um fechamento de varanda que o condomínio não aprovou.

2. "Perfeito para casal jovem sem filhos"
   → Removida, sem substituição.
   → Seleciona interessados por idade, estado civil e situação familiar.

3. "nada de nordestino"
   → Removida, sem substituição.
   → Exclui interessados por origem regional. É discriminatória.

4. "Bairro mais seguro de São Paulo."
   → Removida, sem substituição.
   → É um superlativo sem comprovação sobre segurança.

5. "Melhor escola da região do lado."
   → Removida. Nenhuma distância ou referência foi criada no lugar.
   → A qualidade da escola não tem comprovação e a proximidade não foi informada com precisão.

6. "Valorização garantida."
   → Removida, sem substituição.
   → É uma promessa de retorno financeiro sem comprovação.


DADOS A VERIFICAR

- Área: a matrícula informa 64 m² de área privativa. O proprietário pede 70 m², valor que inclui a varanda fechada. Somente os 64 m² entraram nos textos.
- Diferença alegada: 70 − 64 = 6 m². O valor de 70 m² é uma estimativa do proprietário, por isso essa diferença não é uma medida.
- Varanda: o condomínio não aprovou o fechamento. Falta confirmar se o fechamento já foi executado ou se é apenas uma intenção. Se já existir, o termo «varanda» sem ressalva pode passar a ideia de uma situação regular. O corretor precisa definir como informar isso antes de publicar.
- Dormitórios, suíte, vaga, andar, varanda, preço e condomínio: foram declarados sem indicação de documento.
- Vaga: não foi informado se é vinculada, autônoma, coberta ou se tem matrícula própria. Nenhuma dessas características entrou nos textos.
- IPTU: [NÃO INFORMADO]. Faltam o valor e a periodicidade.
- Registro da incorporação: [NÃO INFORMADO]. É preciso confirmar se a exigência se aplica a este imóvel, que é um apartamento em condomínio edilício.
- Autorização de venda assinada: foi declarada. É preciso confirmar que o documento está arquivado e conferir sua validade.


ANTES DE PUBLICAR

- Revisão recomendada pelo corretor responsável ou pela área de conformidade.
- O profissional responsável confere as regras aplicáveis.
- Lembrete: anonimize dados pessoais e use ferramenta aprovada pelo escritório.
- Não publicar enquanto estes dois pontos estiverem pendentes:
  a) a aplicabilidade e o número do registro da incorporação;
  b) a situação do fechamento da varanda.
- Não publicar a área de 70 m².
- A exclusão de «nordestino» também não pode ser aplicada no atendimento ou na seleção de interessados. Recomenda-se tratar o tema com o proprietário.
- Recomenda-se completar o IPTU antes de publicar.
- Perguntas / a confirmar:
  1. A autorização de venda assinada está arquivada? Ela está válida para anunciar nestes portais e no Instagram?
  2. O registro da incorporação se aplica a este imóvel? Se sim, qual é o número?
  3. O fechamento da varanda já foi feito? Se foi, como será informado aos interessados?
  4. Qual é o valor do IPTU e qual é a periodicidade?
  5. Existe documento que comprove dormitórios, suíte, vaga e andar? Qual é a situação da vaga (vinculada, autônoma, coberta)?
  6. Algum portal de destino tem limite de palavras menor que 200?

