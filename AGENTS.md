# AI Agent Guidelines - Product Wizard

---
template_updated: 2025-09-29T06:04:28
project_updated: 2025-09-30T00:00:00
---

# AI Agent Guidelines

## 🚨 IMMEDIATE AI AGENT INSTRUCTIONS

**STEP 1: RUN VERSION CHECK NOW**
```bash
~/.agents/scripts/check-rules-datetime.sh
```

**STEP 2: MANDATORY - READ THESE FILES IN THIS ORDER BEFORE ANY WORK**:

1. **VERSION CHECK COMPLETE** - Rule updates have been synchronized
   - If outdated, review global template changes before proceeding
   - User trigger phrases: "check for rule updates", "review rule version", "update check", "check rules"
2. **`.dev/ai/STATE-OF-THE-PROJECT.md`** (or create if missing) - Current project context:
   - Must be <14 days old or update it first
   - Use template: `~/.agents/templates/STATE-OF-THE-PROJECT-TEMPLATE.md`
   - Provides essential context eliminating need for comprehensive audits

3. **`~/.agents/AGENTS.md`** - PRIMARY universal AI standards including:
   - STATE-OF-THE-PROJECT system requirements
   - Documentation hierarchy and anti-duplication rules
   - Agent onboarding process (4-step reading order)
   - Handoff task system with `[NEXT_ACTION: task | PRIORITY: 1-5]` format
   - Security protocols and input validation standards
   - Git commit standards (NO AI attribution in commits)
   - AI document organization requirements (`.dev/ai/` structure)
   - Multi-platform integration (Claude, GPT, Gemini, Copilot, etc.)
   - Time tracking and changelog requirements
   - Quality assurance checklists

4. **`~/.claude/CLAUDE.md`** - Additional universal rules:
   - Communication style and tone
   - Mandatory changelog and time tracking formats
   - Development workflow standards
   - Platform-specific integrations

**⚠️ WARNING**: Failure to review these files will result in incorrect behavior and non-compliant outputs.

### 🔄 Automatic Update Checking
**MANDATORY**: Check for rule updates when:
- Starting work on any project (run check-rules-datetime.sh)
- User says: "check for rule updates", "review rule version", "update check", "check rules", "are the rules current"
- More than 24 hours since last session
- Any mention of "outdated rules" or "update rules"

**Quick Check Command**: `~/.agents/scripts/check-rules-datetime.sh`
**Action on Outdated Rules**: If >24 hours behind, review changes and suggest updating

## Repository Guidelines

Product Wizard is a complete development pipeline built on top of GitHub's Spec Kit. It guides users from initial idea to deployed application using Spec-Driven Development (SDD) methodology. The repository structure consists of spec-kit as a Git submodule containing all core Spec Kit functionality and templates.

## Project Structure & Module Organization

```
product-wizard/
├── spec-kit/              # Git submodule - GitHub Spec Kit core
│   ├── src/specify_cli/   # Specify CLI Python package
│   ├── scripts/           # Bash and PowerShell automation scripts
│   │   ├── bash/          # Shell scripts for Unix/Linux/macOS
│   │   └── powershell/    # PowerShell scripts for Windows/cross-platform
│   ├── templates/         # Core templates for spec-driven development
│   │   ├── commands/      # Slash command templates for AI agents
│   │   ├── spec-template.md
│   │   ├── plan-template.md
│   │   └── tasks-template.md
│   ├── docs/              # Spec Kit documentation
│   └── memory/            # Project constitution and principles
├── .dev/                  # AI workspace and local tooling
│   ├── ai/                # AI-generated documentation and state
│   ├── scripts/           # Project-specific helper scripts
│   ├── temp/              # Temporary files
│   └── notes/             # Development notes
├── README.md              # Product Wizard overview
└── .gitmodules            # Submodule configuration
```

## Build, Test, and Development Commands

### Spec Kit CLI - Specify

