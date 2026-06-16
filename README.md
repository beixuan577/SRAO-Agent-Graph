# SRAO Agent Graph

> **SRAO Stage 2-3**: Agent capability graph construction

Part of the [SRAO Framework](https://github.com/beixuan577?tab=repositories&q=srao) — a systematic methodology for building multi-agent workflow orchestration systems across industries.

## What It Does

Takes Structured Requirement Models (SRM) and produces a complete agent cluster blueprint:

- **Stage 2 — Task Decomposition**: Break SRM into atomic tasks with dependency DAGs (serial/parallel/conditional)
- **Stage 3 — Agent Mapping**: Map each task to one of 6 agent categories, generate Agent Cards with I/O schemas and SLAs

## Key Features

- 🧩 6-category agent taxonomy: Perceive, Analyze, Decide, Execute, Interact, Orchestrate
- 📊 Atomic task DAG with I/O schemas and parallel group detection
- 🤖 Agent Card format: capability, interface, SLA, alternatives
- 🔀 Cross-industry reuse detection (e.g., image defect detection works for manufacturing, tunnel inspection, and medical imaging)
- 📈 Mermaid graph visualization

## Agent Categories

| Category | Role | Example |
|----------|------|---------|
| **Perceive** | Acquire external data | Image recognition, ASR, IoT collection |
| **Analyze** | Compute, reason, predict | Simulation, time-series forecasting, KG reasoning |
| **Decide** | Recommend or act autonomously | Threshold alert, path planning, resource allocation |
| **Execute** | Control hardware/software | Robot control, email sending, DB write |
| **Interact** | Communicate with users/systems | Dialog, report generation, API gateway |
| **Orchestrate** | Manage other agents | Workflow monitor, failover, circuit breaker |

## Quick Start

1. Feed SRM output from [SRAO-Domain-Modeler](https://github.com/beixuan577/SRAO-Domain-Modeler)
2. The graph builder decomposes requirements into a task DAG
3. Each task is mapped to an agent with a capability card
4. Output agent graph can be fed to [SRAO-Workflow-Orchestrator](https://github.com/beixuan577/SRAO-Workflow-Orchestrator)

## SRAO Framework

`
SRAO-Domain-Modeler ──SRM──> SRAO-Agent-Graph ──DAG+Graph──> SRAO-Workflow-Orchestrator
   (Model & Structure)         (Decompose & Map)              (Orchestrate & Monitor)
`

## License

MIT
