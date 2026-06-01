# Agent Scripts

A public collection of reusable agent workflows and prompts.

## Skills

- `/brainstorm` — generate and explore ideas before choosing a direction.
- `/create-cli` — design command-line interfaces, flags, help, output, errors, config, and dry-run behavior.
- `/frontend-design` — build distinctive, polished frontend UI instead of generic layouts.
- `/grill-me` — interview the user relentlessly to stress-test a plan, design, or approach.

Each one lives in `skills/<name>/SKILL.md`.

Skills are agent-discoverable workflows. Keep something as a skill only when it is useful for an agent to invoke it from task context.

## Prompts

- `prompts/security-audit.md` — phased, report-only security audit prompt.

Prompts are manual, explicit-use instructions. They live outside `skills/` so agents do not invoke every workflow by themselves.

## Acknowledgements

This collection builds on ideas from Matt Pocock and Brian Madison’s agent workflow methodology. I love their work.

- `/create-cli` is from Peter Steinberger’s `agent-scripts` repo.
- `/frontend-design` is from Anthropic.
- `/grill-me` is from Matt Pocock’s `skills` repo.
- `/brainstorm` is an adaptation of the BMAD brainstorm skill.
