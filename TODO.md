# TODO

## 层次一：文档化约定

- [ ] 命名规则：`identifier` 小写、单数、与文件名一致
- [ ] 引用规则：situation ↔ intention 通过 `name` 字段关联，不受 label 变更影响
- [ ] 周目录规则：统一 `2026-W{NN}` 格式
- [ ] 单独抽出 **CONVENTIONS.md** 作为快速参考

## 层次二：可选辅助脚本

- [ ] 命名一致性检查：每周的 `name` 是否都在 `registry.yaml` 中
- [ ] 跨周追踪检查：某 `name` 在不同周都有 situation 和 intention 对应
- [ ] 孤岛检测：标记只有 situation 没有 intention（或反之）的周

