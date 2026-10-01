# Detections

Candidate detection content derived from the advisories in this repository.

- **`sigma/`** — one Sigma rule per advisory, marked `status: experimental`.
- **`nuclei/`** — one non-invasive version/fingerprint detection template per
  advisory, for confirming whether an **authorized** target runs an affected
  release. Templates detect only; they do not exploit.

These rules and templates are **starting points, not validated production
content**. Field names, log sources, request paths, and matchers must be adapted
to your own telemetry/targets, and each should be tested for coverage and false
positives before use. Run Nuclei templates only against systems you are
authorized to test. Detection guidance for each issue is also documented in its
advisory.
