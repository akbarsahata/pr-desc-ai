# inference-worker

This is a Cloudflare Worker that accepts a list of Git commit messages and returns a generated Pull Request (PR) description using an LLM (e.g., OpenAI GPT).

It serves as the core inference backend for tools like the CLI (`git-parser`) or VSCode extension (`vscode-extension`).

---

## 📡 API Endpoint

**`POST /generate`**

### ➔ Request Body

```json
{
  "commits": [
    "fix login redirect issue",
    "add validation to user input",
    "refactor session management"
  ]
}
```

### ➔ Response

```json
{
  "description": "This PR addresses login redirection issues, adds user input validation, and improves session management by refactoring core logic."
}
```

---

## ✅ TODO

* [ ] Scaffold Worker with `wrangler`
* [ ] Add `/generate` POST endpoint using `Hono` or vanilla Worker
* [ ] Write prompt template for PR description generation
* [ ] Call OpenAI (or any LLM) via API with the provided commits
* [ ] Use Wrangler secrets for API key management
* [ ] Add error handling and logging
* [ ] Add rate-limiting or basic auth if public
* [ ] Deploy to Cloudflare and test with CLI

---

## 🧪 Local Development

```bash
npm install
wrangler dev
```

Use a tool like `curl`, Postman, or your CLI to test:

```bash
curl -X POST http://localhost:8787/generate \
  -H "Content-Type: application/json" \
  -d '{"commits": ["fix bug A", "add test case", "update docs"]}'
```

---

## 🚀 Deployment

```bash
wrangler publish
```

Make sure you've set your OpenAI key:

```bash
wrangler secret put OPENAI_API_KEY
```

---

## 📦 Suggested Stack

| Purpose  | Tool                                                                |
| -------- | ------------------------------------------------------------------- |
| Routing  | [Hono.js](https://hono.dev/)                                        |
| LLM      | [OpenAI API](https://platform.openai.com/docs)                      |
| Hosting  | [Cloudflare Workers](https://developers.cloudflare.com/workers/)    |
| Dev Tool | [Wrangler CLI](https://developers.cloudflare.com/workers/wrangler/) |

---

## 📁 Folder Structure

```
inference-worker/
├── src/
│   └── index.ts            # Entry point for Worker
│   └── generateDescription.ts  # LLM integration logic
├── wrangler.toml
├── package.json
└── README.md
```

---

## 📄 License

MIT
