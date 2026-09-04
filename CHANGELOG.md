# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [0.2.0] - 2026-09-04

### Changed

- 仓库重构：移除旧的按周组织数据（meta/report/schema 目录与 AGENTS/ROADMAP/TODO），改为按领域组织的认知档案
- 首个领域档案 quanttide-docs（index/schema/situation 三文件），自 profile 提炼迁入

### Removed

- 旧格式数据（meta/domain.yaml、meta/world.yaml、report/、schema/consult.*）

## [0.1.0] - 2026-06-09

### Added

- README: project description
- AGENTS.md: document repository purpose
- `notion/` → `thought/`: weekly thinking records (W19-W23)
- `situation/` directory: weekly situation definitions (W19-W23)
- `intention/` directory: weekly intention files (W19-W23)
- `.quanttide/devops/release-journal.jsonl`: release journal
