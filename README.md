# SRAO Agent Graph

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![SRAO Framework](https://img.shields.io/badge/SRAO-Framework-blueviolet)](https://github.com/beixuan577?tab=repositories&q=srao)
[![Stage](https://img.shields.io/badge/Stage-2--3-orange)]()

> **Stop building agents in the dark. Map requirements to capabilities first.**
> Decompose structured requirements into atomic task DAGs, then map each task to the right agent type.

Part of the **SRAO Framework**. Requires SRM input from [SRAO-Domain-Modeler](https://github.com/beixuan577/SRAO-Domain-Modeler). Output feeds into [SRAO-Workflow-Orchestrator](https://github.com/beixuan577/SRAO-Workflow-Orchestrator).

---

## The Problem

You have a requirement. You start building agents. Six months later:

- Agents overlap in capability (3 agents all doing "analysis")
- Critical tasks have no agent assigned
- No one knows which agent to call for a given task
- Cross-industry reuse is zero

SRAO Agent Graph fixes this by making the mapping **explicit and systematic**.

## What It Does

**Stage 2 - Task Decomposition**
- Break SRM into atomic tasks with clear I/O schemas
- Build dependency DAGs (serial / parallel / conditional branches)
- Identify parallelizable tasks for concurrent execution

**Stage 3 - Agent Mapping**
- Classify every task into one of 6 agent categories
- Generate Agent Cards with capability, interface, SLA, and alternatives
- Detect cross-industry reuse opportunities
- Output agent graph with data flow and control flow edges

## 6 Agent Categories

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
4. Output agent graph feeds [SRAO-Workflow-Orchestrator](https://github.com/beixuan577/SRAO-Workflow-Orchestrator)

### Example: Wind Farm Health Monitoring

``
SRM Input: "Monitor turbine health with SCADA data, detect anomalies, predict failures"

Task DAG:
  T1: Read SCADA data     [Perceive]  -->  T2: Vibration analysis [Analyze]
                                         -->  T3: Temperature trend [Analyze]
  T2 + T3 -->  T4: Fault diagnosis [Decide]  -->  T5: Alert notification [Interact]
                                                  T6: Generate work order [Execute]

Agent Graph (Mermaid):
  graph TD
      A1[SCADA Agent<br/>Perceive] --> A2[FFT Agent<br/>Analyze]
      A1 --> A3[TimeSeries Agent<br/>Analyze]
      A2 --> A4[Diagnosis Agent<br/>Decide]
      A3 --> A4
      A4 --> A5[Alert Agent<br/>Interact]
      A4 --> A6[WorkOrder Agent<br/>Execute]
``

## Cross-Industry Reuse

One of the most powerful features — detect agents that work across industries:

| Agent | Reusable In |
|-------|-------------|
| Image defect detection | Manufacturing QC, Tunnel crack detection, Medical imaging |
| Time-series anomaly detection | Equipment monitoring, Weather forecasting, Financial risk |
| Path planning | Drone inspection, Logistics scheduling, Surgical navigation |
| Report generation | All industries |

## Agent Card Format

Every agent gets a standardized capability card:

`yaml
agent_card:
  id: AGT-001
  name: "Vibration FFT Agent"
  category: Analyze
  capability: "Perform FFT on vibration signals to detect frequency anomalies"
  input: { signal: time_series, sample_rate: number }
  output: { spectrum: array, anomalies: list }
  implementation: python_script  # or api_call, llm_chain, rule_engine
  sla:
    latency_p95: "2 seconds"
    accuracy: ">95%"
  alternatives:
    - name: "Wavelet Agent"
      tradeoff: "Better for transient signals, slower"
`

## SRAO Framework Pipeline

`
+----------------------+     +----------------------+     +-----------------------------+
| SRAO-Domain-Modeler  |---->| SRAO-Agent-Graph     |---->| SRAO-Workflow-Orchestrator  |
| (Model & Structure)  | SRM | (Decompose & Map)    | DAG | (Orchestrate & Monitor)     |
+----------------------+     +----------------------+     +-----------------------------+
`

## License

MIT