```bash
# Installation (for development)
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git

# Or run directly without installing
uvx --from git+https://github.com/github/spec-kit.git specify init <PROJECT_NAME>

# Local development (from spec-kit directory)
python -m src.specify_cli --help
python -m src.specify_cli init demo-project --ai claude

# Check system prerequisites
specify check

# Initialize a new project
specify init <project-name> --ai <agent>

# Initialize in current directory
specify init . --ai <agent>
specify init --here --ai <agent>

# Available AI agents: claude, gemini, copilot, cursor, qwen, opencode, codex, windsurf, kilocode, auggie, roo
```

### Git Submodule Management

```bash
# Clone with submodules
git clone --recurse-submodules https://github.com/grigb/product-wizard.git

# Update submodule to latest
git submodule update --init --recursive

# Pull latest changes including submodule updates
git pull --recurse-submodules
```

### Spec-Driven Development Workflow Commands

These slash commands are available after running `specify init`:

```bash
/constitution  # Create or update project governing principles
/specify       # Define what to build (requirements and user stories)
/clarify       # Clarify underspecified areas (run before /plan)
/plan          # Create technical implementation plans
/tasks         # Generate actionable task lists
/analyze       # Cross-artifact consistency & coverage analysis
/implement     # Execute all tasks to build the feature
```

```

## Coding Style & Naming Conventions

### Markdown & Documentation
- Use clear headings, short paragraphs, and relative links
- Filenames: prefer `kebab-case.md` for new docs
- Keep changes scoped; avoid drive-by edits outside your topic

### Python (Specify CLI)
- Follow PEP 8 conventions
- Use type hints where appropriate
- Package structure: `src/specify_cli/`
- Dependencies managed via `pyproject.toml`
- Entry point: `specify = "specify_cli:main"`

### Shell Scripts
- Provide both Bash (`.sh`) and PowerShell (`.ps1`) variants for cross-platform compatibility
- Bash scripts: Use `#!/usr/bin/env bash` shebang
- PowerShell scripts: Use `.ps1` extension
- Store in `scripts/bash/` and `scripts/powershell/` respectively
- Common functions in `common.sh` / `common.ps1`

### 🚨 MANDATORY TODO COMMENT REQUIREMENTS
**AI agents MUST add TODO comments whenever code is incomplete or temporary:**

- **When to add TODO comments**:
  - Any placeholder or stub implementation: `// TODO: Implement actual logic here`
  - Mock/dummy data used temporarily: `// TODO: Replace mock data with real API call`
  - Missing error handling: `// TODO: Add proper error handling for edge cases`
  - Incomplete features: `// TODO: Complete feature implementation`
  - Hardcoded values needing configuration: `// TODO: Move to config file`
  - Missing validation: `// TODO: Add input validation`
  - Performance issues known but not addressed: `// TODO: Optimize for large datasets`
  - Security concerns requiring attention: `// TODO: Add authentication check`
  - Missing tests: `// TODO: Add unit tests for this function`
  - Temporary workarounds: `// TODO: Remove workaround after upstream fix`

- **TODO Comment Format**:
  ```
  // TODO: [Brief description of what needs to be done]
  // TODO(category): [More specific todos - SECURITY, PERFORMANCE, TESTING, etc]
  // TODO(priority): [HIGH/MEDIUM/LOW] - [Description for prioritization]
  # TODO: [Python/Ruby/Shell style]
  <!-- TODO: [HTML/XML style] -->
  ```

- **CRITICAL**: This allows quick auditing of incomplete code with `grep -r "TODO"` or IDE search
- **NO INCOMPLETE CODE WITHOUT TODOs**: Every piece of temporary, incomplete, or placeholder code MUST have a TODO
- **Audit Command**: `grep -rn "TODO" --include="*.{js,ts,py,java,go,rs,cpp,h}" .`

### Data Display & Formatting Standards
- **NEVER use ASCII tables**: Don't create tables with pipes (|), dashes (-), plus signs (+), or box-drawing characters
- **Markdown tables only when necessary**: Use proper Markdown table syntax that renders correctly
- **Prefer structured lists**: Use bullet points and indentation for data presentation
- **Alternative formats for complex data**:
  - Hierarchical bullet lists with clear headers
  - Code blocks with JSON/YAML for structured data
  - Descriptive paragraphs for simple comparisons
  - Numbered lists for sequential or ranked data

