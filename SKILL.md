---
name: markitdown
description: Convert local PDF, Word, PowerPoint, spreadsheet, and other supported files to Markdown with Microsoft's MarkItDown. Use when the user requests MarkItDown or needs structured Markdown for text analysis.
---

# MarkItDown

Use the official MarkItDown package from https://github.com/microsoft/markitdown. Find `markitdown` on PATH, or run `python -m markitdown` in a Python environment where the package is installed. If it is missing, install `markitdown[all]` in an isolated Python environment when the task authorizes setup.

Convert a local file with `markitdown input.pdf -o output.md` (or the equivalent `python -m markitdown` command). Choose the destination requested by the user; otherwise write a `.md` file beside the source. Check before overwriting an existing destination. Confirm the command succeeds, then inspect the Markdown for expected content and obvious omissions before reporting completion.

MarkItDown produces structured text for analysis, not a layout-faithful copy. Scans and embedded images may require OCR or another tool. Do not enable optional plugins or cloud services unless the user asks for them.
