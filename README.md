<p align="center">
  <a href="https://www.fusiontsi.com/">
    <img src="https://www.fusiontsi.com/resources/img/logo.png" width="280" alt="Fusion Technology Strategies">
  </a>
</p>

# Open-source defensive security and IT operations

Fusion Technology Strategies builds practical, evidence-first tools for incident response, AI security, Windows administration, cloud resilience, accessibility, and federal cloud operations.

The projects below are designed for operators who need to understand what a tool will do, test it safely, and retain useful evidence afterward. Each repository documents its guardrails, permissions, limitations, and validation approach.

## Pick a starting point

| If you work with... | Start here | See it before you use it |
| --- | --- | --- |
| Windows endpoints and servers | [Windows Admin Toolkit](https://github.com/fusiontechstrategies/Windows-Admin-Toolkit) | [Preview the guarded automation flow](https://github.com/fusiontechstrategies/Windows-Admin-Toolkit#guarded-automation-lifecycle) or [download the signed release](https://github.com/fusiontechstrategies/Windows-Admin-Toolkit/releases/latest) |
| Microsoft 365 incidents | [M365 Incident Response Console](https://github.com/fusiontechstrategies/M365-Incident-Response-Console) | [Open a sanitized case report](https://github.com/fusiontechstrategies/M365-Incident-Response-Console/blob/main/examples/sanitized-case-report.md) or [review the latest release](https://github.com/fusiontechstrategies/M365-Incident-Response-Console/releases/latest) |
| Website and PDF accessibility | [WCAG 2.2 Site and PDF Scanner](https://github.com/fusiontechstrategies/WCAG-2.2-Site-PDF-Scanner) | [View the synthetic report](https://github.com/fusiontechstrategies/WCAG-2.2-Site-PDF-Scanner/blob/main/examples/sample-report/report-preview.png) and [run the five-minute walkthrough](https://github.com/fusiontechstrategies/WCAG-2.2-Site-PDF-Scanner#five-minute-local-walkthrough) |
| Generative AI applications | [Bedrock Guardrail Firewall](https://github.com/fusiontechstrategies/Bedrock-Guardrail-Firewall) | [Try the offline evaluation](https://github.com/fusiontechstrategies/Bedrock-Guardrail-Firewall#try-it-offline-in-60-seconds) and [review the sanitized demo](https://github.com/fusiontechstrategies/Bedrock-Guardrail-Firewall#reproducible-sanitized-demo) |

## More tools

- [AWS Chaos Engineering Framework](https://github.com/fusiontechstrategies/AWS-Chaos-Engineering-Framework): orchestrate bounded AWS FIS experiments with GovCloud-aware safeguards, rollback, and audit evidence.
- [AWS GovHawk Efficiency Analyzer](https://github.com/fusiontechstrategies/AWS-GovHawk-Efficiency-Analyzer): surface potential waste, security blind spots, and operational risk across AWS GovCloud services.
- [Ultra-Fast Proxy Fetcher & Tester](https://github.com/fusiontechstrategies/Ultra-Fast-Proxy-Fetcher-Tester): turn volatile public proxy feeds into a bounded, security-hardened network-diagnostics report.
- [IDS Rule Converter](https://github.com/fusiontechstrategies/IDS-Rule-Converter): convert and validate Snort and Suricata rules while preserving unsupported or ambiguous semantics for operator review.

## Engineering principles

- **Safe before clever:** potentially disruptive actions are gated, scoped, and documented.
- **Evidence over adjectives:** projects include deterministic tests, sample outputs, and explicit limitations.
- **Auditable dependencies:** automated updates are reviewed, workflows use immutable action references, and protected branches require validation.
- **Operator ownership:** local and offline modes are available where the problem permits them; telemetry is not added to security or administration tools merely to count users.
- **Portable by design:** the primary runtime remains straightforward to inspect and move, even when optional package and integration layers are available.

The [security scanner operations record](SECURITY-OPERATIONS.md) documents portfolio schedules, ownership, exceptions, evidence retention, and the verification process.

## Feedback and security reports

Questions, reproducible bug reports, and implementation feedback are welcome in the relevant project. Please use each repository's `SECURITY.md` instructions for vulnerabilities instead of opening a public issue.

For consulting and mission support, visit [https://www.fusiontsi.com](https://www.fusiontsi.com) or email jeff@fusiontsi.com.
