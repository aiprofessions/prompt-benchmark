# Transcript — skill healthcare-visit-summary [pt] — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:39:41+00:00
- duration_s: 24.0
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: be809fa3846bf99dbf3cad0c4d5bc6433b12569d48eee7045eae4ea7f774d87c
- skill_sha256: 80943af770284153d68a16e287e1c54b0dc76023cc773af4dabcd9aa637ed196

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: healthcare-visit-summary
description: "Use quando você colar uma nota de consulta e pedir um resumo para o paciente com checagem de alertas para revisão do profissional."
---

# Resumo da consulta para o paciente + checagem de alertas

## O que faz

Transforma a nota de consulta em um rascunho para o paciente, com linguagem simples e sem acrescentar condutas. Separa as dúvidas e possíveis alertas para revisão exclusiva do profissional. O profissional responsável valida o conteúdo antes de entregar e faz a comunicação clínica ao paciente.

## O que ela precisa

- Nota da consulta: queixas, preocupações, achados, resultados, hipóteses ou diagnósticos registrados e plano.
- Medicamentos e mudanças prescritas, com dose, unidade, via, frequência e duração, quando registradas.
- Alergias e orientações de retorno e de atendimento urgente dadas pelo profissional.
- Detalhes de exames, acompanhamento e responsáveis pelo contato, quando disponíveis.
- Opcionalmente, indicação de quem receberá o resumo: paciente, familiar ou cuidador.
- Use nota anonimizada e ferramenta aprovada pela instituição; a exceção à anonimização exige cobertura pelos acordos da organização.
- O que faltar será marcado como [NÃO INFORMADO] e listado no final, sem perguntas antes da redação e sem adivinhar dados clínicos.

## Procedimento

1. Entregue sempre a saída completa na primeira resposta; nunca pare para perguntar nem espere confirmação antes de redigir; nunca retenha uma seção ou um cálculo solicitado. Se faltar informação ou houver ambiguidade, escreva [NÃO INFORMADO] ou declare uma premissa razoável como «Premissa: …». Use premissas apenas para apresentação, nunca para preencher dados clínicos. Reúna todas as perguntas na ÚLTIMA seção da saída.
2. Comece com «Aviso de RASCUNHO» e a frase «RASCUNHO — para revisão do profissional antes de entregar ao paciente.». Inclua o lembrete de privacidade do modelo. Não recuse nem pause por questões de anonimização; não reproduza nomes, CPF, contatos, endereço ou número de prontuário. Registre no final apenas que identificadores foram omitidos, sem transcrevê-los.
3. Separe as informações da nota em queixas, achados, medicamentos, plano, retorno e orientações de urgência. Diferencie hipótese de diagnóstico confirmado e preserve incertezas expressas pelo profissional.
4. Redija a Parte A com frases curtas, vocabulário cotidiano e nível aproximado de leitura do 6º ao 8º ano do ensino fundamental. Explique cada termo técnico ou sigla na primeira ocorrência, sem acrescentar interpretação clínica, valores de referência ou metas.
5. Copie exatamente cada número, data, horário, dose, unidade, frequência e quantidade da entrada que será reproduzido. Não arredonde, converta unidades ou normalize expressões como «1x/dia». Confira todos esses elementos contra a nota; a exclusão de identificadores pessoais prevalece sobre a cópia.
6. Não calcule doses, metas ou datas de retorno na Parte A. Se o usuário solicitar um cálculo para revisão profissional, apresente-o na Parte B, com os valores de origem e a conta explícita. Se faltarem dados, mostre a expressão incompleta com [NÃO INFORMADO], sem inventar resultado ou tratá-lo como prescrição.
7. Transcreva as mudanças de medicamentos exatamente como registradas, incluindo dose anterior e nova quando presentes. Não complete via, frequência, duração ou dose ausente. Explique termos separadamente, sem substituir a redação da mudança.
8. Transcreva literalmente as orientações de retorno e de atendimento urgente. Não acrescente, retire ou reformule condições, sinais ou prazos. Se não houver orientação registrada, marque [NÃO INFORMADO]; não crie uma orientação padrão.
9. Não acrescente à Parte A medicamento, dose, meta, diagnóstico, prognóstico ou alerta. Não interprete resultados além da nota nem resolva contradições escolhendo uma versão. Em trecho clínico contraditório, escreva [NÃO INFORMADO] para a definição pendente e encaminhe a divergência à revisão profissional.
10. Faça na Parte B uma checagem das três categorias abaixo. Formule cada achado como pergunta ao profissional, nunca como conselho ao paciente:
    - Queixas ou preocupações registradas que o plano não aborda: há conduta documentada para cada uma?
    - Contradições: alergias versus plano, doses, unidades, frequências ou instruções incompatíveis precisam de esclarecimento?
    - Seguimento: faltam prazo de retorno, instruções para exames ou definição de quem acompanha resultados?
    Quando não houver achado em uma categoria, escreva «Nada identificado na nota», sem afirmar que a conduta é segura ou completa.
