# pr-desc-ai ✨🤖

**pr-desc-ai** is a developer-first tool to auto-generate GitHub Pull Request descriptions using recent commit messages and LLMs like OpenAI GPT.

This monorepo includes:

- ⚙️ `git-parser` – CLI tool to parse commits and request PR description
- ☁️ `inference-worker` – Cloudflare Worker that generates descriptions via LLM
- 🧩 `vscode-extension` – Optional VSCode extension to trigger it directly from your IDE

## 🧠 Why?

Writing good PR descriptions is tedious. This tool saves time, improves communication, and ensures consistency across your team's contributions.

## 🏗 Tech Stack

- TypeScript (monorepo)
- Cloudflare Workers + Wrangler
- OpenAI (or HuggingFace/Ollama)
- VSCode Extension API
- Git CLI integration
