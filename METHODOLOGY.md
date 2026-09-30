# Methodology

Every advisory in this repository follows the same evidence-first process so
that the research is independently reviewable and reproducible.

## 1. Intake

Candidate CVEs are drawn from public vulnerability data (NVD, vendor and
ecosystem advisories, and the CISA KEV catalog). Each candidate keeps its
authoritative identifiers: CVE ID, CWE, CVSS, GHSA, and vendor references.

## 2. Isolated laboratory

Reproduction is performed only against controlled **affected** and **patched**
references inside an isolated environment with no route to the public Internet.
The two controls run side by side so that a behavioral difference can be
attributed to the fix.

## 3. Safe validation

Validation demonstrates the **minimum behavior** needed to establish the
vulnerability primitive. It does not weaponize the issue:

- no command execution or remote code execution is attempted;
- no public or third-party system is contacted or tested;
- validators never accept arbitrary Internet targets.

## 4. Evidence

Each advisory retains the artifacts that support its claims: a
`validation-summary.json`, sanitized source-comparison diffs where available,
and a `SHA256SUMS` file. A per-directory `MANIFEST.json` records the SHA-256
digest and size of every retained file.

## 5. Release standard

Every advisory is released together with its retained validation evidence and
its integrity manifest. Every conclusion is limited to behavior directly
supported by the retained evidence and the cited upstream references;
upstream-reported impact that was not independently reproduced is labeled as
such.

## Scope

This repository is for **defensive** security research: validation, review,
detection, and reproducibility. Weaponized exploit publication and
public-target testing are out of scope.
