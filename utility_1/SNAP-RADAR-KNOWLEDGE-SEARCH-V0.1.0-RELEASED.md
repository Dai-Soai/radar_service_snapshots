SNAPSHOT ID
SNAP-RADAR-KNOWLEDGE-SEARCH-V0.1.0-RELEASED

Phase
RADAR Services Bridge Phase
Utility #1 Completion

Status
LOCKED
RELEASED

PROJECT
RADAR Knowledge Search

Repository
Dai-Soai/radar-knowledge-search

Version
v0.1.0

Release Status
GitHub Release Created
Tag: v0.1.0

CORE PURPOSE
RADAR Knowledge Search là utility độc lập dùng để index và search tài liệu dạng Markdown, TXT, YAML, JSON bằng Python + SQLite + FTS5.

Đây là service nền đầu tiên của RADAR_SERVICES, phục vụ:
- Snapshot search
- Work notes search
- Technical logs search
- Future Telegram Knowledge Bot
- Future Document Assistant
- Future RADAR internal knowledge retrieval

COMPLETED

1. Project Bootstrap
- Tạo repo radar_knowledge_search
- Tạo package knowledge_search/
- Tạo tests/
- Tạo README.md
- Tạo pyproject.toml
- Tạo .gitignore

2. Storage Layer
- SQLite database
- documents table
- RADAR_SEARCH_DB env override
- save_document()
- init_db()

3. Indexer Layer
- Index folder recursively
- Support .md, .txt, .yaml, .yml, .json
- Ignore .venv, .git, __pycache__, .pytest_cache, .egg-info
- Save indexed documents into SQLite

4. Search Layer
- Migrated from LIKE search to SQLite FTS5
- documents_fts virtual table
- MATCH-based full-text search
- Search returns path + content preview

5. CLI Layer
- radar-search index <path>
- radar-search search <keyword>
- Installed through pyproject script entrypoint

6. Tests
- test_storage.py
- test_indexer.py
- test_search.py
- pytest result: 3 passed

7. Packaging
- pyproject.toml configured
- setuptools build backend
- editable install works
- dev dependency pytest added

8. Git / GitHub
- Git initialized
- Repo pushed to GitHub
- Branch main tracks origin/main
- Working tree clean

9. Release
- Tag v0.1.0 created
- Tag pushed to GitHub
- GitHub Release created:
  RADAR Knowledge Search v0.1.0

LOCKED DECISIONS

1. RADAR Knowledge Search is Utility #1 of RADAR Services.

2. v0.1.0 is considered MVP released.

3. GitHub repo, code, tests, and release are the source of truth.

4. Chat history is no longer treated as source of truth for implementation state.

5. Future upgrades must branch from v0.1.0 baseline.

CURRENT CAPABILITY

The tool can:

- index documents
- store them in SQLite
- search using FTS5
- run from CLI
- pass automated tests
- be cloned from GitHub
- be installed locally
- be demonstrated as portfolio utility

COMMANDS VERIFIED

pip install -e ".[dev]"

pytest

radar-search index .

radar-search search "RADAR"

git tag v0.1.0

git push origin v0.1.0

GitHub Release:
RADAR Knowledge Search v0.1.0

NEXT POSSIBLE PHASES

M9 — YAML Config Layer
- Move supported extensions to YAML
- Move ignored dirs to YAML
- Move DB path / preview length / search mode to YAML

M10 — Better Search Output
- line number
- highlighted keyword
- shorter snippet
- result ranking

M11 — REST API Layer
- FastAPI wrapper
- /index
- /search

M12 — Telegram Bridge Integration
- Telegram bot calls radar-search service

M13 — Document Assistant Integration
- PDF/OCR/chunk/search pipeline

DO NOT DO NEXT

Do not jump to:
- Multi-agent
- New RADAR Graph layer
- New Cognition layer
- Dashboard
- Big architecture rewrite

unless it directly serves utility reuse.

SUMMARY

RADAR Knowledge Search v0.1.0 is the first completed RADAR Services utility.

It proves the new direction:

RADAR Core
→ RADAR Services
→ Utility
→ Portfolio
→ Freelance
→ Revenue

Status:
RELEASED / LOCKED / READY FOR NEXT UTILITY PHASE
