
SNAP-DOCUMENT-PIPELINE-MVP-V0.1.0-RELEASED-2026-06-15

Phase: RADAR Services Bridge Phase

Status: RELEASED

Utility ID: #5

Name: Document Pipeline MVP

Version: v0.1.0

Mission

Xây dựng một pipeline tài liệu thống nhất có khả năng:

* Phát hiện loại tài liệu
* Xử lý văn bản
* OCR hình ảnh
* Xuất JSON
* Xuất Markdown
* Publish sang Knowledge Search

Mục tiêu là tạo cầu nối giữa:

Document Sources
↓
Document Pipeline
↓
Knowledge Search

========================================

COMPLETED

M1 — Bootstrap

* Khởi tạo project document_pipeline_mvp
* Thiết lập pyproject.toml
* Thiết lập CLI command: doc-pipe
* Thiết lập pytest foundation

M2 — File Type Detector

* Hỗ trợ phát hiện:

  * txt
  * md
  * json
  * png
  * jpg
  * jpeg

* Trả về routing information cho pipeline

M3 — Text Pipeline

* Xử lý text documents

* Thu thập metadata:

  * characters
  * words
  * line count

* Sinh preview

* Sinh summary cơ bản

M4 — OCR Pipeline

* OCR image documents
* Trích xuất text từ ảnh
* Tạo metadata
* Tạo summary
* Tạo preview

M5 — JSON Export Layer

* Export kết quả pipeline sang JSON
* Hỗ trợ text documents
* Hỗ trợ OCR documents
* Chuẩn hóa report structure

M6 — Markdown Export Layer

* Export kết quả pipeline sang Markdown
* Tạo báo cáo đọc được bởi con người
* Bao gồm:

  * source
  * metadata
  * summary
  * preview
  * extracted content

M7 — Publish Layer

* Publish processed content
  vào published_documents/

* Chuyển đổi pipeline output
  thành text documents có thể index

* Tích hợp với RADAR Knowledge Search

M8 — Batch Pipeline

* Batch process directory

* Hỗ trợ:

  * Text
  * Markdown
  * Images

* Hỗ trợ:

  * batch json export
  * batch markdown export
  * batch publish

M9 — Packaging & README

* Hoàn thiện README
* Hoàn thiện installation guide
* Hoàn thiện Knowledge Search integration guide

M10 — Release

* Khóa release v0.1.0
* Git history chuẩn hóa
* Release candidate pass toàn bộ test

========================================

FINAL TEST STATUS

Pytest: 43 passed

CLI:

* doc-pipe
* --json
* --md
* --publish
* --batch

Knowledge Search:

* radar-search index
* radar-search search

đã xác nhận hoạt động cùng Publish Layer.

========================================

ARCHITECTURE

Document
↓
Detector
↓
Router
↓
Processor
(Text/OCR)
↓
Exporter
(JSON/Markdown)
↓
Publisher
↓
Knowledge Search

========================================

LOCKED DECISIONS

* Utility #5 giữ phạm vi MVP
* Không thêm PDF parsing vào v0.1.0
* Không thêm LLM summarization vào v0.1.0
* Publish output dùng plain text
* Knowledge Search là hệ thống downstream chính thức

========================================

REUSABLE ASSETS

* detector.py
* text_processor.py
* ocr_processor.py
* exporter.py
* publisher.py
* batch_processor.py
* cli.py

========================================

ROLE IN ECOSYSTEM

Trụ:
Ingestion
↓
Processing
↓
Knowledge

Document Pipeline là cầu nối đầu tiên
giữa OCR/Text Processing
và Knowledge Search.

========================================

NEXT PHASE

Utility #6

Automation Layer Foundation

Mục tiêu:

Tự động hóa việc:

* Scan
* Process
* Export
* Publish
* Index

không cần thao tác thủ công.

Status: READY
