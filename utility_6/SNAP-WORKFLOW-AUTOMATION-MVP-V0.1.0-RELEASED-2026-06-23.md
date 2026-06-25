
# SNAP-WORKFLOW-AUTOMATION-MVP-V0.1.0-RELEASED-2026-06-23

## Snapshot ID

`SNAP-WORKFLOW-AUTOMATION-MVP-V0.1.0-RELEASED-2026-06-23`

## Phase

Utility Bridge Phase / RADAR Services Bridge Phase

## Status

RELEASED / LOCKED

## Utility

Utility #6 — Workflow Automation MVP

## Version

v0.1.0

## Repository

`workflow_automation_mvp`

## Release Status

GitHub Release completed.

Tag:

`v0.1.0`

## Test Status

```text
41 passed
```

## Purpose

Workflow Automation MVP is the orchestration layer for the RADAR AI Utility Ecosystem.

Its role is to coordinate reusable local utilities through a workflow contract, task registry, CLI interface, Knowledge Search integration, and Telegram-facing command layer.

This utility transforms the previous standalone utilities into a connected automation pipeline.

## Core Position in RADAR Utility Ecosystem

```text
CLI / Telegram Command
    ↓
Workflow Contract
    ↓
Task Registry
    ↓
Local Workflow Runner
    ↓
Document Pipeline
    ↓
Published Documents
    ↓
Knowledge Search Index
    ↓
Knowledge Search Query
```

## Completed Milestones

### M1 — Bootstrap

* Created `workflow_automation_mvp`
* Added Python package structure
* Added `auto-run` CLI command
* Added sample workflow contract
* Added pytest foundation
* Initial CLI and tests passed

### M2 — Workflow Contract

* Added JSON workflow contract parser
* Added `WorkflowStep`
* Added `WorkflowOptions`
* Added `WorkflowSpec`
* Added validation for required workflow fields
* Added support for workflow options
* Added workflow contract tests

### M3 — Task Registry

* Added task registry
* Added supported task types:

  * `detect`
  * `pipeline`
  * `publish`
* Added unsupported task validation
* Added registry tests
* CLI showed task list from workflow steps

### M4 — Local Workflow Runner

* Added local step executor
* Added `StepExecutionResult`
* Added ordered step execution
* Added disabled step skipping
* Added step result output in CLI
* Fixed module boundary issues:

  * `workflow.py` = contract only
  * `executor.py` = step execution
  * `runner.py` = orchestration
  * `cli.py` = terminal interface

### M5 — Document Pipeline Executor

* Added `pipeline_executor.py`
* Integrated Utility #5 `document_pipeline_mvp`
* Workflow `pipeline` step calls `doc-pipe --batch`
* Generated workflow JSON output
* Generated workflow Markdown output
* Generated published documents
* CLI workflow successfully executed Document Pipeline

### M6 — CLI Layer Expansion

* Added CLI target override
* Added `--export-json`
* Added `--export-markdown`
* Added `--publish`
* Added `--dry-run`
* Added workflow option override layer
* CLI can now execute workflow without editing JSON contract

### M7 — Knowledge Search Integration

* Added `knowledge_executor.py`
* Integrated Utility #1 `radar_knowledge_search`
* Added `index` task type
* Added Knowledge Search index step
* Added post-workflow search query
* Added `--search`
* Workflow can now:

  * publish processed documents
  * index published documents
  * run search query
* End-to-end flow passed:

  * `auto-run`
  * `doc-pipe`
  * `published_documents`
  * `radar-search index`
  * `radar-search search`

### M8A — Telegram Contract

* Added `telegram.py`
* Added `TelegramWorkflowRequest`
* Added Telegram-style `/run` command parser
* Added workflow response formatter
* Added `handle_telegram_command()`
* Dry-run command can be triggered through Telegram-facing contract

### M8B — Mock Telegram Command

* Added mock Telegram command router
* Added `/workflow help`
* Added `/workflow status`
* Added `/run` command routing
* Added `handle_mock_telegram_command()`
* Prepared clean bridge for future Telegram bot integration

### M8C — Telegram Response Integration

* Added compact Telegram-ready workflow response
* Added status icons for chat output
* Added compact mode
* Added search result summary formatting
* Added compact response path:

  * `handle_mock_telegram_command(..., compact=True)`

### M9 — Packaging & README Finalization

* Standardized `pyproject.toml`
* Finalized `README.md`
* Documented installation
* Documented local utility dependencies
* Documented CLI usage
* Documented mock Telegram usage
* Documented workflow contract example
* Documented architecture
* Prepared release candidate

### M10 — v0.1.0 Release

* Final verification completed
* Git tag created:

  * `v0.1.0`
* GitHub Release published
* Release notes finalized
* Utility #6 locked as released

## Supported CLI

