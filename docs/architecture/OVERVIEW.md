# Docs directory overview

## Scope

This file is the domain index for `docs/` — a complete file map of every guide and domain folder (install, API, clients, CLI, compression, architecture deep-dives, env, proxy, deployment, providers, testing, fallback, logs, desktop, troubleshooting, glossary) plus the translation guide. It lists where each document lives and how the domain folders relate.

For getting started as a user, see [en/README.md](../en/README.md) (English entry point); for the product overview, see the root [README](../../README.md).

## File index

| File | Description |
| --- | --- |
| [en/](../en/OVERVIEW.md) | **English** — all domains (api with 00-high-level-index, cli, clients, desktop, env, fallback, glossary, install, logs, proxy, providers, testing, troubleshooting). |
| [zh-cn/](../zh-cn/OVERVIEW.md) | **简体中文** — Chinese translations, one file per English page with the same name (mirrors `en/` exactly; `en/` is authoritative where the two disagree). |
| [policy/TRANSLATION.md](../policy/TRANSLATION.md) | Translating: rules for locale files, the validator, and the settled terminology table. |
| [operations/CHANGELOG.md](../operations/CHANGELOG.md) | Revision history for the `docs/` tree, derived from git commits. |
| [research/](../research/) | Provider free-access survey notes (Router9/Septor, Lucidity/Airforce/DreamPrompting/Waterfall/Logfare). |
| [site/index.html](../site/index.html) | Static website asset (not a doc): redirect page to freellmapi.co. |
| [site/success.html](../site/success.html) | Static website asset (not a doc): post-install success page. |
| [site/install.sh](../site/install.sh) | Unix Docker bootstrap script served by the project website. |
| [site/install.ps1](../site/install.ps1) | PowerShell bootstrap script served by the project website. |
| [site/api.md](../site/api.md), [site/architecture.md](../site/architecture.md), [site/install.md](../site/install.md) | "Moved" redirect stubs kept from earlier docs reorganizations. |

> `site/` holds the static website assets and legacy-path redirect stubs shipped with the docs directory, not markdown documentation.
