# Nuclei detection templates

Non-invasive detection templates for the advisories in this repository. They confirm whether a target is affected; **they do not exploit**. Run them only against systems you are authorized to test.

## Install Nuclei

```bash
# Go toolchain:
go install -v github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest
# or Docker:
docker pull projectdiscovery/nuclei:latest
```

## Run one template against an authorized target

```bash
nuclei -u https://target.example -t CVE-2026-59971.yaml
# Docker:
docker run --rm -v $PWD:/t projectdiscovery/nuclei -u https://target.example -t /t/CVE-2026-59971.yaml
```

## Reproduce in an isolated lab

Several CVEs ship a self-contained lab under [`../labs/`](../labs/) that brings up a vulnerable and a fixed target with `docker compose`, so you can confirm a template flags the vulnerable one and clears the fixed one before using it in the field.

## Detectability matrix

| Advisory | Template | Status | Lab |
|---|---|---|---|
| [CVE-2026-92161](../../CVE-2026-92161/) | `CVE-2026-92161.yaml` | experimental scaffold — tune before use | — |
| [CVE-2026-87902](../../CVE-2026-87902/) | `CVE-2026-87902.yaml` | verified (lab-reproducible) | [lab](../labs/CVE-2026-87902/) |
| [CVE-2026-82377](../../CVE-2026-82377/) | `CVE-2026-82377.yaml` | experimental scaffold — tune before use | — |
| [CVE-2026-77244](../../CVE-2026-77244/) | `CVE-2026-77244.yaml` | experimental scaffold — tune before use | — |
| [CVE-2026-59971](../../CVE-2026-59971/) | `CVE-2026-59971.yaml` | verified (lab-reproducible) | [lab](../labs/CVE-2026-59971/) |
| [CVE-2026-53710](../../CVE-2026-53710/) | `CVE-2026-53710.yaml` | experimental scaffold — tune before use | — |

- **verified (lab-reproducible)** — tuned and confirmed against a local lab target.
- **experimental scaffold** — correct metadata and a starting request/matcher; tune the path and matchers (or switch to version fingerprinting) for your target before relying on it.
- Some issues (e.g. identity/OAuth trust bugs) are not reliably detectable over the network; for those, use the advisory's offline `poc/validate.py --version` check instead.
