# Security Policy

## Supported Scope

Security reports are accepted for:

- Active repositories in the HDCS ecosystem
- CI/CD and dependency configuration
- Documentation that could expose sensitive operational details

## Reporting a Vulnerability

Please do **not** open public issues for sensitive vulnerabilities.

Report privately with:

- affected repository/path
- impact summary
- reproduction steps
- suggested remediation (if available)

Contact: **khalid.hago82@gmail.com**  
Subject: `HDCS Security Report`

## Response Targets

- Initial acknowledgment: within 5 business days
- Triage and severity classification: as soon as reproducible
- Remediation timeline: based on severity and operational impact

## Security Baseline

- No hardcoded secrets in tracked files
- Dependency updates through automated tooling where practical
- Principle of least privilege in automation
- Explicit separation of flight-critical and non-flight-critical software concerns
