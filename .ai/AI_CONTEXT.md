# 06_AI_CONTEXT.md

# Live Translator
## AI Development Context

Version: 1.0

Status: Active

Last Updated: 21 July 2026

---

# 1. Purpose

This document provides persistent development context for AI coding assistants working on the Live Translator project.

It summarizes the project's objectives, engineering decisions, architectural principles, development workflow, coding expectations, and current implementation status.

Every AI assisting with the project shall read this document before performing analysis, planning, implementation, testing, refactoring, or documentation updates.

---

# 2. Project Summary

Project Name:

Live Translator

Platform:

Enigma2

Primary Language:

Python

Package Format:

Single IPK Package

Target Devices:

Enigma2 Set Top Boxes

Project Status:

Pre-Implementation

Current Milestone:

Planning Complete

---

# 3. Product Vision

Live Translator is a professional modular Enigma2 plugin that provides real-time language translation and media assistance services.

The plugin shall provide multiple independent engines that cooperate through a common framework while remaining independently configurable and maintainable.

The architecture emphasizes modularity, reliability, compatibility, extensibility, and automated validation.

---

# 4. Implemented Planning Documents

The following documents are authoritative and shall be consulted before implementation.

01_PROJECT.md

Project definition.

02_MASTER_PROMPT.md

AI development instructions.

03_SRS.md

Software requirements specification.

04_ARCHITECTURE.md

Software architecture.

05_ROADMAP.md

Development execution plan.

---

# 5. Product Owner Decisions

The following decisions have been approved.

License

Closed Source

Python Compatibility

Python 2 and Python 3

Supported Platforms

All supported Enigma2 distributions

Connectivity

Hybrid (Online and Offline)

AI Providers

Support both free and commercial providers

Installation

Single IPK package with automatic dependency installation and automatic default configuration

Virtual Testing

Mandatory before live hardware testing

---

# 6. Translation Engines

The project shall implement the following engines.

1. DVB Subtitle Translation

2. EPG Subtitle Search

3. EPG Translation

4. OCR Translation

5. Live Speech Translation

6. Media Identification

7. AI Voice Translation

Each engine shall be independently configurable.

Failure of one engine shall not affect the remaining engines.

---

# 7. Supported Provider Categories

The architecture supports multiple providers.

Translation Providers

OCR Providers

Speech Recognition Providers

Subtitle Providers

Media Identification Providers

AI Voice Providers

Providers shall be replaceable without modifying the plugin core.

---

# 8. Development Principles

The following principles are mandatory.

Documentation First

Architecture Before Code

Small Incremental Changes

No Placeholder Code

No TODO Comments

Production Quality Code

Professional Documentation

Virtual Testing Before Hardware Testing

No Breaking Existing Functionality

Single Source Repository

---

# 9. Coding Expectations

Generated code shall:

Follow the Architecture document.

Satisfy the SRS.

Remain modular.

Remain readable.

Include meaningful comments only where necessary.

Avoid duplicated functionality.

Avoid circular dependencies.

Fail gracefully.

Be compatible with supported Enigma2 platforms.

Be compatible with Python 2 and Python 3 whenever technically feasible.

---

# 10. Testing Expectations

Every implementation shall include:

Unit Tests

Integration Tests

Mock Provider Tests

Virtual Receiver Validation

Packaging Validation

Regression Testing

Hardware Validation before release

No feature shall be considered complete until successfully tested.

---

# 11. Documentation Rules

Whenever implementation changes occur, the following documents shall be reviewed and updated if affected:

03_SRS.md

04_ARCHITECTURE.md

05_ROADMAP.md

07_PROJECT_STATE.json

08_CHANGELOG.md

Documentation shall remain synchronized with implementation.

---

# 12. Repository Structure

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

The repository structure shall remain consistent throughout development.

---

# 13. Current Project Status

Planning Documents:

Complete

Architecture:

Approved

Implementation:

Not Started

Testing:

Not Started

Packaging:

Not Started

Release:

Not Started

---

# 14. AI Implementation Rules

Before writing code, an AI shall:

Read this document.

Read 03_SRS.md.

Read 04_ARCHITECTURE.md.

Review the current roadmap.

Review the current project state.

Implement only the current milestone.

Run applicable tests.

Update documentation.

Update the changelog.

Update the project state.

Commit only completed work.

---

# 15. AI Restrictions

An AI shall not:

Invent new project requirements.

Modify the architecture without approval.

Change repository structure.

Break compatibility intentionally.

Remove documented functionality.

Ignore testing requirements.

Generate placeholder implementations.

Leave incomplete modules.

Skip documentation updates.

---

# 16. Definition of Done

A task is complete only when:

Implementation is finished.

Code compiles successfully.

Virtual tests pass.

Documentation is updated.

Project state is updated.

Changelog is updated.

No critical defects remain.

The Product Owner approves the milestone.

---

# End of Document