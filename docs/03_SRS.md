# 03_SRS.md

# Software Requirements Specification (SRS)

Project: Live Translator

Version: 1.0

Status: Draft

Author: Mohamed

Target Platform: Enigma2

---

# 1. Introduction

## 1.1 Purpose

This Software Requirements Specification (SRS) defines the functional and non-functional requirements for the Live Translator Enigma2 plugin.

The purpose of this document is to provide a complete, structured, and authoritative specification for the design, implementation, testing, packaging, deployment, and maintenance of the Live Translator project.

This document serves as the primary engineering reference for developers, AI coding assistants, testers, reviewers, and future maintainers.

All implementation decisions shall conform to the requirements defined in this document unless formally approved by the Product Owner.

---

## 1.2 Scope

Live Translator is a professional Enigma2 plugin designed to provide advanced translation and language assistance services for DVB television receivers.

The plugin shall support multiple translation methods including subtitle translation, speech translation, OCR translation, EPG translation, subtitle retrieval, media identification, and AI-powered voice translation.

The plugin shall be designed as a modular and extensible framework capable of supporting multiple translation providers, subtitle providers, OCR engines, speech recognition engines, AI services, and future expansion without requiring major architectural changes.

The plugin shall support installation using a single IPK package with automatic dependency management and automatic default configuration.

The system shall support both online and offline operation whenever technically possible.

---

## 1.3 Definitions

### AI

Artificial Intelligence service used for translation, speech recognition, OCR, media identification, and related processing.

### DVB

Digital Video Broadcasting television service.

### EPG

Electronic Program Guide.

### OCR

Optical Character Recognition.

### STB

Set Top Box running the Enigma2 operating system.

### Provider

A software component that delivers a service to the plugin, such as translation, OCR, subtitle retrieval, speech recognition, or media identification.

### Engine

A functional module responsible for executing one of the plugin's primary translation or identification services.

### Dependency

An external software package, library, executable, or service required by the plugin.

### Virtual Testing

Automated validation performed without requiring a physical DVB receiver.

---

## 1.4 References

The following project documents are considered authoritative references for the Live Translator project:

01_PROJECT.md

02_MASTER_PROMPT.md

04_ARCHITECTURE.md

05_ROADMAP.md

06_AI_CONTEXT.md

07_PROJECT_STATE.json

08_CHANGELOG.md

09_CODING_STANDARDS.md

10_TESTING_STANDARDS.md

All future development shall remain consistent with these documents.
# 4. Translation Engines

The Live Translator plugin shall implement independent translation engines managed by the Engine Manager.

Each engine shall be independently configurable, enabled or disabled by the user, and capable of operating without affecting the functionality of other engines.

Each engine shall support provider prioritization, automatic failover, logging, diagnostics, and independent configuration.

---

## 4.1 DVB Subtitle Translation Engine

The DVB Subtitle Translation Engine shall provide real-time translation of DVB subtitles.

The engine shall:

• Detect DVB subtitles.

• Decode subtitle streams.

• Extract subtitle text.

• Detect the original language automatically whenever possible.

• Translate subtitles into the user-selected language.

• Overlay translated subtitles on the video.

• Preserve subtitle timing.

• Maintain subtitle synchronization.

• Cache repeated translations.

• Automatically recover from subtitle interruptions.

The engine shall support multiple translation providers.

---

## 4.2 EPG Subtitle Search Engine

The EPG Subtitle Search Engine shall automatically retrieve subtitles from Internet subtitle providers.

The engine shall:

• Read the current channel EPG.

• Detect the current programme.

• Determine season and episode information whenever available.

• Search one or more subtitle providers.

• Match subtitles using language, duration, title, episode and release information.

• Download the best matching subtitle.

• Verify subtitle integrity.

• Automatically synchronize subtitle timing.

• Overlay subtitles during playback.

• Retry alternate providers when no subtitle is found.

The engine shall allow manual subtitle selection when multiple matches exist.

---

## 4.3 EPG Translation Engine

The EPG Translation Engine shall translate Electronic Program Guide information.

The engine shall support:

• Event title.

• Short description.

• Extended description.

• Genre.

• Programme information.

Translated EPG data shall be displayed inside the standard Enigma2 interface without modifying the original EPG database.

Caching shall minimize repeated translations.

---

## 4.4 OCR Translation Engine

The OCR Translation Engine shall translate on-screen text extracted from video frames.

The engine shall:

• Capture video frames.

• Detect visible text.

• Perform OCR processing.

• Detect language automatically whenever possible.

• Translate recognized text.

• Overlay translated text.

• Ignore duplicated text.

• Cache previous OCR results.

OCR processing frequency shall be configurable.

---

## 4.5 Live Speech Translation Engine

