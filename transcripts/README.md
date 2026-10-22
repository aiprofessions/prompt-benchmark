# Test transcripts — October 2026 bench

This archive holds every transcript, verdict and locked rubric behind the test results published on the site
(prompt library, data report and methodology page). Everything in it is fictional test material: the sample inputs
were written for the bench and contain no real clients, patients or cases.

Licence: everything in this archive (prompts, inputs, rubrics, transcripts, verdicts, results and the Claude Skills
texts) is published under Creative Commons Attribution 4.0 International (CC BY 4.0,
https://creativecommons.org/licenses/by/4.0/). Credit: AI Professions (aiprofessions.ai). Also on GitHub:
https://github.com/aiprofessions/prompt-benchmark

## What is inside

| Folder | Content |
|---|---|
| `prompts/<prompt_id>/spec.yaml` | The prompt, its fictional input, the 5-criterion rubric, `round`, and the rubric hash locked before the first run |
| `prompts/<prompt_id>/<model>-runN.md` | One transcript per run: header (model id, provider, start time UTC, duration, exit code, rubric hash), the exact query, the verbatim output |
| `prompts/<prompt_id>/grades.json` | Per-criterion verdicts (pass/fail + one-line reason) for every run, with the judge model |
| `prompts-es2/<prompt_id>/` | ES round 2 (10 new Spanish prompts, 2026-10-21): same layout as `prompts/` |
| `tools/<prompt_id>/` | Excel / Microsoft 365 task round: same layout as `prompts/` (spec, transcripts, grades, calibration re-grades) |
| `prompts/<prompt_id>/calib-<model>-runN.json` | Judge-swap re-grades (only for the runs sampled for calibration) |
| `bench/results.json` | Aggregated results per prompt and model |
| `bench/rubrics.lock.json` | SHA-256 of (prompt, input, rubric) per prompt and the lock time |
| `bench/calibration.json`, `bench/calibration-frpt.json` | Judge-swap calibration, round 1 (EN/ES) and round 2 (FR/PT) |
| `bench/spotcheck.json`, `bench/spotcheck-frpt.json` | Spot-check of judge verdicts by the editor agent, round 1 and round 2 |
| `bench/*-fable*.json`, `bench/*-argon*.json` | Calibration and spot-check for the added models (Claude Fable 5.1, Gemini 4 Argon) |
| `bench/*-tools.json` | Excel / Microsoft 365 round: results, rubric lock, calibration, spot-check |
| `bench/*-es2.json` | ES round 2: results, rubric lock, calibration, spot-check |
| `skills/<skill>/<lang>/` | Claude Skills round: current transcripts and per-run grades (`grade-<model>-runN.json`) |
| `skills/<skill>/<lang>/v1.0/`, `v1.1/` | ARCHIVED earlier skill versions (not the published text): the `SKILL.md` that was tested and its transcripts and grades |
| `skills/<skill>/<lang>/stale/` | Runs set aside because the skill text embedded in the query no longer matched the current `SKILL.md`; they were re-run and are kept for completeness |
| `skills/_bench/` | Skill specs and rubrics (`specs.yaml`; FR/PT: `specs-frpt.yaml`), rubric locks, results (all four languages), revision findings |

Counts: 80 prompts, 1200 prompt transcripts; 10 Excel / Microsoft 365 prompts,
150 transcripts; 10 ES round 2 prompts, 150 transcripts; 10 skills in
English and Spanish: 180 current skill transcripts, 114 from earlier
skill versions, 33 set-aside runs; the same skills in French and Brazilian Portuguese:
180 current transcripts, 45 from earlier versions.

## Rounds and dates (UTC, start times of the runs)

- Round 1 — 30 English + 10 Spanish prompts: 2026-10-19 11:34 to 2026-10-19 12:20.
- Round 2 — 20 French + 20 Brazilian Portuguese prompts: 2026-10-19 18:59 to 2026-10-19 20:09.
- Claude Skills round, English and Spanish (current versions): 2026-10-19 14:50 to 2026-10-19 16:13.
- Fable round — `claude-fable-5-1` added on the SAME locked material: all 80 prompts of rounds 1 and 2 (240 transcripts) and the current Claude Skills (60 transcripts): 2026-10-20 09:05 to 2026-10-20 10:41.
- Gemini round — `gemini-4-argon-medium` added on the SAME locked material: all 80 prompts of rounds 1 and 2 (240 transcripts): 2026-10-20 11:16 to 2026-10-20 11:54. Not run on the Claude Skills (a Claude format).
- Excel / Microsoft 365 task round — 10 new prompts (4 English, 2 Spanish, 2 French, 2 Brazilian Portuguese; profession `any`, tools `excel` / `microsoft-365`), all 5 models x 3 runs (150 transcripts): 2026-10-20 12:33 to 2026-10-20 12:43. Text-only answers: formulas were judged by their logic and the stated result on the given data, not executed in Excel. These are chat models answering a pasted task, not Copilot inside Excel or Microsoft 365.
- ES round 2 — 10 new Spanish prompts (separately locked set `bench/rubrics.lock-es2.json`), all 5 models x 3 runs (150 transcripts, folder `prompts-es2/`): 2026-10-21 04:38 to 2026-10-21 05:17. Same judges, judge-swap calibration (`bench/calibration-es2.json`) and spot-check (`bench/spotcheck-es2.json`) as the other rounds.
- Claude Skills FR/PT round — French (France) and Brazilian Portuguese adaptations of the 10 skills, `claude-opus-5-5`, `claude-sonnet-5`, `claude-fable-5-1` x 3 runs, graded by `gpt-6-astra` on rubrics locked separately (`skills/_bench/specs-frpt.yaml`, `skills/_bench/rubrics.lock-frpt.json`); current versions: 180 transcripts, 2026-10-21 05:41 to 2026-10-21 09:55. Four adaptations were revised after the first run and re-tested on the same locked input; the earlier texts and their runs are kept as evidence in `v1.0/` / `v1.1/` folders (construction-daily-report-delay-notice/fr/v1.0, construction-daily-report-delay-notice/fr/v1.1, event-planners-vendor-rfp/fr/v1.0, event-planners-vendor-rfp/pt/v1.0, sales-managers-pipeline-review/fr/v1.0; 45 transcripts). No judge-swap calibration or spot-check was run on this round.

## Models

| Model id | Provider (as recorded) | Role |
|---|---|---|
| `claude-opus-5-5` | anthropic | tested model; judge of `gpt-6-astra` outputs |
| `claude-sonnet-5` | anthropic | tested model |
| `gpt-6-astra` | openai | tested model; judge of Claude outputs (prompts and skills) |
| `claude-fable-5-1` | anthropic | tested model (added 2026-10-20, prompts and skills) |
| `gemini-4-argon-medium` | google | tested model (added 2026-10-20, prompts only) |

Claude and GPT runs were sent through an agent command-line client in safe mode (tools, web access, memory and custom
instructions off). The client adds its own generic assistant system instruction, identical for every model.
Claude models were reached through a routing service on a subscription, `gpt-6-astra` through an OpenAI subscription
sign-in.

`gemini-4-argon-medium` was reached through Google's Antigravity command-line agent, not a plain API call. Each run used
a custom agent with no tools, skills or rules loaded and a one-line system prompt ("You are a helpful assistant."),
started in a fresh empty folder in sandbox mode with permission prompts not auto-approved. The client still wraps the
query with the local time and a model-selection note, and it still exposes one built-in tool (listing or stopping
background tasks). After each run the client's own log was read: a run with any tool call would not have counted as
completed. In this archive: 0 tool calls, 1 turn per run. The `agy_usage` header line is the token count the client
reported. Nothing was edited by hand between the query and the output.

## How the rubrics were locked

Before any model saw a prompt, its rubric was written and the SHA-256 of (prompt, input, rubric) was stored in
`bench/rubrics.lock.json` (skills: `skills/_bench/rubrics.lock.json`, hash of skill, language, input and rubric).
The harness refused any run whose hash did not match. Every transcript header carries `rubric_sha256`; skill
transcripts also carry `skill_sha256`, the hash of the exact `SKILL.md` text embedded in the query.
You can recompute a prompt hash as
`sha256(json.dumps([prompt, input, rubric], ensure_ascii=False, sort_keys=True))`.

## How the judging worked

- Cross-family: `gpt-6-astra` graded Claude outputs and Gemini outputs, `claude-opus-5-5` graded `gpt-6-astra` outputs.
  The skills round has only Claude models, so all skill runs were graded by `gpt-6-astra`.
- One strict JSON verdict per criterion (pass/fail + one-line reason); an unsure judge had to mark fail.
- Calibration: a seeded sample of runs was re-graded by the other judge (`bench/calibration*.json`; the added
  models have their own files `bench/calibration-fable-*.json`, `bench/calibration-argon-*.json`, and the Excel /
  Microsoft 365 round `bench/calibration-tools.json`).
- Spot-check: the editor agent operating the bench (an AI agent, not a human) wrote its own verdict from the full
  transcript before reading the judge's (`bench/spotcheck*.json`).
- No judge-swap calibration or spot-check was run on the skills rounds (English/Spanish incl. the Fable runs, and
  French/Portuguese).

## What was removed (sanitizing)

Command lines, session and conversation ids, local file paths and run-meta files were removed; provider names are
reduced to the vendor (`anthropic`, `openai`, `google`). Queries and outputs are otherwise verbatim.

## What a pass does not mean

A pass means an output met these rubric criteria on this fictional input. It is not a professional sign-off,
not a test of the consumer apps (ChatGPT, Claude.ai, Copilot), and not a guarantee for other inputs.