## Testing Guidelines

### Spec Kit Testing
- Manual testing of CLI workflows (specify init, check)
- Validation of generated templates and directory structures
- Cross-platform testing (Bash vs PowerShell scripts)
- Test with multiple AI agents (Claude, Gemini, Copilot, etc.)
- Verify submodule integrity after updates

### Template Validation
- Ensure all placeholders are replaced correctly
- Validate script execution from generated projects
- Check slash command functionality across agents

## 🔌 MCP SERVER USAGE RULES

### Playwright MCP Server (MANDATORY)
**CRITICAL: AI agents must ONLY use Playwright via MCP server tools**

**FORBIDDEN - NEVER DO THIS**:
- ❌ `npx playwright ...` commands
- ❌ `playwright test` or `playwright codegen` commands
- ❌ Writing scripts that execute playwright via command line
- ❌ Any direct playwright CLI invocation

**REQUIRED - ALWAYS DO THIS**:
- ✅ Use MCP server tools: `mcp__playwright__*` functions
- ✅ `mcp__playwright__browser_navigate` for navigation
- ✅ `mcp__playwright__browser_click` for interactions
- ✅ `mcp__playwright__browser_screen_capture` for screenshots
- ✅ All other `mcp__playwright__*` tools as needed

**Why**: MCP server provides:
- Secure, sandboxed execution
- Proper permission handling
- Consistent cross-platform behavior
- Better error handling and logging
- Direct integration with agent workflows

**Enforcement**: If you find yourself needing playwright functionality, STOP and use the MCP tools instead. Never fall back to CLI commands.

## Version Control & Git Operating Rules

### Agent Operating Rules
**CRITICAL: Agents must NEVER create commits or branches without explicit user permission**

- **Only the user may create commits**: Agents must **never** run `git commit`, `git push`, or any related VCS write commands unless explicitly instructed
- **NO branch creation**: Agents must **NEVER** create new branches (`git branch`, `git checkout -b`)
- **User permission required**: Agents may only commit when the user explicitly requests it (e.g., "please commit", "create a commit", "commit these changes")
- **Stage and inspect only**: Agents may stage changes (`git add`) or inspect changes (`git status`, `git diff`) if requested, but responsibility for recording commits rests solely with the user
- **Pause and ask**: If a workflow appears to require a commit or branch, agents must pause and ask the user how to proceed instead of attempting it themselves
- **NO automatic commits**: Even if changes are complete, do not commit unless explicitly asked
- **NO CO-AUTHOR ATTRIBUTION**: NEVER add "Co-Authored-By: Claude" or any AI attribution to commits
- **NO AI MARKERS IN COMMITS**: Do not add "🤖 Generated with Claude Code" or similar markers
- **USER'S WORK ONLY**: All commits belong solely to the user - AI assistants are tools, not contributors

### Commit & Pull Request Guidelines

**Spec-Driven Development Workflow:**
- Feature branches: Auto-created by `/specify` command (e.g., `001-feature-name`)
- Commits: Conventional-style prefix and imperative subject
  - `docs: update spec template`
  - `feat: add new AI agent support`
  - `fix: resolve script execution issue`
  - `chore: update dependencies`
- Branch naming for Spec Kit development: descriptive feature branches
- PR requirements:
  - Include concise description
  - Reference affected specs or templates
  - List impacted AI agents (Claude, Gemini, etc.)
- Clean commit messages: Professional and focused on changes made

## AI Document Organization (CRITICAL)

**ALL AI-generated documentation MUST follow these rules:**
**REFERENCE**: See `~/.agents/templates/AI_DOCUMENT_ORGANIZATION.md` for complete structure