The Live Speech Translation Engine shall perform real-time speech recognition and translation.

The engine shall:

• Capture audio.

• Detect spoken language.

• Convert speech to text.

• Translate recognized speech.

• Display translated subtitles.

• Handle multiple speakers whenever supported by the selected provider.

Speech recognition providers shall be configurable.

---

## 4.6 Media Identification Engine

The Media Identification Engine shall identify currently playing media when other identification methods fail.

The engine shall:

• Capture approximately 30 seconds of the current audio or video.

• Generate media fingerprints.

• Query Internet identification services.

• Cross-reference multiple providers.

• Identify movies, television series, documentaries, sporting events and other supported media.

• Return confidence scores.

• Supply identified information to other translation engines.

This engine shall operate as an automatic fallback mechanism.

---

## 4.7 AI Voice Translation Engine

The AI Voice Translation Engine shall generate translated speech audio.

The engine shall:

• Receive translated text.

• Generate speech using AI voice providers.

• Support multiple voices.

• Support multiple languages.

• Allow voice selection.

• Allow speech speed adjustment.

• Allow volume adjustment.

• Synchronize generated speech with video playback whenever technically possible.

The user may enable or disable AI voice generation independently.

---

# 5. User Interface

The plugin shall provide a professional Enigma2 user interface fully operable using the remote control.

All screens shall remain responsive and consistent with Enigma2 user interface standards.

---

## 5.1 Main Menu

The Main Menu shall provide access to:

• Translation Engines

• Providers

• Languages

• API Configuration

• General Settings

• Diagnostics

• Logs

• Updates

• About

---

## 5.2 General Configuration

General configuration shall include:

• Default language

• Source language

• Automatic language detection

• Cache settings

• Network settings

• Startup behaviour

• Debug mode

• Logging level

• Performance settings

---

## 5.3 Engine Configuration

Each translation engine shall provide its own configuration screen.

Every engine shall support independent configuration.

Settings may include:

• Enable/Disable

• Provider priority

• Language selection

• Timeouts

• Retry attempts

• Cache options

• Performance limits

• Synchronization options

---

## 5.4 Provider Configuration

Each provider shall provide an independent configuration page.

Configuration may include:

• Enable/Disable

• Priority

• API Key

• Endpoint

• Timeout

• Retry count

• Daily limits

• Diagnostics

---

## 5.5 API Configuration

The plugin shall provide secure management of API credentials.

Supported features include:

• API key storage

• API validation

• Connectivity testing

• Usage information where supported

• Import and export

---

## 5.6 Language Configuration

The Language configuration shall support:

• Default language

• Preferred translation language

• Source language

• Automatic language detection

• Multiple fallback languages

---

## 5.7 Logging Screen

The Logging screen shall provide:

• Real-time log viewing

• Log filtering

• Log export

• Log clearing

• Diagnostic information

---

## 5.8 Diagnostics Screen

Diagnostics shall display:

• Installed dependencies

• Provider status

• Engine status

• Network connectivity

• Python version

• Enigma2 version

• Hardware information

• Memory usage

• Storage usage

---

## 5.9 About Screen

The About screen shall display:

• Plugin name

• Version

• Build number

• Author

• Copyright

• Supported platforms

• Installed providers

• License information

---

# 6. Provider Framework

The Provider Framework shall provide a standardized interface for all external services.

Provider implementations shall remain independent from plugin core logic.

---

## 6.1 Translation Providers

Supported translation providers may include:

• Google Translate

• DeepL

• LibreTranslate

• OpenAI

• Microsoft Translator

Additional providers shall be supported through modular extensions.

---

## 6.2 Speech Recognition Providers

Supported speech providers may include:

• Whisper

• Vosk

• Google Speech

• Microsoft Speech

• Other compatible providers

---

## 6.3 OCR Providers

Supported OCR providers may include:

• Tesseract OCR

• EasyOCR

• PaddleOCR

• Other compatible OCR engines

---

## 6.4 Subtitle Providers

Supported subtitle providers may include:

• OpenSubtitles

• SubDL

• Addic7ed

• Podnapisi

• Other compatible providers

---

## 6.5 Media Identification Providers

Supported media identification providers may include:

• TMDb

• TVDb

• IMDb

• Trakt

• MusicBrainz (where applicable)

• Audio fingerprint providers

The Provider Framework shall support future providers without requiring architectural modifications.
# 7. Installation

The Live Translator plugin shall be distributed as a single installable IPK package.

The installation process shall require minimal user interaction and automatically prepare the runtime environment.

---

## 7.1 Single IPK Package

The plugin shall be distributed as one installation package.

The package shall include:

• Plugin binaries

• Python modules

• Configuration templates

