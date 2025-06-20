# git-parser

This is a Node.js CLI tool that extracts recent Git commit messages and sends them to the `inference-worker` to generate a Pull Request (PR) description.

## 🛠 Features

- Parses commit messages using `git log`
- Sends commit history to the inference API
- Copies the generated PR description to clipboard or prints to console

## ✅ TODO

- [ ] Set up `tsconfig.json` and build script
- [ ] Implement `git log` parser (e.g., `origin/main..HEAD`)
- [ ] Call Cloudflare Worker API with commit list
- [ ] Handle clipboard or stdout output
- [ ] Add CLI flags for `--since`, `--to`, `--range`
- [ ] Add error handling and retries
- [ ] Bundle CLI with `pkg` or `npx` support

## 🧪 Example

```bash
npx ts-node src/index.ts --since origin/main