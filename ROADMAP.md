# Gallery Roadmap

## 现状

- `situation/`：W19-W23 情境 YAML，结构稳定（agenda/ecology/frame/dynamics）
- `intention/`：W19-W23 意向 YAML，结构稳定（agent/level/priority/trigger/risk）
- `schema/`：W19-W23 文件已创建，内容为空（待填充）
- `registry.yaml`：16 个情境名称映射
- `CHANGELOG.md`、`AGENTS.md`：已就位

## Phase 1: Schema 填充

- [ ] 将 `reports/{week}/schemas.yaml` 的 LLM 推理结果人工审核后写入 `schema/{week}.yaml`
- [ ] 每条 schema 需符合 `schema/README.md` 定义的格式
- [ ] 审核标准：causals 是否可证伪、biases 是否源自日志原文、boundaries 是否明确

## Phase 2: 数据结构固化

- [ ] `situation/` 和 `intention/` 的字段定义进入 `schema/README.md` 作为引用规范
- [ ] 移除 `situation/` 和 `intention/` 中不再使用的字段（如 `situation.id` 跨周不唯一）
- [ ] 统一 UUID 生成策略（当前为随机 UUID，跨周不可追踪）

## Phase 3: 跨周关联

- [ ] `situation/registry.yaml` 增加 `since` 和 `until` 字段标注情境活跃周范围
- [ ] `intention/` 引入跨周关联 ID：同一意图在不同周使用相同 tracking_id
- [ ] `schema/` 的 causals 可以引用 `intention/` 中的意向作为证据

## Phase 4: 工具链

- [ ] 本仓库的 schema 数据可作为 Project 11 的测试基准
- [ ] 每次 schema 更新后自动触发 `project-11 report <week>` 验证
- [ ] 工具链输出（`reports/`）与本仓库数据（`situation/` `intention/` `schema/`）分离

## Phase 5: 扩展

- [ ] 将已有 week 的 schema 补全（W19-W22）
- [ ] 定义新的情境类型（如需）
- [ ] 可视化：schema 的 entities/causals 可导出为 Graphviz DOT 格式
