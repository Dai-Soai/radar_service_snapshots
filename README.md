# RADAR Service Snapshots

Release snapshots and milestone records for the RADAR_SERVICE project.

This repository stores immutable snapshots of completed utilities, release milestones, and important architectural decisions.

Source code is maintained in individual utility repositories. This repository only contains release records and project snapshots.

---

# Purpose

The snapshot repository provides:

- Release history
- Milestone records
- Architecture evolution
- Locked design decisions
- Utility release documentation
- Project continuity across development phases

---

# Repository Structure

```text
radar_service_snapshots/
├── utility_1/
├── utility_2/
├── utility_3/
├── utility_4/
├── utility_5/
├── utility_6/
├── utility_7/
├── utility_8/

```

Each utility directory stores release snapshots in both Markdown and YAML formats.

---

# Snapshot Naming Convention

```text
SNAP-<UTILITY>-<VERSION>-<STATE>.md

SNAP-<UTILITY>-<VERSION>-<STATE>.yaml
```

Example:

```text
SNAP-WORKFLOW-RUNNER-MVP-V0.1.0-RELEASED.md
SNAP-WORKFLOW-RUNNER-MVP-V0.1.0-RELEASED.yaml
```

---

# Snapshot Contents

Each snapshot records:

- Snapshot ID
- Development phase
- Utility status
- Version
- Completed milestones
- Locked architecture
- Locked decisions
- Future ideas (UNLOCKED)
- Related files
- Final release state

---

# Development Philosophy

Source Code

↓

Milestones

↓

Snapshots

↓

Release History

The snapshot repository preserves architectural decisions independently from the implementation repositories.

---

# Current Utilities

| Utility | Name | Status |
|---------|------|--------|
| Utility #1 | Knowledge Search | Released |
| Utility #2 | Telegram Knowledge Bot | Stable |
| Utility #3 | Document Assistant | Released |
| Utility #4 | OCR Document | Released |
| Utility #5 | Document Pipeline | Released |
| Utility #6 | Workflow Automation | Released |
| Utility #7 | File Watcher Automation | Released |
| Utility #8 | Workflow Runner | Released |

---

# Phase

Current Phase:

```text
RADAR Services Bridge Phase
```

Goal:

Build reusable AI utilities that can be combined into a modular automation ecosystem.

---

# Design Principles

- Utilities are independent.
- Snapshots are immutable after release.
- Architectural decisions are explicitly locked.
- Source code and release history are stored separately.
- YAML is preferred over hardcoded workflows whenever practical.

---

# License

Internal RADAR project documentation.
