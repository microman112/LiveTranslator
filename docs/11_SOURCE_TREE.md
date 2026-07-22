# 11_SOURCE_TREE.md

# Live Translator
## Source Tree Specification

Version: 1.0

Status: Frozen

Author: Mohamed

Last Updated: 21 July 2026

Related Documents

- 03_SRS.md
- 04_ARCHITECTURE.md
- implementation/00_IMPLEMENTATION_PLAN.md
- implementation/01_PLUGIN_SKELETON.md
- implementation/02_CORE_FRAMEWORK.md
- implementation/03_CONFIGURATION_MANAGER.md
- implementation/04_LOGGING_MANAGER.md
- implementation/05_DEPENDENCY_MANAGER.md
- implementation/06_PROVIDER_FRAMEWORK.md
- implementation/07_ENGINE_FRAMEWORK.md
- implementation/08_UI_FRAMEWORK.md

---

# 1. Purpose

This document defines the complete source tree for the Live Translator project.

It is the authoritative reference for:

- Folder organization
- File organization
- Class ownership
- Module responsibilities
- Import hierarchy
- Dependency boundaries

Every source file shall exist in the location defined by this document.

---

# 2. Repository Structure

LiveTranslator/

.github/

.ai/

docs/

licenses/

resources/

scripts/

package/

build/

releases/

templates/

tests/

tools/

third_party/

src/

---

# 3. Source Tree

src/

plugin.py

bootstrap.py

version.py

---

core/

plugin_core.py

lifecycle.py

service_registry.py

event_bus.py

application_context.py

startup_manager.py

shutdown_manager.py

---

managers/

configuration_manager.py

logging_manager.py

dependency_manager.py

provider_manager.py

engine_manager.py

notification_manager.py

cache_manager.py

api_manager.py

update_manager.py

diagnostics_manager.py

task_manager.py

---

engines/

base_engine.py

engine_factory.py

engine_registry.py

dvb_subtitle_engine.py

epg_search_engine.py

epg_translation_engine.py

ocr_engine.py

speech_engine.py

media_identification_engine.py

ai_voice_engine.py

---

providers/

base_provider.py

provider_factory.py

provider_registry.py

translation_provider.py

ocr_provider.py

speech_provider.py

subtitle_provider.py

media_provider.py

voice_provider.py

---

screens/

main_menu.py

settings_screen.py

provider_screen.py

engine_screen.py

dependency_screen.py

diagnostics_screen.py

log_viewer.py

performance_screen.py

about_screen.py

---

components/

menu_builder.py

dialogs.py

widgets.py

progress.py

status_bar.py

message_box.py

---

services/

translation_service.py

subtitle_service.py

speech_service.py

ocr_service.py

media_service.py

voice_service.py

---

network/

api_client.py

download_manager.py

request_manager.py

response_parser.py

---

cache/

cache_backend.py

translation_cache.py

ocr_cache.py

subtitle_cache.py

speech_cache.py

media_cache.py

---

models/

engine_model.py

provider_model.py

configuration_model.py

statistics_model.py

diagnostics_model.py

---

utils/

constants.py

helpers.py

exceptions.py

filesystem.py

environment.py

platform.py

validators.py

compatibility.py

language.py

time_utils.py

string_utils.py

---

tests/

unit/

integration/

virtual_receiver/

performance/

providers/

engines/

ui/

---

# 4. Dependency Hierarchy

plugin.py

↓

bootstrap.py

↓

Plugin Core

↓

Managers

↓

Services

↓

Providers

↓

Engines

↓

User Interface

↓

Utilities

No reverse dependencies are permitted.

---

# 5. Import Rules

Modules may import only lower-level modules.

Allowed:

Plugin Core → Managers

Managers → Services

Services → Providers

Providers → Network

Engines → Providers

Screens → Managers

Utilities → None

Forbidden:

Utilities → Screens

Providers → Screens

Managers → Screens

Screens → Providers

Engines → UI

Network → UI

Circular imports are prohibited.

---

# 6. Class Ownership

Each file shall contain one primary public class.

Helper classes shall remain private unless explicitly shared.

Shared interfaces shall reside in their dedicated module.

---

# 7. Naming Standards

Classes:

PascalCase

Methods:

snake_case

Variables:

snake_case

Constants:

UPPER_CASE

Files:

snake_case.py

Packages:

lowercase

---

# 8. Package Initialization

Every package shall include:

__init__.py

No business logic shall be placed inside package initialization files.

---

# 9. Testing Structure

Every module shall have corresponding tests.

Example:

configuration_manager.py

↓

tests/unit/test_configuration_manager.py

Provider modules shall include provider-specific integration tests.

Engine modules shall include engine lifecycle tests.

---

# 10. Coding Rules

Every file shall:

Compile successfully

Contain complete implementations

Avoid placeholder code

Avoid TODO comments

Include documentation where appropriate

Pass linting

Pass unit testing

Pass virtual receiver testing

---

# 11. Future Expansion

The architecture shall support adding:

Additional engines

Additional providers

Additional UI screens

Additional diagnostics

Additional cache implementations

Additional APIs

Without modifying existing framework components.

---

# 12. Definition of Complete

The source tree is considered complete when:

All directories exist.

All modules exist.

All public classes are implemented.

Imports follow the dependency hierarchy.

Tests exist for every module.

Documentation matches implementation.

The project builds successfully.

The plugin installs successfully.

The plugin starts successfully.

The plugin shuts down successfully.

---

# End of Document