# Gemini API docs extension for Gemini CLI

This extension provides documentation support for building with the Gemini API
on the Gemini CLI or other MCP-enabled tools.

## Gemini CLI installation

You can clone the repository directly into the Gemini CLI extensions directory. Choose between a global installation (available to your user everywhere) or a local installation (for the current workspace).

### Global Installation
```bash
mkdir -p ~/.gemini/extensions
git clone https://github.com/markmcd/gemini-docs-ext.git ~/.gemini/extensions/gemini-docs-ext
```

### Workspace Installation
```bash
mkdir -p ./.gemini/extensions
git clone https://github.com/markmcd/gemini-docs-ext.git ./.gemini/extensions/gemini-docs-ext
```

Gemini CLI will automatically load the extension on startup.

## Other tools

You can adapt this extension to provide context for other tools or APIs by following these steps:

1.  **Create a system `.md` file:**
    Copy the contents of `GEMINI.md` to your tool's system instructions, e.g.
    `CLAUDE.md` or `CONTEXT.md`.

2.  **Add the MCP servers:**
    [`gemini-extension.json`](gemini-extension.json) contains a fairly standard MCP configuration. You may be able to copy the `mcpServers` block directly into your tool's MCP configuration.


    ```json
    {
      "mcpServers": {
        "gemini-docs-mcp": {
          "command": "uvx",
          "args": [
            "--from",
            "mcpdoc",
            "mcpdoc",
            "--urls",
            "GeminiApiDocs:https://ai.google.dev/gemini-api/docs/llms.txt",
            "GeminiApiReference:https://ai.google.dev/api/llms.txt",
            "--transport",
            "stdio"
          ]
        }
      }
    }
    ```

