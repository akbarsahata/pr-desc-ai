# vscode-extension

This is a Visual Studio Code extension that provides a command to generate a Pull Request (PR) description using recent Git commit messages from the current workspace.

It sends the commits to the `inference-worker` and returns a natural language PR description for developer convenience.

---

## 💡 Features

* VSCode command: `Generate PR Description`
* Reads Git history from the active workspace
* Sends commit messages to a Cloudflare Worker
* Displays the PR description in a popup or inserts it into an active editor
* Configurable endpoint and API key support

---

## ✅ TODO

* [ ] Scaffold extension using `yo code`
* [ ] Register `generatePrDescription` command in `package.json`
* [ ] Read Git commits using `simple-git` or `child_process`
* [ ] Call the `inference-worker` endpoint
* [ ] Show result in VSCode InputBox or paste into current editor
* [ ] Add settings for API endpoint and token
* [ ] Handle error states and display notifications
* [ ] Test extension and package it for release

---

## 🚪 Usage

1. Open a Git project folder in VSCode
2. Open the command palette (`Ctrl+Shift+P`)
3. Run: `Generate PR Description`
4. View or insert the generated PR message

---

## 📚 Configuration

Add the following settings to your `settings.json`:

```json
{
  "prGen.apiEndpoint": "https://your-cloudflare-worker.com/generate",
  "prGen.apiKey": "your-api-key-if-needed"
}
```

---

## 🤖 Extension Dev

To run the extension in development mode:

```bash
npm install
code .
```

Then press `F5` to launch a new Extension Development Host.

---

## 📁 Folder Structure

```
vscode-extension/
├── src/
│   └── extension.ts          # Entry point for command logic
│   └── api.ts                # Handles HTTP request to inference-worker
│   └── git.ts                # Reads commit messages from workspace
├── media/                    # (optional) for Webview assets
├── package.json              # VSCode extension manifest
└── README.md
```

---

## 🚀 Recommended Packages

| Purpose              | Package                         |
| -------------------- | ------------------------------- |
| Git access           | `simple-git` or `child_process` |
| HTTP requests        | `node-fetch` or `axios`         |
| Clipboard (optional) | `clipboardy`                    |
| VSCode API           | `vscode`                        |

---

## 📄 License

MIT