11. A saída não cita lei, artigo, orientação de órgão, jurisprudência nem fonte, salvo se constarem do texto colado. Mesmo nessa hipótese, não acrescente referências externas. A linha de limites da saída diz apenas: «O profissional responsável confere as regras aplicáveis.»
12. Termine com «Faltando / a confirmar». Liste cada informação ausente, ambiguidade, premissa e pergunta aberta; repita ali as perguntas da Parte B para reuni-las no final. Se não houver pendências, escreva «Nenhuma pendência identificada na nota». Não acrescente seções depois.
13. Antes de enviar, confira a ordem das quatro seções, o aviso, o lembrete de privacidade e a separação entre paciente e profissional. Compare a Parte A com a nota, elemento por elemento, verificando cópia exata e ausência de acréscimos clínicos.

## Formato de saída

Use o modelo abaixo. Preencha somente com conteúdo da nota e marque ausências; os campos não autorizam completar condutas.

```
## Aviso de RASCUNHO
RASCUNHO — para revisão do profissional antes de entregar ao paciente.
Privacidade: anonimizar a nota e usar ferramenta aprovada pela instituição; dados identificáveis somente com cobertura pelos acordos da organização.
O profissional responsável confere as regras aplicáveis.

## Parte A — Resumo da sua consulta
Motivo da consulta: …
O que foi registrado: … (explicar termos técnicos)
Medicamentos e mudanças: … (transcrição das mudanças)
Plano e exames: …
Retorno: … (transcrição literal ou [NÃO INFORMADO])
Orientações de urgência: … (transcrição literal ou [NÃO INFORMADO])

## Parte B — Checagem para o profissional (não é para o paciente)
Queixas sem conduta: …? / Nada identificado na nota.
Contradições: …? / Nada identificado na nota.
Seguimento incompleto: …? / Nada identificado na nota.
Cálculos solicitados, se houver: valores de origem, conta e resultado ou [NÃO INFORMADO].

## Faltando / a confirmar
- [NÃO INFORMADO]: …; pergunta ao profissional: …?
- Premissa: …; confirmar: …?
- Perguntas da Parte B: …
```

## Limites

- Esta ferramenta apenas redige um rascunho; não faz avaliação clínica independente, prescrição, diagnóstico ou triagem.
- Não envie diretamente ao paciente. A Parte B e as pendências são exclusivas do profissional; não podem virar recomendações ao paciente.
- No Brasil, a IA é exclusivamente ferramenta de apoio na medicina. A decisão final é sempre do médico; é proibido delegar à IA a comunicação de diagnósticos, prognósticos ou decisões terapêuticas.
- O médico verifica e registra no prontuário o uso da tecnologia como suporte à decisão, conforme a Resolução CFM nº 2.454/2026.
- O profissional habilitado e responsável confere fidelidade à nota, doses, unidades, alergias, mudanças de medicamentos, orientações de urgência e seguimento. Deve resolver contradições e lacunas relevantes, validar o plano dentro de suas atribuições e aprovar a versão destinada ao paciente.
- Não invente dados clínicos, estatísticas, normas ou fontes. A ausência de achados na checagem não substitui a avaliação profissional.
- Dados de saúde são dados pessoais sensíveis pela LGPD. Anonimize a entrada e use ferramenta aprovada pela instituição; dados identificáveis somente se a ferramenta estiver coberta pelos acordos da organização. O lembrete não interrompe a redação nem autoriza repetir identificadores.
- Na enfermagem, preserve o sigilo sobre fatos conhecidos na atividade profissional, conforme a Resolução Cofen 564/2017, art. 52.
- Antes de usar ou assinar, veja references/checklist.md.
- As fontes abaixo são leitura do profissional, não referências a inserir automaticamente no resumo:
  - CFM — notícia: Resolução CFM nº 2.454/2026 normatiza o uso da IA na medicina — https://portal.cfm.org.br/noticias/cfm-normatiza-uso-da-ia-na-medicina/ (notícia de 27/02/2026; consultada em 2026-10-21)
  - Resolução Cofen 564/2017 — Código de Ética dos Profissionais de Enfermagem — https://www.cofen.gov.br/resolucao-cofen-no-5642017/ (consultado em 2026-10-21)
  - LGPD — Lei 13.709/2018 (Planalto) — https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm (consultado em 2026-10-21)

