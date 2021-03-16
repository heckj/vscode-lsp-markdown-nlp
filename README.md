# vscode-lsp-markdown-nlp

LSP service and client for VSCode that works against markdown files

Sourced from [VSCode LSP Documentation](https://code.visualstudio.com/api/language-extensions/language-server-extension-guide)
and the [lsp example code](https://github.com/microsoft/vscode-extension-samples/tree/master/lsp-sample).

Heavily documented sample code for <https://code.visualstudio.com/api/language-extensions/language-server-extension-guide>

DEVNOTE:

- could use <https://github.com/NaturalNode/natural#pos-tagger> for POS tagging to identify use of passive voice
  
## Functionality

This Language Server works for plain text file. It has the following language features:

- Completions
- Diagnostics regenerated on each file change or configuration change

It also includes an End-to-End test.

## Structure

```bash
.
├── client // Language Client
│   ├── src
│   │   ├── test // End to End tests for Language Client / Server
│   │   └── extension.ts // Language Client entry point
├── package.json // The extension manifest.
└── server // Language Server
    └── src
        └── server.ts // Language Server entry point
```

## Running the Sample

- Run `npm install` in this folder. This installs all necessary npm modules in both the client and server folder
- Open VS Code on this folder.
- Press Ctrl+Shift+B to compile the client and server.
- Switch to the Debug viewlet.
- Select `Launch Client` from the drop down.
- Run the launch config.
- If you want to debug the server as well use the launch configuration `Attach to Server`
- In the [Extension Development Host] instance of VSCode, open a document in 'plain text' language mode.
  - Type `j` or `t` to see `Javascript` and `TypeScript` completion.
  - Enter text content such as `AAA aaa BBB`. The extension will emit diagnostics for all words in all-uppercase.
