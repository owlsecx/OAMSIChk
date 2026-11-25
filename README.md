# 🦉 OAMSIChk

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-Security-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0-cyan?style=flat-square"/>
</p>

> **OAMSIChk** — part of the OwlSec Toolkit.

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OAMSIChk is an offline blue-team tool for catching defense-evasion code in PowerShell and other scripts. It decodes -EncodedCommand payloads layer by layer and flags AMSI bypasses, ETW patching and Defender-tampering markers. It also extracts IOCs and generates Sigma rules. It only reads data and never runs scripts or patches AMSI/ETW.

---

## ✨ Features

- Script scanner that decodes PowerShell -EncodedCommand layers and flags AMSI, ETW and Defender-evasion markers
- File and directory marker scanner with IOC extraction
- Blob decoder: Shannon entropy grading plus base64, base64-UTF16, hex, ROT13 and single-byte XOR recovery
- Searchable catalog of evasion techniques mapped to MITRE ATT&CK
- Sigma-rule generator and ATT&CK coverage summary
- Reports in TXT / JSON / Markdown / CSV / SARIF; exits with code 3 on CRITICAL/HIGH findings

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OAMSIChk                                   # interactive menu
./OAMSIChk --script suspicious.ps1
./OAMSIChk --scan ./scripts
./OAMSIChk --decode "<base64 blob>"
./OAMSIChk --sigma > amsi_rules.yml
```

Run `./OAMSIChk --help` for the full list of options.

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, the Go toolchain version it was built with, and every bundled
  component with its exact version and license. Feed it to Grype, Trivy or
  Dependency-Track to audit our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
