# Setup Guide: Viewing & Exporting Diagrams

To ensure you have the best experience while studying System Design in this repository, the following VS Code extensions have been installed/recommended.

## 1. Viewing & Editing Diagrams (Mermaid)
- **Primary Preview**: `Markdown Preview Mermaid Support` (bierner.markdown-mermaid)
- **Live Editor**: `Mermaid Editor` (tomoyukim.vscode-mermaid-editor)
- **Status**: **Installed**
- **How to use**: 
  1. Open any `.md` file containing a diagram (e.g., `04-Case-Studies/01-news-feed.md`).
  2. For **Preview**: Press `Cmd + Shift + V`.
  3. For **Live Editing**: Search `Mermaid Editor: Open Preview` in the Command Palette (`Cmd + Shift + P`).

## 2. Exporting to PDF/HTML
- **Extension**: `Markdown PDF` (yzane.markdown-pdf)
- **Status**: **Installed**
- **How to use**:
  1. Open the `.md` file you want to export.
  2. Right-click anywhere in the editor.
  3. Select `Markdown PDF: Export (pdf)`.
  4. The PDF file will be generated in the same folder.

## 3. Manual Installation (Troubleshooting)
If extensions fail to install via the Marketplace UI, you can install them manually via terminal using the VS Code CLI:

```bash
# Install Mermaid Preview
code --install-extension bierner.markdown-mermaid

# Install Mermaid Editor
code --install-extension tomoyukim.vscode-mermaid-editor

# Install PDF Export
code --install-extension yzane.markdown-pdf
```

## 4. Alternative Local Editors (Recommended)
If you prefer a dedicated application for a more "book-like" reading experience:
- **Typora**: [typora.io](https://typora.io/) - Best minimal interface, native Mermaid support.
- **Obsidian**: [obsidian.md](https://obsidian.md/) - Great for linking knowledge and long-term storage.

---
*Note: If diagrams don't appear immediately after installation, please restart VS Code.*