### Directory Structure
```
.dev/ai/                     # Root - MUST contain only directories, NO FILES
├── archives/                # Outdated but preserved documents
├── audits/                  # System reviews, code audits, assessments
├── configs/                 # Generated configurations
├── conversations/           # Discussion tracking, meeting notes
├── designs/                 # Architecture designs, diagrams
├── documentation/           # Generated docs, guides, explanations
├── handovers/               # Session continuity between agents
├── migrations/              # Migration plans, upgrade guides
├── monitoring/              # Performance metrics, health checks
├── plans/                   # Strategic plans, roadmaps, strategies
├── prompts/                 # Prompt templates, AI instructions
├── reports/                 # Analysis results, status updates
├── research/                # Research findings, investigations
├── reviews/                 # Code reviews, document reviews
├── scratch/                 # Temporary work, drafts
├── templates/               # Reusable templates, boilerplates
├── testing/                 # Test plans, results, coverage
├── troubleshooting/         # Debug logs, error analysis
└── workflows/               # Process definitions, automation
```

### Important Rules
- **CRITICAL**: NO files at `.dev/ai/` root - everything in subdirectories
- **ALWAYS** use PLURAL directory names (plans, reports, audits, etc.)
- **ALWAYS** use timestamp prefix: `YYYY-MM-DD-HH-MM-[Tool]-[Description].md`
  - **MANDATORY**: Use `date +%Y-%m-%d-%H-%M` command for accurate timestamps
  - **NO FRONT MATTER**: Don't add YAML headers unless requested
- **AUTO-PLACE** documents based on context (see decision tree in template)
- **ONLY EXCEPTION**: When user explicitly requests a file in a specific location

### 🚨 CRITICAL: Temporary Scripts Rule
**MANDATORY LOCATION**: `.dev/ai/scripts-temp/` for ALL temporary/utility scripts

**When creating temporary scripts (NOT part of core application):**
- **MUST store in**: `.dev/ai/scripts-temp/`
- **Examples**: API test scripts, data analysis utilities, quick automation, dev helpers
- **Naming**: `YYYY-MM-DD-HH-MM-[Tool]-[Purpose].{extension}`
- **Auto-cleanup**: Scripts >30 days old can be removed

**This keeps temporary scripts clearly separated from production code!**

### 🚨 CRITICAL: Prompt Library Management
**MANDATORY**: All prompts used during agent interactions MUST be added to the prompt library

**Prompt Library Location**: `.dev/prompts/`

**Library Structure:**
- **Index**: `.dev/prompts/index.md` - Master catalog of all prompts
- **Small Prompts**: `.dev/prompts/small-prompts.md` - Short prompts (< 500 words)
- **Large Prompts**: Individual files in `.dev/prompts/` for complex prompts (> 500 words)
- **Templates**: `.dev/prompts/templates/` - Templates for creating new prompts

**When to add prompts:**
- **ANY prompt used**: When you use a prompt to help the user, add it to the library
- **Effective prompts**: Prompts that work well for specific tasks or scenarios
- **User-requested prompts**: When user asks for a prompt to be saved
- **Template prompts**: Reusable prompts for common tasks

**Prompt Addition Requirements:**
- **MUST add immediately**: Don't wait for user to ask - add prompts as you use them
- **Choose location**: Small prompts go in `small-prompts.md`, large prompts get individual files
- **Include context**: Add brief description of when/why to use the prompt
- **Categorize**: Use clear categories and tags for organization
- **Format consistently**: Follow the established prompt library format
- **Update index**: Add entries to `index.md` for discoverability
- **Update library**: Keep the library current and comprehensive

**File Naming for Large Prompts:**
- Format: `[category]-[descriptive-name].md`
- Example: `analysis-complex-system-audit.md`

**This ensures the prompt library grows organically and captures all effective prompts used in the project!**

### Auto-Placement Examples
- "make a plan" → `.dev/ai/plans/YYYY-MM-DD-HH-MM-[Tool]-plan.md`
- "track discussion" → `.dev/ai/conversations/YYYY-MM-DD-HH-MM-[Tool]-discussion.md`
- "handover" → `.dev/ai/handovers/YYYY-MM-DD-HH-MM-[Tool]-handover.md`
- "research X" → `.dev/ai/research/YYYY-MM-DD-HH-MM-[Tool]-X-research.md`
- "audit Y" → `.dev/ai/audits/YYYY-MM-DD-HH-MM-[Tool]-Y-audit.md`

