---
name: srao-agent-graph
description: 智能体图谱构建（SRAO阶段2-3）。将结构化需求(SRM)拆解为原子任务DAG，映射为智能体能力图谱，输出可实例化的Agent集群蓝图。触发词：智能体图谱、Agent图谱、任务拆解、原子任务、DAG、智能体设计、Agent设计、能力映射、智能体注册、任务解构、Agent集群设计、能力图谱。当用户已明确需求和领域模型，需要设计具体Agent集群方案时使用。
---

# SRAO 智能体图谱构建器

将需求拆解为原子任务，映射为智能体，输出可执行的Agent集群蓝图。

## 前置条件

需先完成 `srao-domain-modeler` 的领域建模和需求结构化，获得 SRM 文档。
若用户直接使用本 skill，先快速补建 SRM 的关键部分（domain、goals、workflow_ref）。

## 核心流程

```
SRM文档 → 任务拆解(阶段2) → 智能体映射(阶段3) → 输出Agent图谱
```

## 阶段2：任务拆解

### 拆解原则

1. **原子性**：每个任务有明确的输入/输出，无法再细分
2. **独立性**：任务间通过数据传递耦合，不依赖内部状态
3. **可并行**：标明哪些任务可同时执行，哪些必须串行
4. **可度量**：每个任务有成功标准（准确率、延迟等）

### 拆解步骤

1. 从 SRM 的 workflow_ref 出发，将每个步骤展开为原子任务
2. 识别任务间依赖关系，构建 DAG
3. 标注并行/串行/条件分支
4. 为每个原子任务定义 I/O Schema

### DAG输出格式

```yaml
task_dag:
  name: "DAG名称"
  description: "一句话描述"
  
  tasks:
    - id: T1
      name: "原子任务名"
      description: "做什么"
      input_schema:
        field1: { type: string, required: true }
        field2: { type: number, required: false }
      output_schema:
        result: { type: object }
      deps: []           # 无依赖，可立即执行
      parallel_group: A  # 同组可并行
      
    - id: T2
      name: "原子任务名"
      deps: [T1]         # 依赖T1完成后执行
      parallel_group: null
      
    - id: T3
      name: "原子任务名"
      deps: [T1]         # 与T2并行
      parallel_group: A

  # 条件分支定义
  branches:
    - condition: "T2.result.severity == 'high'"
      then: [T4]
      else: [T5]
```

## 阶段3：智能体映射

### 六类智能体分类

| 类别 | 职责 | 典型能力 | 实现倾向 |
|------|------|----------|----------|
| **感知类** | 获取外部数据 | 图像识别、语音转文字、IoT采集 | API调用 + 模型推理 |
| **分析类** | 计算、推理、预测 | 仿真、时序预测、知识推理 | Python脚本 + ML模型 |
| **决策类** | 给出建议或行动 | 阈值判断、路径规划、资源调配 | 规则引擎 + LLM推理 |
| **执行类** | 操控硬件/软件 | 设备控制、邮件发送、数据库写入 | API调用 + SDK |
| **交互类** | 用户/系统通信 | 对话、报表、网关 | LLM + 模板引擎 |
| **编排类** | 管理其他智能体 | 工作流监控、容错切换 | 状态机 + 重试逻辑 |

### 映射步骤

1. **逐任务匹配**：将每个原子任务映射到上述六类中的一类
2. **优先复用**：检查已有Agent/工具/API是否可复用
3. **能力定义**：为每个Agent定义能力卡
4. **接口标准化**：统一用 HTTP/gRPC 接口，定义请求/响应 Schema
5. **依赖分析**：标明Agent间的数据流和控制流

### Agent能力卡格式

```yaml
agent_card:
  id: AGT-001
  name: "Agent名称"
  category: 感知 | 分析 | 决策 | 执行 | 交互 | 编排
  
  capability: |
    一句话描述该Agent的核心能力
  
  input:
    format: json
    schema:
      field1: { type: string, desc: "说明" }
  
  output:
    format: json
    schema:
      result: { type: object, desc: "说明" }
  
  implementation:
    type: api_call | python_script | llm_chain | rule_engine | human_in_loop
    detail: "实现说明"
    dependencies: ["依赖的库/服务"]
  
  sla:
    latency_p95: "预估延迟"
    availability: "可用性目标"
    accuracy: "准确率目标"
  
  alternatives:
    - name: "备选Agent"
      tradeoff: "优劣对比"
```

## 智能体图谱可视化

输出图谱的邻接关系（可用于Neo4j存储或Mermaid可视化）：

```yaml
agent_graph:
  nodes:
    - id: AGT-001
      name: "数据采集Agent"
      category: 感知
  edges:
    - from: AGT-001
      to: AGT-002
      type: data_flow     # data_flow | control_flow
      payload: "采集的原始数据"
```

Mermaid格式（直接渲染）：

```
graph TD
    A1[数据采集Agent<br/>感知类] --> A2[频谱分析Agent<br/>分析类]
    A1 --> A3[时序预测Agent<br/>分析类]
    A2 --> A4[故障诊断Agent<br/>决策类]
    A3 --> A4
    A4 --> A5[通知Agent<br/>交互类]
    A4 --> A6[工单Agent<br/>执行类]
```

## 跨行业复用检测

构建图谱时，自动检测可跨行业复用的Agent：

| 通用Agent | 可复用行业 |
|-----------|-----------|
| 图像缺陷检测 | 制造业质检、隧道裂缝、医疗影像 |
| 时序异常检测 | 设备监控、气象预测、金融风控 |
| 路径规划 | 无人机巡检、物流调度、手术导航 |
| 报告生成 | 所有行业 |
| 通知推送 | 所有行业 |

## 交付物检查清单

- [ ] 完整的原子任务DAG（含依赖关系和并行组）
- [ ] 每个原子任务的I/O Schema
- [ ] Agent能力卡（全部Agent）
- [ ] Agent图谱邻接关系（含数据流和控制流）
- [ ] Mermaid可视化图
- [ ] 跨行业复用分析

若用户需要将图谱落地为可执行的工作流，引导使用 `srao-workflow-orchestrator` skill。