• Icons

• Language resources

• Default configuration

• Installation scripts

The user shall not be required to install multiple packages manually.

---

## 7.2 Automatic Dependency Installation

The installer shall automatically detect required software dependencies.

When supported by the target Enigma2 distribution, the installer shall:

• Detect missing packages

• Download required packages

• Install dependencies

• Verify successful installation

• Retry failed installations

• Report unrecoverable failures

The installation process shall continue whenever optional dependencies cannot be installed.

---

## 7.3 Automatic Environment Detection

During installation the plugin shall automatically detect:

• Enigma2 distribution

• Python version

• CPU architecture

• Available storage

• Available memory

• Network connectivity

• Package manager

The plugin shall configure itself according to the detected environment whenever possible.

---

## 7.4 Default Configuration

After installation the plugin shall automatically generate default configuration values.

The user shall be able to begin using the plugin without completing a setup wizard.

Default values shall be optimized for first-time users.

---

## 7.5 Upgrade Support

The installer shall support upgrades from previous versions.

Upgrades shall preserve:

• User settings

• API keys

• Provider priorities

• Language preferences

• Engine configuration

Configuration migration shall occur automatically whenever required.

---

# 8. Configuration

The plugin shall provide centralized configuration management with independent configuration pages for every subsystem.

Configuration shall be stored persistently and validated before use.

---

## 8.1 Global Settings

Global settings shall include:

• Default language

• Source language

• User interface language

• Automatic startup

• Logging level

• Cache settings

• Network settings

• Performance options

---

## 8.2 Engine Settings

Each translation engine shall have an independent configuration page.

Each engine shall support settings including:

• Enable or Disable

• Translation provider priority

• Retry count

• Timeout

• Cache

• Synchronization

• Performance limits

• Debug options

Engine configuration shall not affect unrelated engines.

---

## 8.3 Provider Settings

Each provider shall have an independent configuration page.

Provider configuration may include:

• Enable or Disable

• API Key

• Endpoint

• Authentication

• Priority

• Timeout

• Retry attempts

• Daily request limits

---

## 8.4 Cache Settings

The cache system shall support:

• Enable or Disable

• Cache expiration

• Maximum cache size

• Automatic cleanup

• Manual cleanup

• Cache statistics

---

## 8.5 Debug Settings

Debug settings shall support:

• Debug mode

• Extended logging

• Provider diagnostics

• Engine diagnostics

• Performance diagnostics

• Export diagnostic reports

---

# 9. Non-Functional Requirements

The plugin shall satisfy the following non-functional requirements.

---

## 9.1 Performance

The plugin shall:

• Minimize CPU usage

• Minimize memory usage

• Minimize storage consumption

• Avoid unnecessary network requests

• Use caching where appropriate

• Load modules only when required

The plugin shall remain responsive during normal receiver operation.

---

## 9.2 Reliability

The plugin shall:

• Continue operating after recoverable failures

• Detect unavailable providers

• Automatically switch to backup providers

• Prevent data corruption

• Preserve configuration integrity

• Recover gracefully from runtime errors

---

## 9.3 Security

The plugin shall:

• Securely store API credentials

• Protect configuration files

• Validate all external input

• Verify downloaded data

• Prevent unauthorized configuration modification

Sensitive information shall never be exposed through logs.

---

## 9.4 Compatibility

The plugin shall support:

• Approved Enigma2 distributions

• Python 2

• Python 3

• Supported CPU architectures

• Future provider expansion

Compatibility layers shall isolate platform-specific implementation differences whenever possible.

---

## 9.5 Maintainability

The software shall be designed to support:

• Modular implementation

• Independent engine updates

• Independent provider updates

• Configuration migration

• Documentation consistency

• Automated testing

---

## 9.6 Scalability

The architecture shall support future additions including:

• New translation engines

• Additional providers

• Additional OCR engines

• Additional speech engines

• Additional subtitle providers

• Future AI services

Architectural redesign shall not be required to support future expansion.

---

# 10. Error Handling

The plugin shall implement centralized error handling.

Errors shall be classified as:

• Information

• Warning

• Recoverable Error

• Critical Error

The system shall:

• Log all errors

• Display user-friendly messages

• Continue operation whenever possible

• Automatically retry transient failures

• Switch to backup providers when available

• Prevent application crashes caused by recoverable errors

Critical failures shall be reported with sufficient diagnostic information to support troubleshooting.
# 11. Logging

The Live Translator plugin shall implement a centralized logging system to support diagnostics, troubleshooting, performance monitoring, and software maintenance.

---

## 11.1 Log Levels

The logging system shall support the following log levels:

• Debug

• Information

• Warning

• Error

• Critical

---

## 11.2 Logged Information

