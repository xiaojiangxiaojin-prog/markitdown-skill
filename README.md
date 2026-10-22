# MarkItDown skill for AI agents

A portable agent skill for converting local files to Markdown with [Microsoft MarkItDown](https://github.com/microsoft/markitdown). This repository contains instructions for agents; it does not bundle or modify MarkItDown. It is an independent community integration, not a Microsoft project.

## Install

1. Install Python 3.10–3.14 and the official converter in your preferred Python environment:

   ```bash
   python -m pip install "markitdown[all]"
   ```

   The `all` extra enables optional format dependencies. For fewer dependencies, install only the extras you need, as described in the [upstream README](https://github.com/microsoft/markitdown#installation).

2. Place this repository's [`SKILL.md`](SKILL.md) in your agent's global skills directory as `markitdown/SKILL.md`. For Codex, the destination is `~/.codex/skills/markitdown/SKILL.md` (Windows: `%USERPROFILE%\.codex\skills\markitdown\SKILL.md`). Other agents that support the Agent Skills format can use the same file in their documented skills directory.

3. Start a new agent session and ask it to use `markitdown` on a local file. Agents without skill discovery can read `SKILL.md` directly or reference it from their own instruction file.

## Use

```bash
markitdown input.pdf -o output.md
```

If the executable is not on `PATH`, use the Python environment where it was installed:

```bash
python -m markitdown input.pdf -o output.md
```

The agent checks that conversion succeeded and reviews the resulting Markdown before reporting completion. MarkItDown targets structured text analysis; scanned pages and embedded images may need separate OCR. Optional plugins and cloud services are not enabled by this skill.

## License and source

The original converter is maintained by [Microsoft](https://github.com/microsoft/markitdown) under its own license. This skill's instructions are released under [MIT](LICENSE).
