<p align="center">
  <img src="banner.svg" alt="Koru — deception-first runtime defense for the AI era" width="100%">
</p>

<h1 align="center">Koru</h1>

<p align="center">
  <strong>Deception-first runtime defense for the AI era.</strong><br>
  Catch AI attack agents and hijacked agents when they touch credentials — <em>before</em> the credential is used.
</p>

<p align="center">
  <a href="https://github.com/korusecurity/koru/actions/workflows/ci.yml"><img src="https://github.com/korusecurity/koru/actions/workflows/ci.yml/badge.svg" alt="CI"></a>
  <a href="https://github.com/korusecurity/koru/releases"><img src="https://img.shields.io/github/v/release/korusecurity/koru" alt="Release"></a>
  <a href="https://github.com/korusecurity/koru/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-Apache--2.0-blue.svg" alt="License"></a>
</p>

## What is Koru?

Koru is an open-source, deception-based runtime security tool for Linux servers. It plants
**honeytokens** — decoy credentials, fake SSH keys, decoy `.env` files, fake MCP configs and
AI-bait notes — and detects access to them **at the kernel level with eBPF**, before any
credential is used. It then traces the accessing process lineage and reports whether the reader
looks like a **human, an AI agent, or a possibly hijacked AI agent**.

## Why Koru

- **Access before use.** Alerts when a decoy file is *read* on the host — not when a fake key is
  used somewhere else. Kernel-level `open()` detection, sub-second.
- **AI-agent attribution.** Process lineage tells apart a human, a coding agent (Claude Code,
  Cursor, Codex), an MCP server chain, or a container.
- **Local-first and open.** Apache-2.0, no telemetry, no cloud dependency. Data stays on your box.

## Repositories

- **[koru](https://github.com/korusecurity/koru)** — the eBPF honeytoken access-detection sensor for Linux.

## Quick start

```bash
git clone https://github.com/korusecurity/koru.git
cd koru
cargo build --release
sudo ./target/release/koru tuzak kur   # plant decoys
```

## Security · Contributing · Contact

- **Security policy:** [SECURITY.md](https://github.com/korusecurity/koru/blob/main/SECURITY.md)
- **Contributing:** [CONTRIBUTING.md](https://github.com/korusecurity/koru/blob/main/CONTRIBUTING.md)
- **Report a vulnerability:** via the repo's Security tab ("Report a vulnerability")

<sub>Koru is an open-source project by Korusec. Built for the AI-agent era.</sub>
