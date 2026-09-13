# Agent Observability and Replay

## Goal

Make agent execution inspectable, debuggable, measurable, and reproducible.

## Motivation

For long-running or autonomous agents, chat history alone is not enough. We need a structured execution trace showing decisions, actions, tool results, state changes, permissions, failures, and verification outcomes.

## Core Idea

Record an append-only execution trajectory.

```text
Task
├── Model decision
├── Action request
├── Permission decision
├── Tool execution
├── Observation
├── State update
├── Verification
└── Final outcome
```

## Useful Metrics

- model latency
- tool latency
- token usage
- cost
- number of iterations
- tool failure rate
- retries
- permission denials
- task success rate
- verification result

## Replay Idea

A stored session could later be replayed with:

- the same model
- a different model
- mocked tool results
- different policies

This enables regression testing and model comparison.

## Next Experiment

Add a JSONL event log to MiniClaw where every model call, action, observation, and state transition is recorded.