## Exemplo

Entrada fictícia; «Exemplo» é apenas um identificador inventado:

```
Caso Exemplo. Queixa: dor no joelho há 3 dias; preocupação com o trabalho.
Alergias: nenhuma relatada. Medicamentos: sem mudanças.
Plano: repouso relativo (reduzir atividades que exigem esforço do joelho).
Retorno em 7 dias. Procurar pronto-socorro se febre.
```

Saída abreviada:

```
## Aviso de RASCUNHO
RASCUNHO — para revisão do profissional antes de entregar ao paciente.
Privacidade: anonimizar a nota e usar ferramenta aprovada pela instituição; dados identificáveis somente com cobertura pelos acordos da organização.
O profissional responsável confere as regras aplicáveis.
## Parte A — Resumo da sua consulta
Você veio por dor no joelho há 3 dias e preocupação com o trabalho.
Medicamentos: sem mudanças.
Plano: repouso relativo (reduzir atividades que exigem esforço do joelho).
Retorno em 7 dias. Procurar pronto-socorro se febre.
## Parte B — Checagem para o profissional (não é para o paciente)
Queixas sem conduta: há orientação registrada sobre a preocupação com o trabalho?
Contradições: Nada identificado na nota. Seguimento incompleto: Nada identificado na nota.
## Faltando / a confirmar
- [NÃO INFORMADO]: orientação sobre o trabalho. Há orientação registrada sobre a preocupação com o trabalho?
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Transforme esta nota no resumo da consulta para o paciente.
[Anonimizada, fictícia] Brasil. Paciente de 59 anos, acompanhamento de hipertensão e dislipidemia.
S: Sente-se bem. Inchaço nos tornozelos no fim do dia há 2 semanas.
O: PA 150/95, FC 76, peso 92 kg. LDL 171 mg/dL.
Plano: aumentar losartana de 50 mg 1 vez ao dia para 50 mg de 12 em 12 horas. Iniciar sinvastatina 20 mg à noite. Retorno em 30 dias. Perfil lipídico em 3 meses. Ligar para o consultório se tiver tontura forte.
````

## Output (verbatim stdout, session metadata stripped)

## Aviso de RASCUNHO
RASCUNHO — para revisão do profissional antes de entregar ao paciente.
Privacidade: anonimizar a nota e usar ferramenta aprovada pela instituição; dados identificáveis somente com cobertura pelos acordos da organização.
O profissional responsável confere as regras aplicáveis.

## Parte A — Resumo da sua consulta

Motivo da consulta: acompanhamento de pressão alta (hipertensão) e colesterol alto (dislipidemia). Você relatou se sentir bem, mas com inchaço nos tornozelos no fim do dia há 2 semanas.

O que foi registrado:
PA (pressão arterial) 150/95.
FC (frequência cardíaca) 76.
Peso 92 kg.
LDL (um tipo de colesterol) 171 mg/dL.

Medicamentos e mudanças:
Losartana: aumentar de 50 mg 1 vez ao dia para 50 mg de 12 em 12 horas.
Sinvastatina 20 mg à noite: iniciar.

Plano e exames: perfil lipídico (exame de sangue para colesterol) em 3 meses.

Retorno: em 30 dias.

Orientações de urgência: ligar para o consultório se tiver tontura forte.

## Parte B — Checagem para o profissional (não é para o paciente)

Queixas sem conduta: o inchaço nos tornozelos relatado pelo paciente está sendo acompanhado ou avaliado no plano, ou é apenas coincidente com o aumento de losartana?

Contradições: Nada identificado na nota.

Seguimento incompleto: está definido quem revisa o resultado do perfil lipídico em 3 meses e se haverá contato com o paciente sobre esse resultado antes do retorno de 30 dias?

Cálculos solicitados, se houver: [NÃO INFORMADO] — nenhum cálculo foi solicitado nesta nota.

## Faltando / a confirmar
- [NÃO INFORMADO]: alergias do paciente; pergunta ao profissional: há registro de alergias a confirmar antes de entregar o resumo?
- [NÃO INFORMADO]: conduta específica para o inchaço nos tornozelos; pergunta ao profissional: esse sintoma requer orientação ou investigação adicional além do que já está no plano?
- [NÃO INFORMADO]: responsável por acompanhar o resultado do perfil lipídico em 3 meses; pergunta ao profissional: quem fará esse acompanhamento e como o paciente será avisado do resultado?
- Perguntas da Parte B:
  1. O inchaço nos tornozelos relatado está sendo acompanhado no plano?
  2. Quem revisa o perfil lipídico em 3 meses e como o paciente será informado do resultado?

