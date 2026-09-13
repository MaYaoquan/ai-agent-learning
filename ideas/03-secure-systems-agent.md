# Secure Systems Agent

## Goal

Build a domain-specialized agent for Linux, networking, containers, cloud, and security operations.

## Motivation

A domain agent can combine strong systems knowledge with controlled tool execution instead of behaving like a generic chatbot with shell access.

## Core Idea

The agent should diagnose first, gather evidence with low-risk read-only actions, propose remediation, request approval for risky changes, execute safely, and verify the result.

```mermaid
flowchart TD
    A[Problem] --> B[Generate Hypotheses]
    B --> C[Diagnostic Plan]
    C --> D[Read-only Evidence Collection]
    D --> E[Root Cause Assessment]
    E --> F[Proposed Remediation]
    F --> G[Risk / Approval]
    G --> H[Execute]
    H --> I[Verify]
    I --> J{Resolved?}
    J -- Yes --> K[Complete]
    J -- No --> L[Replan / Rollback]
```

## Possible Domains

- Linux troubleshooting
- TCP/IP and network diagnosis
- Docker and Kubernetes
- cloud infrastructure
- security operations
- performance troubleshooting

## North-Star Goal

> Build an AI agent that I would actually trust with root access to a production Linux server.

## Next Experiment

Create a read-only Linux diagnostic skill that can inspect CPU, memory, processes, disks, networking, and logs without modifying the system.