### Migration Completed
[Track what has been migrated if reorganizing existing AI docs. Example:]
- ✅ All files from `docs/ai/` moved to appropriate subdirectories
- ✅ All files from `docs/handovers/` moved to `.dev/ai/handovers/`
- ✅ Feature analysis moved to `.dev/ai/audits/feature-analysis/`
- ✅ No loose files at `.dev/ai/` root

## AI Document Migration Status

[This section tracks if AI document migration has been completed]

**Status**: ⏳ PENDING / ✅ COMPLETE / ❌ NOT NEEDED

<!-- When migration is complete, update this section: -->
<!--
**✅ MIGRATION COMPLETE** - [Date]
- Migrated by: [Tool Name]
- Migration report: `.dev/ai/reports/[timestamp]-[tool]-migration-report.md`
- Files migrated: [count]
- Validation passed: ✅

### Migration Summary
- ✅ All AI-generated files moved to `.dev/ai/` subdirectories
- ✅ Changelogs relocated to `.dev/ai/changelogs/`
- ✅ Time-logs relocated to `.dev/ai/time-logs/`
- ✅ No loose files at `.dev/ai/` root
- ✅ All directories use plural names
- ✅ Empty directories removed

**Note to future agents**: Migration is complete. Do not re-run unless fixing specific issues.
-->

## Documentation Standards

### Markdown Formatting
**IMPORTANT**: Use GitHub Flavored Markdown (GFM) for all documentation.

#### GFM Rules
- **Line breaks**: Add blank lines between elements that should render separately
  - Example: Add blank line between `**Date**: ...` and `**Purpose**: ...` so they render on separate lines
- **Lists**: Use consistent spacing and indentation
- **Code blocks**: Use triple backticks with language identifiers
- **Tables**: Follow GFM table syntax with proper alignment
- **When issues arise**: User may say "fix for GFM" or "use GFM formatting"

### Link Standards
**IMPORTANT**: All links in documentation must use relative paths.

#### Link Rules
- **Use relative paths**: `../modules/backend/spec.md`
- **Never use absolute paths**: Avoid `/docs/...` or `/Users/...`
- **Navigate from current file**: Use `../` to go up directories
- **Test on GitHub**: Ensure links work on GitHub

### Examples
✅ Correct: `../team/workflow.md`
❌ Wrong: `/docs/team/workflow.md`

## Development File Organization

**This is the DEVELOPMENT version of the repository. Keep it organized:**

### .dev/ Directory Structure
```
.dev/                       # Development-only files (excluded from production sync)
├── ai/                    # ALL AI-generated documentation
│   ├── handovers/        # Session handover documents
│   ├── analysis/         # Reports and audits
│   └── [subdirectories]   # As specified above
├── scripts/               # Utility scripts, tools, helpers
│   └── *.py, *.sh        # check_links.py, sync scripts, etc.
├── temp/                 # Temporary files, work-in-progress
└── notes/                # Development notes, scratch files
```

### Rules for Development Files
- **Utility scripts** → `.dev/scripts/` (e.g., check_links.py)
- **Sync/copy scripts** → `.dev/scripts/` (e.g., copy-from-knowledge-graph-lab.sh)
- **Temporary files** → `.dev/temp/`
- **Notes/scratch** → `.dev/notes/`
- **PROJECT_DESCRIPTION.md** → `.dev/notes/` (use README.md for public description)
- **AI content** → `.dev/ai/[appropriate-subdirectory]/`

### Production Sync
The `.dev/` directory is automatically excluded when syncing to the production repository, keeping it clean and professional.

### Files That Stay in Root
- `README.md` - Main Product Wizard documentation
- `AGENTS.md` - This file (AI agent guidelines)
- `CLAUDE.md` - Claude-specific pointer to AGENTS.md
- `.gitmodules` - Git submodule configuration for spec-kit
- `spec-kit/` - GitHub Spec Kit submodule (contains all core functionality)

## Project Overview

