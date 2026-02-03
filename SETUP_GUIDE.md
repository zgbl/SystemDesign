# Setup Guide: Viewing & Exporting Diagrams

To ensure you have the best experience while studying System Design in this repository, the following VS Code extensions have been installed/recommended.

## 1. Viewing & Editing Diagrams (Mermaid)
- **Robust Preview (Recommended)**: `Markdown Preview Enhanced` (shd101wyy.markdown-preview-enhanced)
- **Standard Preview**: `Markdown Preview Mermaid Support` (bierner.markdown-mermaid)
- **Live Editor**: `Mermaid Editor` (tomoyukim.vscode-mermaid-editor)
- **Status**: **Installed**
- **How to use**: 
  1. Open any `.md` file containing a diagram (e.g., `04-Case-Studies/01-news-feed.md`).
  2. For **Robust Preview**: Right-click -> `Markdown Preview Enhanced: Open Preview to the Side`.
  3. For **Standard Preview**: Press `Cmd + Shift + V`.
  4. For **Live Editing**: Search `Mermaid Editor: Open Preview` in the Command Palette (`Cmd + Shift + P`).

## 2. Exporting to PDF/HTML
- **Extension**: `Markdown PDF` (yzane.markdown-pdf)
- **Status**: **Installed**
- **How to use**:
  1. Open the `.md` file you want to export.
  2. Right-click anywhere in the editor.
  3. Select `Markdown PDF: Export (pdf)`.
  4. The PDF file will be generated in the same folder.

## 3. Manual Installation (Troubleshooting)
If extensions fail to install via the Marketplace UI, you can install them manually via terminal.

### For Antigravity Users (Recommended)
Use the `agy` CLI which is specifically for your IDE:

```bash
# Install all required extensions for Antigravity
/Users/tuxy/.antigravity/antigravity/bin/agy --install-extension shd101wyy.markdown-preview-enhanced
/Users/tuxy/.antigravity/antigravity/bin/agy --install-extension bierner.markdown-mermaid
/Users/tuxy/.antigravity/antigravity/bin/agy --install-extension tomoyukim.vscode-mermaid-editor
/Users/tuxy/.antigravity/antigravity/bin/agy --install-extension bpruitt-goddard.mermaid-markdown-syntax-highlighting
/Users/tuxy/.antigravity/antigravity/bin/agy --install-extension yzane.markdown-pdf
```

### For Standard VS Code Users
```bash
code --install-extension shd101wyy.markdown-preview-enhanced
code --install-extension bierner.markdown-mermaid
code --install-extension tomoyukim.vscode-mermaid-editor
code --install-extension bpruitt-goddard.mermaid-markdown-syntax-highlighting
code --install-extension yzane.markdown-pdf
```

## 4. Alternative Local Editors (Recommended)
If you prefer a dedicated application for a more "book-like" reading experience:
- **Typora**: [typora.io](https://typora.io/) - Best minimal interface, native Mermaid support.
- **Obsidian**: [obsidian.md](https://obsidian.md/) - Great for linking knowledge and long-term storage.

---

## 5. Troubleshooting Post-mortem (Lessons Learned)

### Why it failed initially?
- **CLI Mismatch**: I was using the standard `code` command in the terminal.
- **Path Separation**: On your Mac, `code` points to the standard Visual Studio Code installation (`~/.vscode/extensions`). 
- **Environment Isolation**: You were using **Antigravity**, which is a separate IDE environment with its own extension folder (`~/.antigravity/extensions`) and its own CLI tool (`agy`).
- **Result**: The plugins were successfully "installed" by my commands, but they were placed in the wrong IDE's folder, so Antigravity couldn't see them.

### Why it works now?
- **Correct CLI**: We identified and used the Antigravity-specific CLI tool: `/Users/tuxy/.antigravity/antigravity/bin/agy`.
- **Targeted Installation**: By using `agy --install-extension`, we forced the plugins into the exact folder Antigravity uses.

### What to watch out for in the future?
- **Multiple IDEs**: If you have both VS Code and Antigravity installed, remember they don't share plugins.
- **Use `agy` for Antigravity**: For any future plugin needs (like Copilot, Themes, or Linters), always use the `agy` command or use the built-in Extensions view inside the Antigravity UI.
- **MPE vs. Standard Preview**: Always prefer **Markdown Preview Enhanced** (Cmd+K, V) for complex documents with diagrams, as it has a much more robust rendering engine.

---
*Note: If diagrams don't appear immediately after installation, please restart Antigravity.*
