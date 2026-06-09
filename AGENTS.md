# AGENTS.md

本仓库是**事实源**——从原始日志中提炼的情境、意图与图式数据，是可追溯的认知工程实验证据。

## 数据层次

- `situation/`：按周组织的情境定义，记录 `agenda/ecology/frame/dynamics`
- `intention/`：按情境组织的意向定义，记录 `agent/level/priority/trigger/risk`
- `schema/`：细粒度心智模型，记录 `entities/causals/boundaries/dynamics/mappings/biases`
- `registry.yaml`：情境名称与标签映射表

## 数据流

```
原始日志（lab/data/）
    ↓ 提炼
gallery（本仓库）← 事实源
    ↓ 引用
lab（examples/default/）← 工具消费方
```

- gallery 是唯一的**事实源**，lab 是工具消费方
- lab 中的 `project-11` 直接读取本仓库的 YAML 文件
- lab 生成的推理产物（`reports/`、`schemas.yaml`）不写回 gallery
- gallery 的数据只能通过人工审核后修改，不通过工具自动写入

## 心智模型抽取规范

### 数据来源对比

| 来源 | 信噪比 | 最佳贡献字段 | 局限 |
|------|--------|-------------|------|
| **`thought/`**（原始文本） | 低 | `causals`（完整推理链）、`biases`（直觉错误） | 表述不精确，需筛选 |
| **`situation/`**（情境） | 高 | `entities`（核心概念）、`frame`（认知框架）、`dynamics`（时间演化） | 丢失原始语境，偏差不显式 |
| **`intention/`**（意图） | 高 | `motivation`（因果动因）、`trigger`（动态参数）、`priority/risk`（属性） | 仅覆盖有意识的目标 |

### 字段来源映射

| 心智模型字段 | 主要来源 | 辅助来源 |
|-------------|---------|---------|
| `entities` | 情境 `frame` | — |
| `causals` | 想法日志（推理链条） | 意图 `motivation` |
| `boundaries` | 情境 + 想法日志 | — |
| `properties` | 情境 `frame` | 意图 `priority`, `risk` |
| `dynamics` | 情境 `dynamics` | 意图 `trigger` |
| `mappings` | **意图**（结构化 intent-action） | 情境 `agenda` |
| `biases` | 想法日志（事后反思） | — |

### 抽取流程

1. **骨架**：以情境的 `frame` 字段为骨架，提取核心实体和认知框架
2. **因果**：从想法日志中提取推理链条，用意图的 `motivation` 补充动因
3. **映射**：以意图 YAML 为主体，提取结构化的 intent-action 对
4. **偏差**：从想法日志中的直觉判断和事后反思提取常见误解

## 原则

- 本仓库不推理关系，不生成分析——只保留可追溯的事实源
- 数据格式以 `schema/README.md` 为准
- 所有数据文件必须经过审核状态标记（待审核/已通过/已拒绝）
