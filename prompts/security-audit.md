# Security Audit Prompt

Run this as a phased, report-only security audit. Do not edit app code.

## Phase 1: Structural Scan

First, do a brief structural scan of the repository.

Identify stack, package manager, deploy target, generated/cache/vendor dirs to exclude, and obvious security-relevant surfaces.

## Phase 2: Subagent Recon And Tool Selection

Spawn `{x}` subagents, each focused on one area:

- Tech stack

- Architecture

- Databases/persisted state

- Security-relevant attack surface

Do not fix anything yet and close them after they are done.

Each subagent should identify repo-specific risks and recommend high-leverage open-source detective, report-only security tools for finding bugs and vulnerabilities in this repo.

Prefer tools that:

- Have an OSI-style open-source local CLI/engine, not only a free SaaS tier.

- Address a repo-specific risk or workflow gap.

- Are practical to run locally with CLI.

- Complement rather than duplicate another selected tool.

- Have a clear first read-only assessment use case in this codebase.

- If multiple tools occupy the same category, pick the canonical/upstream tool unless a fork or alternative has a concrete repo-specific advantage.

Consolidate the subagent recommendations into a final repo-relevant tool list, and save those tools under /audit/tools.md

## Phase 3: Audit Workspace And Tool Runs

Prepare a report-only security audit workspace in `/audit` for this repo.

Run a brief preflight: identify available tools and blockers.

For each selected tool, create config/commands under `/audit`, then spawn a subagent to run it with outputs in `/audit/results.md`. Batch agents if needed.

Use clear excludes for generated/cache/vendor dirs.

Run dynamic tools only against a local disposable target; if unavailable, record the blocker instead of inventing findings.

## Phase 4: Report

Filter duplicates and low-confidence noise by root cause.

Report only high and critical issues into `audit/security_audit_ddmmyy.md` and give me a Risk Register Table
