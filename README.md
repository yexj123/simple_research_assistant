# Building a Simple Research Assistant: From Raw API to Agentic AI

A progressive, step-by-step exploration of agentic design patterns in Python focused on OpenAI API.

## Purpose
This repository isn't aimed at building a feature-complete product. Instead, its goal is to demonstrate **how agentic AI systems are constructed from first principles**—moving from basic API calls to manual loop orchestration, and automated version using OpenAI Agents SDK.

## Learning Roadmap

```text
Streaming
        ↓
Structured Outputs
        ↓
Tool Calling
        ↓
Debugging Tool Calls
        ↓
Manual Reflection Loop
        ↓
OpenAI Agents SDK
```

## Stage 1 — Streaming Chat

Learn the basics of the OpenAI Responses API.

Features:
- Streaming responses
- Conversation memory using `previous_response_id`
- System instructions
- Interactive CLI

Concepts:
- Responses API
- Streaming events
- Conversation state

## Stage 2 — Structured Outputs

Use Pydantic models for type-safe structured responses.

```python
class ResearchExtraction(BaseModel):
    summary: str
    key_points: List[str]
    confidence_score: float
```

## Stage 3 — Tool Calling

Add a custom DuckDuckGo search tool.

```text
User
  ↓
Model
  ↓
Function Call
  ↓
DuckDuckGo Search
  ↓
Search Results
  ↓
Model
  ↓
Structured Output
```

## Stage 4 — Debugging Tool Calls

Inspect response objects, tool calls, parsed arguments, and parsed outputs to understand the API internals.

## Stage 5 — Manual Reflection Workflow

Validate the generated summary and automatically retry with feedback if validation fails.

```text
Generate
   ↓
Validate
   ↓
Fail
   ↓
Feedback
   ↓
Generate Again
```

Concepts:
- Reflection
- Retry loops
- Agent orchestration

## Stage 6 — OpenAI Agents SDK

Reimplement the workflow using the OpenAI Agents SDK with a Research Agent and Reviewer Agent.

```text
User
  │
  ▼
Research Agent
  │
  ▼
Reviewer Agent
  ├── Approved → Final Output
  └── Needs Revision → Research Agent
```
