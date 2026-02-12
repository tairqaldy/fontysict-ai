# Codex Custom Slash Commands (S2 SDE)

These prompts replicate the Cursor slash commands for use with **Codex CLI**.

## Setup for Codex CLI

Codex reads custom prompts from `~/.codex/prompts/` (your user home). To use these:

### Option 1: Copy (recommended)

```powershell
# Windows PowerShell - run from repo root
$dest = "$env:USERPROFILE\.codex\prompts"
New-Item -ItemType Directory -Force -Path $dest
Copy-Item -Path ".codex\prompts\*.md" -Destination $dest -Exclude "README.md"
```

### Option 2: Symlink (advanced)

```powershell
# Windows - run as admin or enable Developer Mode for symlinks
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.codex"
New-Item -ItemType SymbolicLink -Path "$env:USERPROFILE\.codex\prompts" -Target "$PWD\.codex\prompts"
```

## Usage

After setup, restart Codex (CLI or IDE extension). Then:

1. Type `/` in the Codex chat input
2. Type `prompts:` or the prompt name (e.g. `prompts:question`)
3. Add your arguments: `prompts:question what is SOLID?`

| Command | Description |
|---------|--------------|
| `prompts:question` | Ask about project, program, schedule |
| `prompts:review` | Code review against SDE standards |
| `prompts:help-assignment` | Help with assignments |
| `prompts:explain-concept` | Explain a concept |
| `prompts:plan-iteration` | Plan portfolio iteration work |
| `prompts:help-research` | Research document (DOT Framework) |
| `prompts:check-learning-outcomes` | Check LO coverage |
| `prompts:review-portfolio` | Portfolio review & guidance |

## Note on VS Code Codex Extension

The Codex VS Code extension has **limited support** for custom slash commands. These prompts work fully in the **Codex CLI**. If you use the extension, check [GitHub issues](https://github.com/openai/codex/issues) for slash command support updates.
