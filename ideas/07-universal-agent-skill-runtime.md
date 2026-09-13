# Universal Agent Skill Runtime

## Goal

Define a portable skill representation that can be adapted to multiple agent ecosystems.

## Motivation

Different agent systems expose similar concepts such as instructions, skills, tools, MCP connections, permissions, hooks, and sessions, but their formats are not identical.

## Core Idea

Define a neutral internal skill specification and provide exporters/adapters for different runtimes.

```text
Universal Skill Definition
          ↓
     Skill Adapter
   ┌──────┼──────┬────────┐
   ↓      ↓      ↓        ↓
Claude   Codex  OpenClaw  Other Harnesses
```

A possible internal schema could include:

```yaml
name:
description:
instructions:
requires:
  tools:
  mcp:
permissions:
tests:
```

## Potential Commands

```text
agent-skill install network-debug
agent-skill test network-debug
agent-skill export --target codex
agent-skill export --target claude
```

## Open Questions

- Which concepts are portable across ecosystems?
- Which provider-specific features should remain extensions?
- How should permissions and tests be represented?
- Can one skill definition preserve semantics across runtimes?

## Next Experiment

Compare a simple file-analysis skill across two agent runtimes and identify the minimum common schema.
