# BUILD_RULES.md

# Live Translator
## AI Build Rules

Version: 1.0

Status: Approved

Last Updated: 2026-07-21

---

# Purpose

This document defines the mandatory engineering rules that every AI coding assistant shall follow when working on the Live Translator project.

These rules apply to every implementation milestone.

Failure to comply with these rules shall be considered an incomplete implementation.

---

# Project Status

Current Version

0.1.0

Current Phase

Pre-Implementation

Architecture

Frozen

Implementation

Not Started

The architecture and documentation are considered the single source of truth.

---

# Required Reading

Before generating or modifying code, the AI shall read and understand:

docs/00_PROJECT_INDEX.md

docs/03_SRS.md

docs/04_ARCHITECTURE.md

docs/05_ROADMAP.md

docs/06_AI_CONTEXT.md

docs/07_PROJECT_STATE.json

docs/08_CHANGELOG.md

docs/09_CODING_STANDARDS.md

docs/10_TESTING_STANDARDS.md

docs/11_SOURCE_TREE.md

docs/implementation/

No implementation shall begin without understanding these documents.

---

# General Rules

The AI shall:

Follow the approved architecture.

Follow the approved source tree.

Implement only the requested milestone.

Generate production-quality code.

Keep modules cohesive.

Keep interfaces stable.

Preserve backward compatibility where required.

Avoid unnecessary complexity.

---

# Forbidden

The AI shall never:

Generate placeholder code.

Generate TODO comments.

Generate incomplete implementations.

Invent undocumented requirements.

Modify frozen architecture without approval.

Rename public modules without approval.

Break dependency hierarchy.

Create circular imports.

Remove existing functionality unless requested.

---

# Source Code Rules

Every source file shall:

Compile successfully.

Contain a complete implementation.

Use consistent naming.

Follow Python best practices.

Include appropriate documentation.

Use meaningful logging.

Handle expected errors gracefully.

---

# Python Compatibility

Maintain compatibility with:

Python 2

Python 3

where required by the project.

Compatibility decisions shall follow the architecture documentation.

---

# Architecture Rules

Respect the dependency hierarchy.

Allowed:

Plugin

↓

Bootstrap

↓

Core

↓

Managers

↓

Services

↓

Providers

↓

Engines

↓

UI

↓

Utilities

Forbidden:

Utilities → UI

Providers → UI

Managers → UI

Circular imports

Cross-layer shortcuts

---

# Documentation Rules

When a milestone changes documentation, the AI shall update:

07_PROJECT_STATE.json

08_CHANGELOG.md

Any affected implementation document

Documentation shall remain synchronized with implementation.

---

# Testing Rules

Every completed milestone shall:

Pass static analysis.

Pass unit tests.

Pass integration tests where applicable.

Pass virtual Enigma2 validation where available.

Fix discovered issues before completion.

---

# Git Rules

Implement one milestone at a time.

Keep commits focused.

Do not mix milestones.

Do not modify unrelated files.

---

# Performance Rules

Avoid unnecessary allocations.

Avoid blocking operations.

Optimize startup time.

Optimize memory usage.

Optimize network usage.

---

# Security Rules

Protect credentials.

Validate external input.

Handle provider failures safely.

Do not expose sensitive information in logs.

---

# Deliverables

A completed milestone shall include:

Production source code

Unit tests

Updated documentation (if applicable)

Updated project state

Updated changelog

Successful validation

Git-ready changes

---

# Definition of Done

A milestone is complete only when:

All required files are implemented.

Code is internally consistent.

Tests pass.

Documentation is synchronized.

No placeholder code exists.

No TODO comments exist.

No known blocking issues remain.

The milestone is ready for review and commit.

---

# End of Document