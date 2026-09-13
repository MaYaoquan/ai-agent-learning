# Project Direction

## Goal

Use the first practical AI-agent projects after the fundamentals phase to strengthen both engineering capability and interview readiness.

The recommended progression is:

1. Build an **SRE / Network Agent** first.
2. Build a **Secure Agent Runtime** next.
3. Combine both into a **Secure Systems Agent** as the longer-term portfolio project.

---

## Phase 1 — SRE / Network Agent

### Why start here?

An SRE / Network Agent is a good first practical agent because it turns agent fundamentals into a realistic troubleshooting workflow.

A typical task might be:

> Pod A can reach Pod B directly, but access through Service B times out. Diagnose the issue.

The agent could:

```text
Collect system/network state
        ↓
Generate hypotheses
        ↓
Run read-only diagnostics
        ↓
Evaluate evidence
        ↓
Identify likely root cause
        ↓
Propose remediation
```

Possible capabilities include:

- Linux troubleshooting
- TCP/IP diagnostics
- process and socket inspection
- routing analysis
- DNS troubleshooting
- iptables / nftables inspection
- conntrack inspection
- container and Kubernetes diagnostics
- service / endpoint analysis
- log inspection

### Interview Value

This project can demonstrate several areas at the same time:

- AI Agent architecture
- Agent Loop design
- Context and State management
- Tool execution
- planning and hypothesis generation
- Linux and networking knowledge
- root-cause analysis
- observability
- safe execution boundaries

It also creates natural system-design and troubleshooting interview questions, such as:

- How does the agent maintain state across troubleshooting steps?
- How does it avoid repeating the same diagnostic action?
- How does it distinguish observation from inference?
- How does it verify that a proposed fix actually solved the problem?
- How should the agent handle incomplete or contradictory evidence?

---

## Phase 2 — Secure Agent Runtime

Once the SRE / Network Agent starts interacting with real systems, several engineering problems appear naturally:

```text
How much shell access should the agent have?
How should sudo be controlled?
Which operations require approval?
How are dangerous actions blocked?
How are actions audited?
How is a failed change rolled back?
How is successful remediation verified?
```

These requirements motivate a dedicated **Secure Agent Runtime**.

Core capabilities should include:

- capability-based permissions
- least privilege
- command and argument validation
- risk classification
- human approval gates
- sandboxed execution
- dry-run support
- post-action verification
- rollback
- event tracing
- audit logs
- session replay
- loop / no-progress detection

A possible execution path is:

```text
Agent Decision
      ↓
Action Request
      ↓
Policy / Risk Engine
      ↓
Permission Check
      ↓
Optional Human Approval
      ↓
Sandbox / Controlled Execution
      ↓
Verification
   ┌──┴──┐
Success  Failure
   │        │
Commit   Rollback
   └──┬─────┘
      ↓
Audit Trail
```

### Interview Value

This project can support deeper discussions around:

- least privilege
- capability-based security
- sandboxing
- secure tool execution
- policy enforcement
- transactional execution
- failure recovery
- observability
- reproducibility
- trust in autonomous systems

---

## Phase 3 — Secure Systems Agent

The longer-term project combines the domain-specialized SRE / Network Agent with the Secure Agent Runtime.

```text
              SRE / Network Agent
                      │
                      ▼
              Secure Agent Runtime
                      │
       ┌──────────────┼──────────────┐
       │              │              │
    Planner       Policy Engine   Audit / Replay
       │              │              │
       └─────── Controlled Actions ───┘
                      │
                      ▼
              Real Linux / Network /
             Container / Cloud Systems
```

The goal is not merely to build an agent that can run commands.

The goal is to build an agent that can interact with real systems in a way that is:

- useful
- explainable
- observable
- permission-aware
- verifiable
- recoverable
- auditable

A useful long-term north-star question is:

> **What engineering mechanisms would be required before I would trust an AI agent with privileged access to a production Linux system?**

---

## Plan Development Path

```text
AI Agent Fundamentals
        ↓
MiniClaw
        ↓
SRE / Network Agent v0.1
        ↓
Secure Agent Runtime v0.1
        ↓
Secure Systems Agent
        ↓
Evaluation / Replay / Adaptive Model Routing
```

The SRE / Network Agent provides a concrete problem domain.

The Secure Agent Runtime provides the safety and reliability mechanisms required to operate in that domain.

Together, they can become a strong portfolio project for AI infrastructure, systems, networking, cloud, platform, SRE, and security-oriented software engineering interviews.
