# 00_PROJECT_INDEX.md

# Live Translator
## Project Documentation Index

Version: 1.0

Status: Active

Author: Mohamed

Last Updated: 21 July 2026

---

# Welcome

Welcome to the **Live Translator** project.

This repository follows a **Documentation First** development methodology.

No implementation should begin before the planning documentation has been reviewed.

This index is the starting point for all developers, AI coding assistants, reviewers, and contributors.

---

# Project Overview

Project Name:

Live Translator

Platform:

Enigma2 (E2)

Primary Language:

Python

Supported Versions:

- Python 2
- Python 3

Package Format:

Single IPK Package

Target Devices:

Enigma2 Set Top Boxes

License:

Closed Source

Current Version:

0.1.0

Current Status:

Planning Complete

---

# Documentation Reading Order

Every developer or AI shall read the following documents in order before making changes.

| Order | Document | Purpose |
|--------|----------|---------|
| 00 | 00_PROJECT_INDEX.md | Repository entry point |
| 01 | 01_PROJECT.md | Project definition |
| 02 | 02_MASTER_PROMPT.md | AI development instructions |
| 03 | 03_SRS.md | Software Requirements Specification |
| 04 | 04_ARCHITECTURE.md | Software Architecture |
| 05 | 05_ROADMAP.md | Development roadmap |
| 06 | 06_AI_CONTEXT.md | Persistent AI context |
| 07 | 07_PROJECT_STATE.json | Machine-readable project state |
| 08 | 08_CHANGELOG.md | Project history |
| 09 | 09_CODING_STANDARDS.md | Coding rules |
| 10 | 10_TESTING_STANDARDS.md | Testing rules |

---

# Current Project Phase

Phase:

Planning

Milestone:

Planning Baseline Complete

Implementation Status:

Not Started

Next Phase:

Phase 1 – Core Framework Implementation

---

# Core Functional Engines

The plugin implements the following engines in the approved order:

1. DVB Subtitle Translation

2. EPG Subtitle Search

3. EPG Translation

4. OCR Translation

5. Live Speech Translation

6. Media Identification

7. AI Voice Translation

Each engine shall operate independently and be individually configurable.

---

# Repository Structure

```text
LiveTranslator/

.ai/
docs/
src/
tests/
resources/
scripts/
package/
build/
releases/
examples/
tools/
templates/
```

---

# Development Workflow

Every implementation milestone shall follow this workflow:

1. Read project documentation.

2. Review the current roadmap.

3. Review the project state.

4. Implement only the approved milestone.

5. Perform automated testing.

6. Perform virtual receiver testing.

7. Update documentation.

8. Update changelog.

9. Update project state.

10. Commit completed work.

11. Push to GitHub.

No milestone shall be considered complete until all steps have been completed.

---

# Engineering Principles

The project follows these engineering principles:

- Documentation First
- Architecture Before Code
- Modular Design
- Professional Quality
- Automatic Testing
- Virtual Validation Before Hardware Testing
- Incremental Development
- Version Controlled Releases
- Single IPK Installation
- Automatic Dependency Management
- Cross-Distribution Compatibility
- Python 2 & Python 3 Support

---

# AI Rules

Every AI contributing to this project shall:

- Read this document first.
- Follow the approved architecture.
- Implement only approved functionality.
- Avoid introducing undocumented requirements.
- Update documentation after implementation.
- Run applicable tests before completion.
- Never generate placeholder code or TODO comments.

---

# Project Status Summary

| Component | Status |
|-----------|--------|
| Repository | ✅ Complete |
| Planning Documents | ✅ Complete |
| Requirements | ✅ Approved |
| Architecture | ✅ Approved |
| Roadmap | ✅ Approved |
| Coding Standards | ✅ Approved |
| Testing Standards | ✅ Approved |
| Implementation | ⏳ Not Started |
| Virtual Testing | ⏳ Pending |
| Hardware Testing | ⏳ Pending |
| Production Release | ⏳ Pending |

---

# Future Documentation

The following documents will be created during implementation:

```text
docs/guides/

11_PROVIDER_GUIDE.md
12_DEVICE_COMPATIBILITY.md
13_API_CONFIGURATION.md
14_DEVELOPER_GUIDE.md
15_RELEASE_PROCESS.md
```

These documents will be based on the implemented software and validated through testing.

---

# Definition of Ready

The project is ready for implementation when:

- Planning documents are complete.
- Architecture is approved.
- Roadmap is approved.
- Documentation baseline is committed.
- Project state is synchronized.
- Planning baseline tag is created in Git.

---

# End of Document