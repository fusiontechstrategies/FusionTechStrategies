<p align="center">
  <a href="https://www.fusiontsi.com/">
    <img src="https://www.fusiontsi.com/resources/img/logo.png" width="280" alt="Fusion Technology Strategies">
  </a>
</p>

# Open-source defensive security and IT operations

Fusion Technology Strategies builds practical, evidence-first tools for incident response, AI security, Windows administration, cloud resilience, accessibility, and federal cloud operations.

The projects below are designed for operators who need to understand what a tool will do, test it safely, and retain useful evidence afterward. Each repository documents its guardrails, permissions, limitations, and validation approach.

## Start here

| Project | What it helps you do | Best first step |
| --- | --- | --- |
| [M365 Incident Response Console](https://github.com/fusiontechstrategies/M365-Incident-Response-Console) | Investigate and contain Microsoft 365 incidents with guarded live actions and tamper-evident evidence | Run the offline self-test, then use a disposable lab tenant |
| [Bedrock Guardrail Firewall](https://github.com/fusiontechstrategies/Bedrock-Guardrail-Firewall) | Inspect AI traffic for PII, prompt injection, unsafe content, and grounding problems | Run the local deterministic demo before enabling optional cloud integrations |
| [Windows Admin Toolkit](https://github.com/fusiontechstrategies/Windows-Admin-Toolkit) | Operate twenty guarded local and remote Windows administration workflows | Download the latest signed release and verify it before execution |

## More tools

- [WCAG 2.2 Site & PDF Scanner](https://github.com/fusiontechstrategies/WCAG-2.2-Site-PDF-Scanner): audit websites and PDFs, exercise axe-core in a real browser, and produce evidence-first remediation reports.
- [AWS Chaos Engineering Framework](https://github.com/fusiontechstrategies/AWS-Chaos-Engineering-Framework): orchestrate bounded AWS FIS experiments with GovCloud-aware safeguards, rollback, and audit evidence.
- [AWS GovHawk Efficiency Analyzer](https://github.com/fusiontechstrategies/AWS-GovHawk-Efficiency-Analyzer): surface potential waste, security blind spots, and operational risk across AWS GovCloud services.
- [Ultra-Fast Proxy Fetcher & Tester](https://github.com/fusiontechstrategies/Ultra-Fast-Proxy-Fetcher-Tester): turn volatile public proxy feeds into a bounded, security-hardened network-diagnostics report.

## Engineering principles

- **Safe before clever:** potentially disruptive actions are gated, scoped, and documented.
- **Evidence over adjectives:** projects include deterministic tests, sample outputs, and explicit limitations.
- **Auditable dependencies:** automated updates are reviewed, workflows use immutable action references, and protected branches require validation.
- **Operator ownership:** local and offline modes are available where the problem permits them; telemetry is not added to security or administration tools merely to count users.
- **Portable by design:** the primary runtime remains straightforward to inspect and move, even when optional package and integration layers are available.

## Feedback and security reports

Questions, reproducible bug reports, and implementation feedback are welcome in the relevant project. Please use each repository's `SECURITY.md` instructions for vulnerabilities instead of opening a public issue.

For consulting and mission support, visit [https://www.fusiontsi.com](https://www.fusiontsi.com) or email jeff@fusiontsi.com.
