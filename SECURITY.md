# Security Policy

Security is a first-class design constraint across every Orlixys product.
If you've found something that shouldn't be there, this document explains
how to tell us about it without putting users at risk.

---

## Reporting a Vulnerability

**Do not open public GitHub issues for security concerns.**
Public issues expose users before a fix is shipped.

Send a detailed report by email to:

**`support@orlixys.com`**

Use the subject line: `[SECURITY] <product> — <short summary>`

A good report includes:

- The affected product, version (or release tag), and platform
- A clear description of the vulnerability and its impact
- Steps to reproduce — ideally a minimal proof of concept
- Any logs, payloads, screenshots or recordings that help
- Your assessment of severity (informational, low, medium, high, critical)
- Suggested remediation (optional, always appreciated)

If the issue is sensitive enough to need encryption, mention it in your
first message and a PGP key will be provided.

---

## Scope

Security reports are welcome for any of the following:

| Product | Repository |
|---|---|
| Orlixys Optimizer (source) | https://github.com/Orlixys/Orlixys-Optimizer-Source |
| Orlixys Optimizer (releases) | https://github.com/Orlixys/Orlixys-Optimizer-Releases |
| Orbit | proprietary, contact `support@orlixys.com` |
| Photon | proprietary, contact `support@orlixys.com` |
| Organisation infrastructure | https://github.com/Orlixys |

### Always in scope

- Privilege escalation, code execution, or sandbox escape in any product
- Network interception or man-in-the-middle attacks against the
  auto-update channel (Velopack / GitHub Releases)
- Bypasses of the anonymous hardware ID — anything that can be used to
  re-identify a user across machines or sessions
- Driver vulnerabilities introduced by Optimizer's optional sensor
  monitoring (LibreHardwareMonitor / WinRing0)
- Improper handling of administrator elevation
- Supply-chain compromise of the build or release pipeline

### Out of scope

- Vulnerabilities in third-party dependencies that have not been
  integrated into the products above
- Social engineering, physical attacks, or anything requiring access to
  developer machines
- Denial of service that requires more resources than a normal user
  would have
- Reports generated only from automated scanners without manual
  validation
- Issues affecting end-of-life versions (only the latest minor release
  receives security updates)

---

## Supported Versions

Only the latest minor release of each product receives security updates.
Users running outdated versions should update via the in-app auto-updater
(Optimizer) or contact support (Orbit, Photon).

| Product | Supported |
|---|---|
| Orlixys Optimizer | Latest minor release |
| Orbit | Latest minor release |
| Photon | Latest minor release |

---

## Response Times

| Stage | Target |
|---|---|
| Initial acknowledgment | 72 hours |
| Triage and severity assessment | 7 days |
| Fix or mitigation plan | Depends on severity |
| Public disclosure | Coordinated with the reporter |

Orlixys is currently a one-person operation. Response times are
best-effort, not contractual.

---

## Recognition

Researchers who report valid vulnerabilities through this process and
practice responsible disclosure will be credited (with permission) in:

- Release notes for the affected product
- The acknowledgments section of the affected repository

There is no paid bug bounty program at this time. If a report leads
directly to a real fix that protects users, it will be acknowledged
publicly with a link to your work or handle, if you'd like.

---

## A Note On Product Design

Orlixys products are built with privacy as a first-class constraint:

- No telemetry, no analytics SDKs, no remote logging by default
- Anonymous SHA-256 hardware IDs only — nothing identifiable is collected
- Sensor monitoring (which requires a kernel driver) is **opt-in** and
  disabled by default, due to known CVE-2020-14979 in the underlying
  driver
- Administrator elevation is **on demand**, never persistent
- Optimizer ships with the manifest set to `asInvoker`, not
  `requireAdministrator`

Reports that argue Orlixys *should* collect telemetry, *should* require
permanent admin, or *should* persist tracking data are not
vulnerabilities — they are feature requests, and the answer is no.

Thanks for keeping these products honest.
