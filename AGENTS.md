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

## 原则

- 本仓库不推理关系，不生成分析——只保留可追溯的事实源
- 数据格式以 `schema/README.md` 为准
- 所有数据文件必须经过审核状态标记（待审核/已通过/已拒绝）
