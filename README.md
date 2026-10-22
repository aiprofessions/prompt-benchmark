# Prompt benchmark: AI on real professional tasks

Open data behind the test results published on [AI Professions](https://aiprofessions.ai): **100 prompts** for real tasks in
ten professions plus Excel / Microsoft 365, in four languages (34 EN, 22 ES, 22 FR, 22 PT), run on **5 models × 3 runs**
and graded criterion by criterion: **1,500 runs, 7,500 verdicts**. Every transcript is here,
verbatim.

Live results and the method in plain words: [AI model test results](https://aiprofessions.ai/models/ai-model-test-results/) ·
[Methodology](https://aiprofessions.ai/methodology/).

## How it was tested

1. **Rubric first.** For each prompt a fictional input and 5 pass/fail criteria (one of them a SAFETY criterion: no
   invented figures, facts or citations) were written, and the SHA-256 of (prompt, input, rubric) was locked **before
   any model saw the prompt**. The harness refused runs with a mismatched hash.
2. **3 runs per model**, plain chat, no tools, no web, no memory.
3. **Cross-family judge.** Claude and Gemini outputs were graded by `gpt-6-astra`; `gpt-6-astra` outputs by
   `claude-opus-5-5`. One strict JSON verdict per criterion; an unsure judge had to fail it.
4. **Checks on the judge.** Judge-swap calibration on a seeded sample and an editor spot-check
   (`transcripts/bench/calibration*.json`, `spotcheck*.json`). The two judges differ in strictness, so compare
   Claude-vs-GPT scores with caution; models graded by the same judge compare directly.

| Model | Prompts | Graded runs | Judge |
|---|---|---|---|
| `claude-fable-5-1` | 100 | 300 | `gpt-6-astra` |
| `claude-opus-5-5` | 100 | 300 | `gpt-6-astra` |
| `claude-sonnet-5` | 100 | 300 | `gpt-6-astra` |
| `gemini-4-argon-medium` | 100 | 300 | `gpt-6-astra` |
| `gpt-6-astra` | 100 | 300 | `claude-opus-5-5` |

## What is inside

| Path | Content |
|---|---|
| `prompts/<id>.yaml` | Prompt, scenario, fictional sample input, profession, task, jurisdictions, link to the live page |
| `results/<id>.yaml` | Locked rubric + `rubric_sha256`, judges, calibration, per-model results (run scores, average criteria passed) |
| `data/results.csv` | One row per prompt × model — the quickest way in |
| `transcripts/` | Every run verbatim, per-criterion verdicts, rubric locks, calibration, spot-checks, the Claude Skills rounds. See [transcripts/README.md](./transcripts/README.md) |

Prompt ids: `<profession>-<lang>-<task>-NN` (`acc` accountants, `law` lawyers, `re` real estate, `hc` healthcare,
`ev` event planners, `eng` engineers, `ta` travel agents, `cm` construction managers, `sm` sales managers,
`id` interior designers, `xl` Excel, `m365` Microsoft 365).

## Limits

All inputs are fictional. A pass means an output met these criteria on this input; it is not a professional
sign-off, not a test of the consumer apps (ChatGPT, Claude.ai, Gemini app, Copilot) and not a guarantee for other
inputs. The judges are LLMs, checked by calibration and an AI editor spot-check, not by a human review of every output.

## License and citation

[CC BY 4.0](./LICENSE). Credit: **AI Professions (aiprofessions.ai)**. Citation metadata: [CITATION.cff](./CITATION.cff).

Related: [aiprofessions/claude-skills](https://github.com/aiprofessions/claude-skills) — 10 tested Claude Skills in 4 languages.
Corrections: open an issue or write to nick@aiprofessions.ai.
