# TCU Jurisprudência

### TCU Jurisprudência for Claude, ChatGPT and AI agents

Public search of the Brazilian Federal Court of Accounts (TCU) case law: keyword search across rulings (acórdãos), selected jurisprudence (enunciados) and binding summaries (súmulas), with summary, highlighted snippets, rapporteur and links to full text. Also lists the latest rulings. Platform-hosted, no credentials.

- 📊 **2 tools**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `TCU Jurisprudência`, URL `https://api.mcp.ai/p_tcu`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=tcu&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF90Y3UifQ==)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=tcu&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_tcu%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_tcu
```

---

## 2 tools

| Tool | Description |
|---|---|
| `tcu_buscar` | Busca textual (por palavra-chave) na jurisprudência do TCU. |
| `tcu_acordaos_recentes` | Lista os acórdãos mais recentes do TCU (dados abertos oficiais), paginado, sem palavra-chave: sumário, relator, colegiado, data da sessão e links. |

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_tcu` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
