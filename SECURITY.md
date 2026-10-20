# Security Policy

Security is part of every Orlixys delivery, not an extra phase. This
document explains how to report a security issue in any Orlixys project
on GitHub without putting users at risk.

For **orlixys.com** and **status.orlixys.com**, the full policy (scope,
what you may test and what is not allowed) is at
[orlixys.com/security](https://orlixys.com/security/), also published as
[`security.txt`](https://orlixys.com/.well-known/security.txt).

---

## Reporting a Vulnerability

**Do not open public GitHub issues for security concerns.**
Public issues expose users before a fix is shipped.

Send a detailed report by email, in Portuguese or English, to:

**`contact@orlixys.com`**

Use the subject line: `[SECURITY] <project> — <short summary>`

A good report includes:

- The affected project, version (or release tag), and platform
- What the issue lets someone do
- Steps to reproduce — ideally a minimal proof of concept
- Any logs, payloads, screenshots or recordings that help
- The date, time and source IP of your tests, when they touched an
  Orlixys service, so we can tell them apart from an attack

If your proof involves other people's data, describe what you saw
without sending the data.

---

## Scope

Security reports are welcome for any of the following:

| Project | Where |
|---|---|
| Orlixys Optimizer (releases) | https://github.com/Orlixys/Orlixys-Optimizer-Releases |
| Orlixys Optimizer (source) | https://github.com/Orlixys/Orlixys-Optimizer-Source |
| Other Orlixys software | listed at https://orlixys.com/software/ |
| orlixys.com and status.orlixys.com | policy at https://orlixys.com/security/ |
| Organisation on GitHub | https://github.com/Orlixys |

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

- Third-party services such as Cloudflare and GitHub: report issues in
  them to each one's own security channel
- Vulnerabilities in third-party dependencies that have not been
  integrated into the products above
- Denial of service and load testing, or any test that takes down or
  slows down an Orlixys service
- Social engineering, phishing, physical attacks, or anything requiring
  access to developer machines
- Reports generated only from automated scanners without manual
  validation
- Versions that no longer receive updates (only the latest release of
  each product does)

---

## Supported Versions

Only the latest release of each product receives security updates.
Optimizer updates itself through its built-in auto-updater.

| Product | Supported |
|---|---|
| Orlixys Optimizer | Latest release |
| Other Orlixys software | Latest release, once available |

---

## After You Report

We confirm receipt within **5 business days**. Once we have looked into
it, we tell you whether the issue is confirmed and when it is fixed. If
you do not hear back within that time, write again.

We ask you to wait for the fix before disclosing the issue, for up to
**90 days** from your report. If the fix needs more time, we explain why
and agree on a new date with you.

---

## Recognition

Orlixys has no bug bounty program and does not pay for reports. With
your permission, researchers who report valid vulnerabilities through
this process are credited in the release notes of the affected product.

Asking for payment in exchange for not disclosing an issue is not
good-faith research.

---

## A Note On Optimizer's Design

Orlixys Optimizer is built with privacy as a first-class constraint:

- No telemetry, no analytics SDKs, no remote logging by default
- Anonymous SHA-256 hardware IDs only — nothing identifiable is collected
- Sensor monitoring (which requires a kernel driver) is **opt-in** and
  disabled by default, due to known CVE-2020-14979 in the underlying
  driver
- Administrator elevation is **on demand**, never persistent
- Optimizer ships with the manifest set to `asInvoker`, not
  `requireAdministrator`

Reports that argue Optimizer *should* collect telemetry, *should* require
permanent admin, or *should* persist tracking data are not
vulnerabilities — they are feature requests, and the answer is no.

Thanks for keeping these products honest.
