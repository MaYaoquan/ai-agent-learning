# 03 Core Components

## Agender

```text
AI Agent
├── Model
├── Context
├── State
├── Actions
├── Control Loop
└── Runtime
```

Core Components Table
| Component | Core Question | Responsibility |
|---|---|---|
| **Model** | Who thinks? | Reasoning and decision-making |
| **Context** | What does it currently know? | Information given to the model |
| **State** | What does it remember? | Persistent task information |
| **Actions** | What can it do? | Interact with the environment |
| **Control Loop** | How does it progress? | Coordinate iterative execution |
| **Runtime / Harness** | Who manages everything? | Orchestrate the whole Agent |


## Model

The Model of an AI Agent is the reasoning and decision-making component of an AI Agent system. It's usually implemented as a large language model, such as GPT, Claude, DeepSeek, Gemini, or Llama.

```text
          Model
            │
            ▼
Observe → Decide → Action
```

**Key Idea**:
The runtime controls the loop, while the model makes decisions inside the loop.

## Context

The model does not directly observe the environment. It reasons over the context provided by the agent runtime.

### Definition:
Context is the set of information made available to the model for a specific inference or decision.

```text
Agent State / Memory / Environment
              ↓
        Context Builder
              ↓
           Context
              ↓
            Model
              ↓
          Decision
```

Context may contain:
```text
Context
│
├── System Instructions
│
├── User Request / Goal
│
├── Conversation History
│
├── Current Task State
│
├── Previous Actions
│
├── Tool Observations / Results
│
├── Retrieved Knowledge
│
├── Skill Instructions
│
├── Available Tool Descriptions
│
└── Environment Information
```

For example: Find the largest Python file and explain it.
```text
System:
You are a coding assistant.

User Goal:
Find the largest Python file and explain what it does.

Current State:
Repository inspection is in progress.

Previous Observation:
There are 200 Python files.

Previous Action:
Calculated file sizes.

New Observation:
agent.py is the largest file.

Available Actions:
- read_file
- list_files
- search_code

Current Question:
What should I do next?
```

The most common context format is structured data, like JSON.

```json
{
  "messages": [
    {
      "role": "system",
      "content": "You are a coding agent."
    },
    {
      "role": "user",
      "content": "Find the largest Python file."
    },
    {
      "role": "assistant",
      "content": "I will inspect the repository."
    },
    {
      "role": "tool",
      "content": "agent.py: 120 KB"
    }
  ],
  "tools": [
    {
      "name": "read_file",
      "description": "Read a file from the repository"
    }
  ]
}
```

**Note**: The APIs of different models actually use different schemas. 

Therefore, the context can be serialised into 

#### Key Idea:

Context is model-visible information, not necessarily plain text.

## State

## Actions

## Control Loop

## Runtime/Harness
