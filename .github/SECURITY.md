# Security Policy

Core Companion is designed for resilient, off-grid tactical communication and civil defense. We take the security, cryptographic integrity, and privacy of our users seriously.

---

## Supported Versions

Security fixes are released for the following versions:

| Version Line | Supported | Notes |
|:---|:---:|:---|
| Current Stable (`v0.7.x`, `v0.8.x`) | ✅ Yes | Actively maintained |
| Release Candidates (`-rcN-*`) | ✅ Yes | Pre-release testing builds |
| Older releases (`< v0.7.0`) | ❌ No | Please upgrade to the latest stable or RC build |

---

## Reporting a Vulnerability

> [!WARNING]
> **DO NOT report security vulnerabilities through public GitHub issues, discussions, or pull requests.**
> Public disclosure before a fix is ready endangers users relying on Core Companion in emergency and off-grid conditions.

### Preferred Method: GitHub Private Vulnerability Reporting

Please submit vulnerabilities directly and privately through GitHub's Coordinated Vulnerability Disclosure:
👉 **[Report a Security Vulnerability Privately](https://github.com/RO-Mesh/core-companion/security/advisories/new)**

### What to Include in Your Report

To help us investigate and patch the vulnerability as quickly as possible, please provide:
1. **Description**: Clear description of the vulnerability and its potential impact.
2. **Component Affected**: Specific module (e.g., Secure Vault storage, BLE frame parser, App Update URL verification, cryptographic key management).
3. **Proof of Concept / Steps to Reproduce**: Minimal steps, test scripts, or radio payload examples demonstrating the issue.
4. **Environment**: App edition (Full vs Client), version tag, Android OS version, and radio hardware if applicable.

---

## Security Practices in Core Companion

Core Companion adheres to a defense-in-depth security model informed by the `harperaa/secure-claude-skills` standard:
* **No Secret Leakage**: No private signing keys, keystores, or tokens are ever embedded in source code or public repositories.
* **Strict Download Allowlists**: In-app updates verify HTTPS origin against an explicit domain allowlist and validate binary checksums (`SHA256SUMS.txt`).
* **Path Traversal Protection**: All user input, preset files, and update file names are strictly sanitized against directory traversal attacks.
* **Obfuscation**: Production AOT binaries are compiled with `--obfuscate --split-debug-info`, and debug symbols are kept strictly private.
* **Zero Tracking / Zero Telemetry**: Core Companion collects zero personal data, zero analytics, and runs 100% offline.