Product Wizard is a complete development pipeline that guides users from initial idea to deployed application. Built as an extension of GitHub's Spec Kit, it provides additional tooling and workflows for Spec-Driven Development (SDD). The platform is designed for developers at any level—from junior developers on their first project to non-technical founders with an app idea—enabling them to build working software through guided, specification-driven development.

## Project Phase & Current Status

This project is in **Initial Development Phase** - establishing Product Wizard as a standalone wrapper around Spec Kit:

**Current Architecture:**
- Core functionality: GitHub Spec Kit (Git submodule at `spec-kit/`)
- Product Wizard extensions: Future enhancements and additional tooling

**Immediate Focus:**
- Setting up project structure and AI agent guidelines
- Establishing development workflows
- Planning Product Wizard-specific enhancements beyond Spec Kit core
## Architecture Overview

Product Wizard leverages a modular architecture built on GitHub's Spec Kit foundation:

### Core Components

1. **Spec Kit (Submodule)**:
   - Python CLI tool (`specify`) for project bootstrapping
   - Multi-platform script templates (Bash & PowerShell)
   - Slash command framework for AI agents
   - Template system for specs, plans, and tasks

2. **Spec-Driven Development Workflow**:
   - `/constitution` - Project principles and guidelines
   - `/specify` - Feature specification creation
   - `/clarify` - Requirement clarification
   - `/plan` - Technical implementation planning
   - `/tasks` - Task breakdown
   - `/analyze` - Cross-artifact analysis
   - `/implement` - Execution

3. **Multi-Agent Support**:
   - Claude Code, Gemini CLI, GitHub Copilot, Cursor
   - Qwen Code, opencode, Codex CLI, Windsurf
   - Kilocode, Auggie, Roo Code

## Repository Structure

```
product-wizard/
├── spec-kit/                          # Git submodule - Spec Kit core
│   ├── src/specify_cli/              # Python CLI implementation
│   │   └── __init__.py               # Main CLI logic
│   ├── scripts/                      # Automation scripts
│   │   ├── bash/                    # Unix/Linux/macOS scripts
│   │   │   ├── common.sh            # Shared functions
│   │   │   ├── create-new-feature.sh
│   │   │   ├── setup-plan.sh
│   │   │   ├── check-prerequisites.sh
│   │   │   └── update-agent-context.sh
│   │   └── powershell/              # Windows/cross-platform scripts
│   │       ├── common.ps1
│   │       ├── create-new-feature.ps1
│   │       ├── setup-plan.ps1
│   │       ├── check-prerequisites.ps1
│   │       └── update-agent-context.ps1
│   ├── templates/                    # Core SDD templates
│   │   ├── commands/                # AI agent slash commands
│   │   │   ├── constitution.md
│   │   │   ├── specify.md
│   │   │   ├── clarify.md
│   │   │   ├── plan.md
│   │   │   ├── tasks.md
│   │   │   ├── analyze.md
│   │   │   └── implement.md
│   │   ├── spec-template.md         # Feature specification template
│   │   ├── plan-template.md         # Implementation plan template
│   │   └── tasks-template.md        # Task breakdown template
│   ├── docs/                        # Spec Kit documentation
│   │   ├── installation.md
│   │   ├── local-development.md
│   │   └── quickstart.md
│   ├── memory/                      # Project principles
│   │   └── constitution.md
│   ├── pyproject.toml               # Python package configuration
│   ├── AGENTS.md                    # Spec Kit agent guidelines
│   └── README.md                    # Spec Kit documentation
├── .dev/                            # Product Wizard workspace
│   ├── ai/                         # AI-generated documentation
│   ├── scripts/                    # Utility scripts
│   ├── temp/                       # Temporary files
│   └── notes/                      # Development notes
├── AGENTS.md                        # Product Wizard agent guidelines
├── CLAUDE.md                        # Claude-specific redirect
├── README.md                        # Product Wizard overview
└── .gitmodules                     # Submodule configuration
```

## Key Documentation

### Product Wizard Documentation
- Main overview: `README.md`
- AI agent guidelines: `AGENTS.md` (this file)
- Claude redirect: `CLAUDE.md`

