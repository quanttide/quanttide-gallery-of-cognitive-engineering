# ROADMAP

数据模型之间的关系是软性的（字段命名约定），而非硬性的（校验强制）。

## 原则

- ❌ 不引入 JSON Schema 或 YAML 校验（演化阶段 schema 追不上变化速度）
- ❌ 不强制必填字段（某些字段为空是有效状态）
- ❌ 不做自动化跨周一致性检查（演化意味着同一 name 在不同周可有不同属性集）

## 层次一：文档化约定

把现存约定写清楚，不改变代码和数据。

- [ ] 命名规则：`identifier` 小写、单数、与文件名一致
- [ ] 引用规则：situation ↔ intention 通过 `name` 字段关联，不受 label 变更影响
- [ ] 周目录规则：统一 `2026-W{NN}` 格式
- [ ] 单独抽出 **CONVENTIONS.md** 作为快速参考

## 层次二：可选辅助脚本

提供工具帮助自查，可选运行不阻止合并。

- [ ] 命名一致性检查：每周的 `name` 是否都在 `registry.yaml` 中
- [ ] 跨周追踪检查：某 `name` 在不同周都有 situation 和 intention 对应
- [ ] 孤岛检测：标记只有 situation 没有 intention（或反之）的周

## 层次三：数据浏览工具

让数据更容易被浏览和理解（对应 Project 11: Situation Engine）。

- [ ] 周报生成器：按周自动拼合 situation + intention + thought
- [ ] 演化追踪：给定 `name` 列出所有周的变化摘要
- [ ] 关系图导出：从 causal_rules 提取关系图
