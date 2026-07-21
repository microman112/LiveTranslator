# 07_ENGINE_FRAMEWORK.md

# Live Translator
## Engine Framework Implementation

Version: 1.0

Status: Approved

Author: Mohamed

Related Documents

00_IMPLEMENTATION_PLAN.md

02_CORE_FRAMEWORK.md

03_CONFIGURATION_MANAGER.md

04_LOGGING_MANAGER.md

05_DEPENDENCY_MANAGER.md

06_PROVIDER_FRAMEWORK.md

03_SRS.md

04_ARCHITECTURE.md

---

# 1. Objective

Implement a unified Engine Framework responsible for managing every processing engine used by the Live Translator plugin.

The framework shall provide a common lifecycle, configuration model, execution model, event system, diagnostics, caching, statistics, scheduling, and error recovery.

Every engine shall inherit from the Engine Base class.

---

# 2. Supported Engines

The framework shall support the approved engine order.

1. DVB Subtitle Translation

2. EPG Subtitle Search

3. EPG Translation

4. OCR Translation

5. Live Speech Translation

6. Media Identification

7. AI Voice Translation

Future engines shall be supported without framework modifications.

---

# 3. Engine Responsibilities

Every engine shall:

• Register itself

• Initialize

• Load configuration

• Validate dependencies

• Validate providers

• Start

• Execute

• Pause (future)

• Resume (future)

• Stop

• Shutdown

• Generate diagnostics

• Report statistics

---

# 4. Engine Lifecycle

Each engine shall implement the following lifecycle.

Created

↓

Registered

↓

Configured

↓

Initialized

↓

Ready

↓

Running

↓

Idle

↓

Paused (future)

↓

Stopping

↓

Stopped

↓

Shutdown

↓

Unloaded

All state transitions shall be validated.

---

# 5. Engine Base Interface

Every engine shall implement:

initialize()

shutdown()

start()

stop()

restart()

reload()

execute()

validate()

configure()

reset()

health_check()

diagnostics()

statistics()

get_status()

get_version()

No engine shall bypass the common interface.

---

# 6. Engine Registration

The Engine Manager shall register:

Engine Name

Engine Version

Engine Category

Priority

Dependencies

Supported Providers

Supported Languages

Supported Inputs

Supported Outputs

Capabilities

Configuration Profile

Health Status

---

# 7. Engine Categories

Translation

OCR

Speech

Subtitle

Media Recognition

Voice

Future categories shall be supported without framework redesign.

---

# 8. Execution Modes

Supported execution modes:

Automatic

Manual

Background

On-Demand

Scheduled (future)

Event Driven

Hybrid

Each engine shall define its supported execution modes.

---

# 9. Input Sources

The framework shall support:

DVB Subtitle Stream

DVB Audio Stream

DVB Video Frames

EPG Information

OCR Images

Microphone Audio

Recorded Audio

Subtitle Files

Network Streams

Media Samples

Future input sources shall be extensible.

---

# 10. Output Targets

The framework shall support:

Translated DVB Subtitles

Overlay Subtitles

Translated EPG

Audio Output

Voice Overlay

Notification Messages

Log Entries

Diagnostic Reports

Future output targets shall be supported.

---

# 11. Provider Integration

Engines shall communicate only through the Provider Framework.

No engine shall directly communicate with provider implementations.

Provider selection shall support:

Automatic

Manual

Priority

Fallback

Capability Matching

Performance Optimization

---

# 12. Configuration

Every engine shall expose:

Enable / Disable

Priority

Primary Language

Secondary Language

Preferred Provider

Fallback Provider

Cache Settings

Retry Policy

Timeout

Diagnostics

Performance Options

Advanced Options

Each engine shall provide its own configuration page.

---

# 13. Event Integration

Supported engine events:

Engine Registered

Engine Initialized

Engine Started

Engine Stopped

Engine Restarted

Engine Failed

Configuration Changed

Provider Changed

Translation Completed

Recognition Completed

Diagnostics Generated

All events shall use the Event Bus.

---

# 14. Scheduling

The Engine Manager shall coordinate engine execution.

Scheduling priorities:

Critical

High

Normal

Low

Background

Execution shall avoid blocking the Enigma2 user interface.

---

# 15. Cache Integration

Every engine shall integrate with the Cache Manager.

Supported cache types:

Translation Cache

Subtitle Cache

OCR Cache

Speech Cache

Media Cache

Provider Cache

Cache behavior shall be configurable.

---

# 16. Error Recovery

Recoverable failures:

Retry

↓

Alternative Provider

↓

Alternative Engine

↓

Cached Result

↓

Notify User

↓

Continue

Critical failures:

Log

↓

Generate Diagnostics

↓

Stop Affected Engine

↓

Continue Remaining Engines

No single engine shall terminate the plugin.

---

# 17. Performance Monitoring

The framework shall collect:

Execution Count

Execution Time

Average Runtime

Success Rate

Failure Rate

Provider Latency

Cache Hit Ratio

CPU Usage

Memory Usage

Network Usage

Statistics shall be available through Diagnostics.

---

# 18. Diagnostics

Every engine shall provide:

Current Status

Current Provider

Loaded Configuration

Health Status

Statistics

Last Execution

Last Failure

Dependency Status

Provider Status

Version

Runtime Information

---

# 19. Security

Engines shall:

Validate input

Sanitize provider responses

Protect credentials

Avoid exposing sensitive information

Reject malformed data

Handle unexpected provider behavior safely

---

# 20. Testing Requirements

Every engine shall successfully complete:

Registration Testing

Initialization Testing

Configuration Testing

Execution Testing

Provider Integration Testing

Cache Testing

Error Recovery Testing

Diagnostics Testing

Performance Testing

Virtual Receiver Testing

Hardware Validation

Regression Testing

---

# 21. Acceptance Criteria

The milestone is complete when:

The Engine Framework supports all seven approved engines.

The Engine Base class is implemented.

The Engine Manager operates correctly.

All lifecycle states function.

Provider integration succeeds.

Caching functions.

Diagnostics operate correctly.

Statistics are collected.

Error recovery functions.

Framework remains extensible.

Documentation is updated.

Project State is updated.

Changelog is updated.

Changes are committed to Git.

---

# End of Document