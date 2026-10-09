# OfficeDocs

[Website](https://officedocs.io) · [Download](https://officedocs.io/download) · [Documentation](https://officedocs.io/docs) · [Pricing](https://officedocs.io/pricing) · [Deutsch](README.de.md) · [日本語](README.ja.md)

OfficeDocs is a self-hosted document collaboration suite for real-time docs, writers, spreadsheets, presentations, forms and tables, with configurable AI agents built into every product, deployed into a private cloud you control.

This repository contains release information and installation documentation. It is not the application source-code repository. Product use is subject to the applicable product licence; free use does not imply an open-source licence.

## Start an evaluation

1. Read the [installation guide](docs/INSTALL.md) and prepare a dedicated server for the selected architecture.
2. Download the **amd64** or **arm64** ZIP from the [download page](https://officedocs.io/download). Both packages include the installer, the product release package and installation instructions. No website registration is required to read the documentation or download a package.
3. Compare its SHA256 with [SHA256SUMS](SHA256SUMS), extract it, and follow the installer checks.
4. Request a licence from [support.global@shimo.im](mailto:support.global@shimo.im). The free perpetual plan covers up to **5 users**. The Team plan is **$5 per user per month**, with **20% off** annual billing. See [pricing](https://officedocs.io/pricing) for the current offer.
5. Before putting real work on the system, verify sign-in, two-person editing, save and reopen, access permissions, backup and restore on your deployment. Download integrity is not proof that a deployment has passed these checks.

## Current release

- Product release: `co1.8.20260830.3884-drive-release`
- Installer: `v1.8.1-rc12-global`
- Architectures: `amd64` (x86_64) and `arm64` (aarch64)
- Packaged setup: online, All-in-One single node
- Packaged guide: Ubuntu 24.04 LTS, 16 CPU cores, 32 GB RAM and 100 GB SSD; internet access is required to download packages and images. These are the packaged evaluation instructions, not a production capacity benchmark. Use the [resource planning guide](https://officedocs.io/docs/deployment/system-requirements) for longer-term storage and cluster planning.
- [Machine-readable release manifest](releases/co1.8.20260830.3884-drive-release.json)
- [OfficeDocs release archive](https://github.com/officedocs/officedocs/releases/tag/co1.8.20260830.3884-drive-release)

OfficeDocs is an independent international brand using the same underlying product as ShimoDocs. The initial OfficeDocs distribution reuses the approved ShimoDocs release unchanged. File names, signatures, technical commands and some interface labels retain their original names. This public repository provides the OfficeDocs release assets; the website download page also provides verified downloads, and the manifest records their provenance. Installation packages are release assets, not files in Git history.

## Documentation and support

- [Quick start](https://officedocs.io/docs/deployment/getting-started/quick-start)
- [System requirements](https://officedocs.io/docs/deployment/system-requirements)
- [Deployment documentation](https://officedocs.io/docs)
- [Talk through your deployment](https://officedocs.io/contact-sales)

The current support and licence address is **support.global@shimo.im**. Never include passwords, private keys or licence contents in a public issue.
