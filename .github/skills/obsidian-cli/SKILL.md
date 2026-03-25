---
name: obsidian-cli
description: Interact with Obsidian vaults using the Obsidian CLI to read, create, search, and manage notes, tasks, properties, and more. Also supports plugin and theme development with commands to reload plugins, run JavaScript, capture errors, take screenshots, and inspect the DOM. Use when the user asks to interact with their Obsidian vault, manage notes, search vault content, perform vault operations from the command line, or develop and debug Obsidian plugins and themes.
---

# Obsidian CLI

For GitHub Copilot in this repo, do **not** invoke the `obsidian` binary directly. On this machine it is the AppImage launcher and opens the GUI. Use the local wrapper with `python3 ./.github/scripts/obsidian-cli` for terminal-safe vault operations.

Use `python3 ./.github/scripts/obsidian-cli` to interact with the vault from the command line. It operates on markdown files in the current working directory, or on a specific vault passed with `--vault`.

## Command reference

Run `python3 ./.github/scripts/obsidian-cli --help` to see the supported commands in this repo.

## Syntax

**Parameters** take a value with `=`. Quote values with spaces:

```bash
python3 ./.github/scripts/obsidian-cli create --name "My Note" --content "Hello world"
```

**Flags** use standard POSIX CLI style:

```bash
python3 ./.github/scripts/obsidian-cli create --name "My Note" --silent --overwrite
```

For multiline content use `\n` for newline and `\t` for tab.

## File targeting

Many commands accept `--file` or `--path` to target a file.

- `--file <name>` -- resolves like a wikilink using the note name or filename
- `--path <path>` -- exact path from vault root, e.g. `folder/note.md`

## Vault targeting

Commands target the current working directory by default. Use `--vault <path>` to target a specific vault:

```bash
python3 ./.github/scripts/obsidian-cli --vault "$PWD" search --query "test"
```

## Common patterns

```bash
python3 ./.github/scripts/obsidian-cli read --file "My Note"
python3 ./.github/scripts/obsidian-cli create --name "New Note" --content "# Hello" --silent
python3 ./.github/scripts/obsidian-cli append --file "My Note" --content "New line"
python3 ./.github/scripts/obsidian-cli search --query "search term" --limit 10
python3 ./.github/scripts/obsidian-cli property:set --name "status" --value "done" --file "My Note"
python3 ./.github/scripts/obsidian-cli backlinks --file "My Note"
```

Current wrapper scope: `read`, `create`, `append`, `search`, `property:set`, and `backlinks`.

Prefer direct file edits for complex note generation. Use the wrapper when the user explicitly asks for terminal commands or CLI-based workflows.

## Plugin development

### Develop/test cycle

For plugin and theme development, the local wrapper is **not** a replacement for Obsidian's live developer tooling. If you need runtime app inspection, use the GUI app intentionally and treat it as a separate workflow from terminal-safe vault editing.

After making code changes to a plugin or theme, follow this workflow only if you have a real Obsidian developer CLI available in your environment:

1. **Reload** the plugin to pick up changes:
   ```bash
   obsidian plugin:reload id=my-plugin
   ```
2. **Check for errors** -- if errors appear, fix and repeat from step 1:
   ```bash
   obsidian dev:errors
   ```
3. **Verify visually** with a screenshot or DOM inspection:
   ```bash
   obsidian dev:screenshot path=screenshot.png
   obsidian dev:dom selector=".workspace-leaf" text
   ```
4. **Check console output** for warnings or unexpected logs:
   ```bash
   obsidian dev:console level=error
   ```

### Additional developer commands

Run JavaScript in the app context:

```bash
obsidian eval code="app.vault.getFiles().length"
```

Inspect CSS values:

```bash
obsidian dev:css selector=".workspace-leaf" prop=background-color
```

Toggle mobile emulation:

```bash
obsidian dev:mobile on
```

Run `obsidian help` to see additional developer commands including CDP and debugger controls.

## Environment note

In this workspace, `obsidian` currently resolves to the AppImage launcher at `/home/jepabon/.local/bin/obsidian`. That command opens the GUI and should not be used for automated CLI note operations.