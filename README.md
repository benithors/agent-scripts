# Agent Scripts

A public collection of reusable agent workflows and prompts.

## Skills

- `/agent-browser` — automate browser, website, and Electron app workflows with the agent-browser CLI.
- `/autoreview` — run structured Codex or Claude code reviews before commit or ship.
- `/brainstorm` — generate and explore ideas before choosing a direction.
- `/create-cli` — design command-line interfaces, flags, help, output, errors, config, and dry-run behavior.
- `/frontend-design` — build distinctive, polished frontend UI instead of generic layouts.
- `/grill-me` — interview the user relentlessly to stress-test a plan, design, or approach.

Each one lives in `skills/<name>/SKILL.md`.

Skills are reusable workflows. Matt Pocock's convention is: user-invoked skills set `disable-model-invocation: true`; model-invoked skills omit that field and keep a model-facing `description`.

## Prompts

- `prompts/security-audit.md` — phased, report-only security audit prompt.

Prompts are manual, explicit-use instructions. They live outside `skills/` so agents do not invoke every workflow by themselves.

Codex CLI does not currently use `disable-model-invocation` to control skill invocation. For Codex, implicit skill use is controlled by `agents/openai.yaml` with `policy.allow_implicit_invocation`; keep Codex-only manual workflows in `prompts/`.

## Acknowledgements

This collection builds on ideas from Matt Pocock and Brian Madison’s agent workflow methodology. I love their work.

- `/autoreview` and `/create-cli` are from Peter Steinberger’s `agent-scripts` repo.
- `/frontend-design` is from Anthropic.
- `/grill-me` is from Matt Pocock’s `skills` repo.
- `/brainstorm` is an adaptation of the BMAD brainstorm skill.
