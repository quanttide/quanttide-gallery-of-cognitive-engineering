# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Added

- AGENTS.md: document repository purpose as factual source preservation
- `situation/` directory: weekly situation definitions (W19-W23)
  - 9 situation types with `agenda/ecology/frame/dynamics` dimensions
  - `registry.yaml` for cross-week name/label mapping
- `intention/` directory: weekly intention files (W19-W23)
  - Per-situation YAML with structured fields (agent/level/priority/trigger/risk)
  - CE framework template: `id/title/description/motivation` + structured metadata

### Changed

- `situation/`: standardized fields to `id/uuid/name/label/content{agenda,ecology,frame,dynamics}`
- `situation/` labels: shortened to concise names (e.g. "商业模式探索" → "商务拓展")
- `situation/` naming: `product` → `agent`, `meta` → `infra`, `innov` → `devops`/merged into `think`
- `intention/`: restructured from flat key-value to `name/label/description` object format
- `intention/` fields: `timing` → `trigger`, `uncertainty` → `risk`
- `intention/` trigger values: `until/upon` → `persistent/conditional`
- `intention/`: added UUID, reordered fields to `id/title/description/motivation` first
- `intention/`: removed `situation` and `intentions` wrapper (implied by filename)
- `notion/` → `thought/`: directory renamed

### Removed

- `situation/2026-W23/org.json`: replaced by YAML format

## [0.1.0] - 2026-06-05

### Added

- Initial repository setup with README
- Notion case archive (`notion/`)
