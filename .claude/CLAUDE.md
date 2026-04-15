# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a course examples repository for AI coding assistant tools. It is **documentation/reference only** — there is no application to build, test, or run. Files here are templates, rules, and skill definitions for various AI tools.

## Repository Structure

Each top-level directory corresponds to a different AI coding assistant tool:

- `claude-code/` — Rules and skills for Claude Code (this tool). Rules are auto-loaded via this CLAUDE.md.
- `cursor/` — Cursor rules (`.mdc` format), commands, and skills
- `copilot/` — GitHub Copilot instructions, reusable prompts, and skills
- `windsurf/` — Windsurf rules and workflows
- `antigravity/` — Google Antigravity rules, skills, and workflows

Each tool directory follows a similar pattern: `rules/`, `skills/`, and sometimes `workflows/` or `commands/` subdirectories.

## Key Conventions

- Most files include a `source:` frontmatter field linking to the original upstream repo
- Skills use a `SKILL.md` entry point in their directory
- Antigravity skills may include a `metadata.json`
- Copilot instructions use `.instructions.md` suffix; prompts use `.prompt.md` suffix
- Cursor rules use `.mdc` format with frontmatter