The logging system shall record:

• Plugin startup and shutdown

• Engine initialization

• Provider initialization

• Dependency installation

• Configuration changes

• Translation requests

• OCR requests

• Speech recognition events

• Subtitle searches

• Media identification requests

• API communication

• Installation events

• Upgrade events

• Runtime exceptions

• Performance statistics

---

## 11.3 Log Management

The logging system shall support:

• Automatic log rotation

• Maximum log size

• Automatic cleanup of old logs

• Manual log export

• Manual log deletion

• Diagnostic report generation

---

## 11.4 Privacy

Sensitive information including API keys, authentication tokens, passwords, and personal information shall never be written to log files.

---

# 12. Testing Requirements

The Live Translator project shall include comprehensive testing throughout development.

Testing shall be performed before every release.

---

## 12.1 Unit Testing

Individual modules shall be tested independently.

Unit testing shall include:

• Core Framework

• Configuration Manager

• Provider Manager

• Engine Manager

• Dependency Manager

• Cache Manager

• API Manager

• Logging Manager

---

## 12.2 Integration Testing

Integration testing shall verify interaction between:

• Engines

• Providers

• Configuration

• User Interface

• Dependency Manager

• Installation

---

## 12.3 Virtual Receiver Testing

The project shall support virtual validation without requiring a physical DVB receiver.

Virtual testing shall verify:

• Plugin startup

• Configuration loading

• Dependency validation

• Provider initialization

• Engine loading

• Package integrity

• Error recovery

---

## 12.4 Mock Provider Testing

Mock providers shall be used to validate:

• Translation

• OCR

• Speech Recognition

• Subtitle Retrieval

• Media Identification

without requiring external Internet services.

---

## 12.5 Performance Testing

Performance testing shall evaluate:

• CPU usage

• Memory usage

• Storage consumption

• Network traffic

• Startup time

• Translation latency

---

## 12.6 Regression Testing

Regression testing shall ensure that new functionality does not break existing features.

---

## 12.7 User Acceptance Testing

Before production release, complete functional validation shall be performed using one or more supported Enigma2 receivers.

---

# 13. Packaging Requirements

The plugin shall be released as a professional installation package.

---

## 13.1 Package Format

The official release shall be distributed as a single installable IPK package.

---

## 13.2 Package Contents

The package shall contain:

• Plugin source

• Compiled resources

• Configuration templates

• Icons

• Language files

• Installation scripts

• Upgrade scripts

• Metadata

---

## 13.3 Installation Verification

The installation package shall verify:

• Package integrity

• Required dependencies

• Platform compatibility

• Python compatibility

• Available storage

---

## 13.4 Build Validation

Before release the build system shall verify:

• Successful build

• Dependency validation

• Syntax validation

• Packaging validation

• Documentation consistency

• Version consistency

---

# 14. Versioning

The Live Translator project shall implement controlled software version management.

---

## 14.1 Version Format

The project shall use Semantic Versioning.

Examples:

0.1.0

0.5.0

1.0.0

1.1.2

2.0.0

---

## 14.2 Version Updates

Every release shall update:

• Plugin Version

• Build Number

• Changelog

• Documentation

• Project State

---

## 14.3 Release Notes

Every release shall include release notes describing:

• New features

• Improvements

• Bug fixes

• Compatibility changes

• Known limitations

---

# 15. Acceptance Criteria

The Live Translator project shall be considered ready for release only when all of the following conditions are satisfied.

---

## 15.1 Functional Acceptance

All approved translation engines operate correctly.

All configuration screens operate correctly.

All supported providers initialize correctly.

Automatic dependency management functions correctly.

Installation completes successfully.

Upgrade process completes successfully.

---

## 15.2 Quality Acceptance

Source code complies with Coding Standards.

Documentation is complete.

Testing requirements are satisfied.

No unresolved critical defects remain.

Repository consistency is maintained.

---

## 15.3 Packaging Acceptance

The official IPK package:

• Installs successfully

• Starts successfully

• Detects supported environments

• Loads configuration

• Initializes engines

• Initializes providers

• Completes virtual validation

---

# 16. Future Enhancements

The architecture shall support future expansion without requiring major redesign.

Potential future enhancements include:

• Additional translation providers

• Additional OCR engines

• Additional subtitle providers

• Additional speech recognition providers

• Additional AI voice providers

• Local AI model support

• Offline translation models

• Automatic language learning

• Cloud synchronization

• User profile synchronization

• Plugin marketplace integration

• Additional media recognition providers

• Advanced analytics

• Performance optimization

• Support for future Enigma2 platform improvements

Future enhancements shall remain compatible with the modular architecture defined by this project whenever technically feasible.

---

# End of Document