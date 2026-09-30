<div align="center">

# 🛡️ Security Research

**Independent vulnerability research by [r0xd4n3t](https://github.com/r0xd4n3t)**

Evidence-backed advisories · Isolated validation · Reproducible security research

![Evidence Backed](https://img.shields.io/badge/evidence-backed-111827?style=flat-square)
![Isolated Validation](https://img.shields.io/badge/validation-isolated%20labs-0f766e?style=flat-square)
![Defensive Research](https://img.shields.io/badge/research-defensive-1d4ed8?style=flat-square)
![Integrity](https://img.shields.io/badge/integrity-SHA--256-6d28d9?style=flat-square)

</div>

---

> **Research principle**
>
> Every published advisory is tied to retained validation evidence and constrained reproducibility material. Conclusions are limited to behavior supported by the evidence.

## 🔬 Research Index

| Advisory | Summary | CWE | CVSS | KEV | Artifacts |
| :--- | :--- | :--- | :---: | :---: | :--- |
| **[CVE-2026-92161](CVE-2026-92161/)** | CVE-2026-92161: Unverified Discord email trusted by FriendsOfFlarum OAuth | CWE-345 | 9.8 (v3.1) | — | [Advisory](CVE-2026-92161/ADVISORY.md) · [Evidence](CVE-2026-92161/evidence/) · [Validator](CVE-2026-92161/poc/) |
| **[CVE-2026-87902](CVE-2026-87902/)** | CVE-2026-87902: WordPress page-template traversal and local PHP inclusion | CWE-98 | 9.2 (v4.0) | 🔴 **KEV** | [Advisory](CVE-2026-87902/ADVISORY.md) · [Evidence](CVE-2026-87902/evidence/) · [Validator](CVE-2026-87902/poc/) |
| **[CVE-2026-82377](CVE-2026-82377/)** | CVE-2026-82377: Cross-weblog missing authorization in Apache Roller XML-RPC APIs | CWE-862 | 9.9 (v3.1) | — | [Advisory](CVE-2026-82377/ADVISORY.md) · [Evidence](CVE-2026-82377/evidence/) · [Validator](CVE-2026-82377/poc/) |
| **[CVE-2026-77244](CVE-2026-77244/)** | CVE-2026-77244: Unauthenticated operator-credential fallback in MCP Atlassian | CWE-287 | 10 (v3.1) | — | [Advisory](CVE-2026-77244/ADVISORY.md) · [Evidence](CVE-2026-77244/evidence/) · [Validator](CVE-2026-77244/poc/) |
| **[CVE-2026-59971](CVE-2026-59971/)** | CVE-2026-59971: MySQL MCP Server SSE transport lacks Host validation | CWE-306 | 10 (v3.1) | — | [Advisory](CVE-2026-59971/ADVISORY.md) · [Evidence](CVE-2026-59971/evidence/) · [Validator](CVE-2026-59971/poc/) |

## 🤖 Feeds, dashboard & detections

A structured [`index.json`](index.json) lists every advisory with its CWE, CVSS, CISA KEV status, affected and fixed versions, upstream references, and evidence checksums — ready for tooling and dashboards.

- 📄 **[`index.json`](index.json)** — machine-readable feed of every advisory.
- 🏢 **[CSAF 2.0](csaf/)** — OASIS-standard advisory documents for vulnerability-management tooling.
- 📡 **[Atom feed](feed.xml)** — subscribe to new advisories.
- 🖥️ **[Web dashboard](https://r0xd4n3t.github.io/security-research/)** — searchable, filterable view of every advisory.
- 🛡️ **[Detections](detections/)** — candidate Sigma rules per advisory (experimental; validate before use).

See [`METHODOLOGY.md`](METHODOLOGY.md) for the validation model, [`SECURITY.md`](SECURITY.md) for corrections and coordinated disclosure, and [`CONTRIBUTING.md`](CONTRIBUTING.md) to get involved.

## 📊 Repository at a Glance

| | |
| :--- | :--- |
| **Published research** | **5 advisories** |
| **Validation model** | Affected and patched controls in isolated environments |
| **Evidence integrity** | SHA-256 manifests and retained validation artifacts |
| **Public PoC policy** | Constrained defensive validators or non-networked evidence verifiers |

## 🧪 Research Standard

Each published CVE package is designed to make the research independently reviewable without overstating what was reproduced.

- **Isolated validation** — testing is performed against controlled affected and patched references.
- **Evidence first** — retained artifacts support the published technical claims.
- **Reproducibility** — each package includes a manifest and integrity hashes.
- **Constrained validation** — public validators do not accept arbitrary Internet targets.
- **Defensive scope** — weaponized exploit publication and public-target testing are outside the repository scope.

## 📦 Advisory Package

```text
CVE-YYYY-NNNNN/
├── README.md
├── ADVISORY.md
├── REFERENCES.md
├── MANIFEST.json
├── images/
│   ├── cover.svg
│   └── validation.svg
├── poc/
│   ├── README.md
│   └── validate.py
└── evidence/
    ├── validation-summary.json
    └── source/
        ├── *.diff
        └── SHA256SUMS
```

## 🔐 Integrity & Reproducibility

Every published CVE directory contains a `MANIFEST.json` recording the SHA-256 digest and size of the retained public artifacts.

Where source-comparison evidence is available, sanitized unified diffs and their checksums are retained under `evidence/source/`.

## ⚠️ Scope

This repository is intended for **defensive security research, validation, review, and reproducibility**.

Published material does not imply that every impact described by an upstream advisory was independently reproduced. Refer to each advisory's validation and limitations sections for the exact research boundary.

---

<div align="center">

**[r0xd4n3t](https://github.com/r0xd4n3t) · Security Research**

<sub>Evidence over assumption.</sub>

</div>