```bash
auto-run workflows/sample.workflow.json
auto-run workflows/sample.workflow.json --dry-run
auto-run workflows/sample.workflow.json --publish --search "Workflow"
auto-run workflows/sample.workflow.json --target data/custom_docs --export-json --export-markdown --publish
```

## Mock Telegram Commands

```text
/workflow help
/workflow status
/run workflows/sample.workflow.json --dry-run
/run workflows/sample.workflow.json --publish --search Workflow
/run workflows/sample.workflow.json --target data/custom_docs --export-json --export-markdown --publish
```

## Compact Telegram Response Example

```python
from workflow_automation.telegram import handle_mock_telegram_command

response = handle_mock_telegram_command(
    "/run workflows/sample.workflow.json --publish --search Workflow",
    compact=True,
)

print(response)
```

## Local Utility Integrations

### Integrated Utilities

* `document_pipeline_mvp`
* `radar_knowledge_search`

### Required Local Installs

```bash
pip install -e ../document_pipeline_mvp
pip install -e ../radar_knowledge_search
```

### CLI Dependencies

```bash
which auto-run
which doc-pipe
which radar-search
```

## Main Files

```text
workflow_automation/
├── cli.py
├── executor.py
├── knowledge_executor.py
├── pipeline_executor.py
├── registry.py
├── runner.py
├── telegram.py
└── workflow.py
```

## Main Tests

```text
tests/
├── test_cli.py
├── test_executor.py
├── test_knowledge_executor.py
├── test_pipeline_executor.py
├── test_registry.py
├── test_telegram.py
└── test_workflow.py
```

## Supported Task Types

| Task Type  | Purpose                                         |
| ---------- | ----------------------------------------------- |
| `detect`   | Validate and acknowledge workflow target        |
| `pipeline` | Run Document Pipeline                           |
| `publish`  | Publish processed documents                     |
| `index`    | Index published documents with Knowledge Search |

## Locked Architecture Principles

### LOCKED

`workflow.py` is contract-only.

It must contain:

* `WorkflowStep`
* `WorkflowOptions`
* `WorkflowSpec`
* workflow JSON loading
* workflow validation

It must not import:

* `executor.py`
* `runner.py`
* `cli.py`

### LOCKED

`executor.py` executes steps.

It owns:

* `StepExecutionResult`
* step execution logic
* pipeline step dispatch
* index step dispatch

### LOCKED

`runner.py` orchestrates workflow execution.

It owns:

* loading workflow spec
* applying CLI overrides
* dry-run handling
* executing enabled steps
* optional Knowledge Search query
* final workflow status

### LOCKED

`cli.py` is terminal-facing only.

It owns:

* argparse
* CLI flags
* terminal output formatting

### LOCKED

`telegram.py` is Telegram-facing adapter only.

It owns:

* Telegram command parsing
* mock Telegram command routing
* compact chat response formatting
* bridge to workflow runner

## Important Lessons

### Circular Import Boundary

The following import direction is valid:

```text
cli.py
    ↓
runner.py
    ↓
executor.py
    ↓
workflow.py
```

The following direction is forbidden:

```text
workflow.py → executor.py
workflow.py → runner.py
workflow.py → cli.py
```

### Test Strategy

External CLI integrations are validated through contract and smoke tests, while direct subprocess-heavy behavior is kept lightweight in unit tests.

### Utility Ecosystem Direction

Utility #6 is the first orchestration utility that connects previous tools into an operational pipeline.

It connects:

```text
Utility #5 — Document Pipeline
Utility #1 — Knowledge Search
Telegram-facing command layer
```

## Final State

```text
UTILITY #6 — Workflow Automation MVP

M1 Bootstrap                         ✅
M2 Workflow Contract                 ✅
M3 Task Registry                     ✅
M4 Local Workflow Runner             ✅
M5 Document Pipeline Executor        ✅
M6 CLI Layer Expansion               ✅
M7 Knowledge Search Integration      ✅
M8A Telegram Contract                ✅
M8B Mock Telegram Command            ✅
M8C Telegram Response Integration    ✅
M9 Packaging & README Finalization   ✅
M10 v0.1.0 Release                   ✅

Status: RELEASED / LOCKED
Version: v0.1.0
Test Status: 41 passed
GitHub Release: completed
```

## Next Utility Direction

Recommended next utility:

`Utility #7 — File Watcher Automation MVP`

Purpose:

```text
watch folder
    ↓
detect new file
    ↓
trigger workflow_automation_mvp
    ↓
document pipeline
    ↓
publish
    ↓
index
    ↓
search/report
```

This moves the ecosystem from manual workflow execution to event-driven automation.

## Continuation Command

Continue with:

```text
Tri Kỷ, chúng ta bắt đầu Utility #7 — File Watcher Automation MVP, M1 Bootstrap.
```
