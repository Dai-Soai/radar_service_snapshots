# RADAR Service Snapshots

Release snapshots and milestone records for the RADAR_SERVICE project.

This repository stores immutable snapshots of completed utilities, release milestones, architectural contracts, and locked design decisions.

Source code is maintained in individual utility repositories. This repository only stores release records, architecture snapshots, and project history.

---

# Purpose

The snapshot repository provides:

- Release history
- Milestone records
- Architecture evolution
- Contract boundaries
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
├── utility_9/
├── utility_10/
├── utility_11/
├── utility_12/
├── utility_13/
```

Each utility directory stores release snapshots in both Markdown and YAML formats.

---

# Snapshot Naming Convention

```text
SNAP-<UTILITY>-<VERSION>-<STATE>.md

SNAP-<UTILITY>-<VERSION>-<STATE>.yaml
```

Example

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
- Milestone completion
- Contract Boundary
- Locked architecture
- Locked decisions
- Deliverables
- Future ideas (UNLOCKED)
- Related files
- Release status

---

# Development Philosophy

```text
Source Code
      │
      ▼
Milestones
      │
      ▼
Snapshots
      │
      ▼
Release History
      │
      ▼
Architecture Knowledge
```

Snapshots preserve architectural evolution independently from implementation repositories.

---

# Current Utilities

| Utility | Name | Status |
|----------|------|--------|
| Utility #1 | Knowledge Search | Released |
| Utility #2 | Telegram Knowledge Bot | Stable |
| Utility #3 | Document Summary Engine | Released |
| Utility #4 | OCR Document | Released |
| Utility #5 | Document Pipeline | Released |
| Utility #6 | Workflow Automation | Released |
| Utility #7 | File Watcher Automation | Released |
| Utility #8 | Workflow Runner | Released |
| Utility #9 | Telegram Notifier | Released |
| Utility #10 | Pipeline Orchestrator | Released |
| Utility #11 | Pipeline Template Registry | Released |
| Utility #12 | Pipeline Variable Resolver | Released |
| Utility #13 | Pipeline Validator | Released |

---

# Pipeline Architecture (Current)

```text
Pipeline Template Registry
            │
            ▼
Pipeline Variable Resolver
            │
            ▼
Pipeline Validator
            │
            ▼
Pipeline Orchestrator
            │
            ▼
Workflow Runner
            │
            ▼
Telegram Notifier
```

Each utility owns a clearly defined contract boundary.

---

# Current Phase

```text
RADAR Services Bridge Phase
```

Goal

Build reusable AI utilities that can be composed into a modular automation ecosystem with clear contracts, independent releases, and reusable components.

---

# Design Principles

- Utilities are independent.
- Snapshots are immutable after release.
- Every utility owns a Contract Boundary.
- Architectural decisions are explicitly LOCKED.
- Source code and release history are stored separately.
- YAML is preferred over hardcoded workflows whenever practical.
- Utilities communicate through documented contracts instead of direct package coupling.

---

# Snapshot Workflow

```text
Develop Utility
      │
      ▼
Complete Milestones
      │
      ▼
Run Tests
      │
      ▼
Release v0.1.0
      │
      ▼
Create Snapshot (.md + .yaml)
      │
      ▼
Store in radar_service_snapshots
```

---

# License

Internal RADAR project documentation.
