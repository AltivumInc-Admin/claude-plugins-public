# Altivum Claude Code Plugins

Public **Claude Code plugin marketplace** from [Altivum Inc.](https://altivum.io) —
open workflow tooling for the community. Marketplace name: **`altivum`**.

## Install

```bash
claude plugin marketplace add AltivumInc-Admin/claude-plugins-public
claude plugin install altivum-feature-dev-pipeline@altivum
```

Update later by re-running `claude plugin install` (or `claude plugin update`) after a new release.

## Plugins

| Plugin | Version | What it does |
|--------|---------|--------------|
| [`altivum-feature-dev-pipeline`](plugins/altivum-feature-dev-pipeline) | 0.2.0 | A full feature workflow: `/ship` orchestrates **eval → plan → execute → deploy** with approval gates between phases. Includes `deploy-validator` & `security-reviewer` subagents and a blocking pre-deploy gate. |

### altivum-feature-dev-pipeline highlights
- **`/altivum-feature-dev-pipeline:ship <goal>`** — runs the whole pipeline, pausing for your approval between phases.
- Phase commands also run standalone: `:eval`, `:plan`, `:execute`, `:deploy`.
- **`security-reviewer`** subagent reviews diffs for auth/IDOR, injection, secrets, IAM least-privilege, and more.
- **`deploy-validator`** subagent verifies a deploy end-to-end (status, live endpoints, migrated data).
- A **blocking pre-deploy gate** stops production-mutating commands until explicitly approved.

See the plugin's [README](plugins/altivum-feature-dev-pipeline/README.md) for full details.

## Repo layout

```
claude-plugins-public/
├── .claude-plugin/marketplace.json
└── plugins/
    └── altivum-feature-dev-pipeline/
        ├── .claude-plugin/plugin.json
        └── commands/  agents/  hooks/  README.md
```

## License

[MIT](LICENSE) © Altivum Inc.

---

*This is the public distribution repo. Plugins are developed in a private repo and released
here once vetted.*