### Spec Kit Documentation
- Core methodology: `spec-kit/README.md`
- Spec-Driven Development guide: `spec-kit/spec-driven.md`
- Installation: `spec-kit/docs/installation.md`
- Quickstart: `spec-kit/docs/quickstart.md`
- Local development: `spec-kit/docs/local-development.md`
- Adding new agents: `spec-kit/AGENTS.md`

### Templates
- Feature specification: `spec-kit/templates/spec-template.md`
- Implementation plan: `spec-kit/templates/plan-template.md`
- Task breakdown: `spec-kit/templates/tasks-template.md`
- Slash commands: `spec-kit/templates/commands/`

## Future Development

Planned enhancements for Product Wizard beyond Spec Kit core:

### Potential Extensions
- Enhanced AI agent integrations and tooling
- Additional project templates and workflows
- User experience improvements for non-technical users
- Integration with additional development tools
- Custom visualization and reporting features
- Domain-specific templates and workflows

## Spec Kit Workflow Integration

How the Spec-Driven Development process works:

### 1. Constitution Phase (`/constitution`)
- Establishes project principles and guidelines
- Creates `.specify/memory/constitution.md`
- Provides foundational decision-making framework

### 2. Specification Phase (`/specify`)
- Creates feature branch (e.g., `001-feature-name`)
- Runs `scripts/{bash,powershell}/create-new-feature.sh`
- Generates `specs/001-feature-name/spec.md` from template
- Captures user stories and functional requirements

### 3. Clarification Phase (`/clarify`)
- Required before planning phase
- Resolves underspecified areas
- Records answers in Clarifications section
- Reduces downstream rework

### 4. Planning Phase (`/plan`)
- Runs `scripts/{bash,powershell}/setup-plan.sh`
- Generates implementation artifacts:
  - `research.md` - Technology research
  - `data-model.md` - Data structures
  - `contracts/` - API specifications
  - `quickstart.md` - Getting started guide

### 5. Task Breakdown (`/tasks`)
- Converts plan into actionable tasks
- Creates `tasks.md` with dependencies
- Supports parallel execution markers

### 6. Analysis Phase (`/analyze`)
- Cross-artifact consistency checking
- Coverage analysis
- Validation before implementation

### 7. Implementation Phase (`/implement`)
- Executes tasks in dependency order
- Follows TDD approach from plan
- Provides progress updates

## Important Notes

### Submodule Management
- Spec Kit is included as a Git submodule at `spec-kit/`
- Always use `git clone --recurse-submodules` when cloning
- Update submodule: `git submodule update --init --recursive`
- Pull with submodules: `git pull --recurse-submodules`

### Script Execution
- Scripts exist in both Bash and PowerShell variants
- CLI auto-selects based on OS unless `--script sh|ps` specified
- Always run scripts from repository root
- Scripts use JSON output for parsing by AI agents

### AI Agent Compatibility
- Product Wizard works with 11+ AI coding assistants
- Each agent has specific directory structures (`.claude/`, `.gemini/`, etc.)
- Command formats vary by agent (Markdown, TOML)
- See `spec-kit/AGENTS.md` for adding new agent support

## Agent-Specific Instructions

### Working with Spec Kit Submodule
- **DO NOT** modify files in `spec-kit/` directly unless contributing to Spec Kit itself
- Always verify submodule status before making changes: `git submodule status`
- Product Wizard extensions should be in root directory, not in submodule
- When testing Spec Kit changes, work within `spec-kit/` directory

### Development Workflow
- Keep edits minimal and topic-scoped
- Follow all global `~/.agents/AGENTS.md` and `~/.claude/CLAUDE.md` rules
- Test slash commands with multiple AI agents when making changes
- Verify both Bash and PowerShell script variants work correctly
- Update version in `spec-kit/pyproject.toml` and `CHANGELOG.md` for Spec Kit changes

### Documentation Updates
- Product Wizard docs: Update `README.md` and `AGENTS.md`
- Spec Kit docs: Update files in `spec-kit/docs/` and `spec-kit/README.md`
- Always use relative paths in documentation links