# Day 27 – Structured Tool Calling Agent 🤖

A structured tool-calling AI agent built with **Python, OpenAI API, and FastAPI**.

This project rebuilds the manual ReAct agent from Day 26 using OpenAI's structured function/tool calling approach. Instead of parsing tool calls from raw LLM text, the model returns structured tool calls with function names and typed arguments.

## 🎯 Objective

The main goal of this project is to compare:

- Day 26: Manual ReAct + raw text parsing
- Day 27: Structured Function/Tool Calling

The project measures how structured tool calling improves reliability, argument handling, and multi-step tool execution.

---

## 🛠️ Tech Stack

- Python
- OpenAI API
- FastAPI
- Pydantic
- Uvicorn
- JSON Schema
- Function / Tool Calling

---

## 🔧 Tools Implemented

The agent supports four tools:

### 1. `search_documents`

Searches the available document knowledge base.

### 2. `get_weather_stub`

Returns simulated weather information for a requested location.

### 3. `calculate`

Performs mathematical calculations.

### 4. `get_today`

Returns the current date.

Each tool is defined using a structured JSON schema containing:

- Tool name
- Description
- Parameters
- Parameter types
- Required fields

---

## 🔄 Tool Execution Flow

The agent follows this workflow:

```text
User Question
      ↓
OpenAI Model
      ↓
Structured Tool Call
      ↓
Tool Name + JSON Arguments
      ↓
Argument Validation
      ↓
Python Tool Execution
      ↓
Tool Result
      ↓
OpenAI Model
      ↓
Final Answer
