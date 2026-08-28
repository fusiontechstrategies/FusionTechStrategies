# Security scanner operations

This record describes how FusionTechStrategies maintains the shared security-scanning foundation used by its public repositories. Repository-specific `SECURITY.md` files remain the correct channel for vulnerability reports.

## Ownership and change control

- FusionTechStrategies maintainers own the central workflow, repository callers, alert triage, and exception review.
- The reusable definition is `.github/workflows/reusable-security.yml` in this repository.
- Every caller uses a complete commit SHA. Floating branches and tags are not accepted for the reusable workflow.
- Central workflow changes are validated in this repository first, then adopted by consumers through small signed pull requests.
- Required scanner checks are not removed or bypassed to make a pull request green.
- Dependency updates are reviewed in small batches against the supported runtime and platform matrix.

The current reusable-workflow revision is `f64c8eb98fa6c907e013d158089ea6ab38e91ad7`.

## Live weekly schedule

All times are UTC. Pull requests and pushes to `main` also run the applicable scanner gate.

| Day and time | Repository | Semgrep policy | Companion coverage |
| --- | --- | --- | --- |
| Monday 10:47 | IDS Rule Converter | Shared ruleset | Trivy, full-history Gitleaks, Bandit, dependency audit, CodeQL, and native engine validation |
| Tuesday 08:31 | AWS GovHawk Efficiency Analyzer | Shared ruleset | Trivy, full-history Gitleaks, dependency audit, and extended CodeQL default setup |
| Tuesday 11:13 | FusionTechStrategies profile | Disabled because the repository contains documentation and workflow configuration only | Trivy, full-history Gitleaks, and Markdown validation |
| Wednesday 08:43 | Ultra-Fast Proxy Fetcher and Tester | Shared ruleset | Trivy, full-history Gitleaks, Bandit, dependency audit, and extended CodeQL default setup |
| Thursday 08:17 | Bedrock Guardrail Firewall | Automatic ruleset with the documented Python 3.7 compatibility exclusion | Trivy, full-history Gitleaks, Bandit, dependency audits, CodeQL, and adversarial tests |
| Thursday 08:53 | AWS Chaos Engineering Framework | Shared ruleset | Trivy, full-history Gitleaks, Bandit, dependency audits, and CodeQL |
| Friday 09:07 | WCAG 2.2 Site and PDF Scanner | Executable Python and validation code only | Trivy, full-history Gitleaks, Bandit, dependency audits, CodeQL, browser tests, and package validation |
| Saturday 09:19 | M365 Incident Response Console | Disabled because the shared ruleset has no PowerShell coverage | Trivy, full-history Gitleaks, PSScriptAnalyzer, Pester, and dependency smoke validation |

Windows Admin Toolkit has a validated scanner implementation in a draft pull request. Its default-branch schedule remains inactive until the separate VM and release qualification gates permit that pull request to merge.

## Exception rationale

Exceptions must be narrow, documented beside the caller, and supported by a positive replacement control.

- The profile repository does not contain application source. Semgrep is disabled; Trivy, Gitleaks, and Markdown validation remain active.
- M365 Incident Response Console is PowerShell. Semgrep is disabled; PSScriptAnalyzer and Pester provide language-aware analysis and regression coverage.
- WCAG examples include a static offline HTML accessibility fixture, not a Django template. Semgrep targets executable Python and validation code; Trivy and Gitleaks still inspect the complete repository.
- Bedrock Guardrail Firewall supports Python 3.10 and newer. Its Python 3.7 compatibility finding is excluded while all other automatic rules remain enabled.
- Windows Admin Toolkit uses tested PowerShell-focused generic rules in its draft workflow because the shared registry ruleset does not provide equivalent PowerShell coverage.

## Evidence and triage

- Semgrep, Trivy, and Gitleaks results are uploaded as SARIF when the event is trusted to write code-scanning results.
- Scanner artifacts are retained for 90 days.
- Forked pull requests receive read-only execution and do not receive a security-events write token.
- A failed required gate blocks merge until the finding or infrastructure failure is understood and resolved.
- Open code, dependency, and secret alerts are reviewed before the next release or adoption change in that repository.
- Suppressions require an applicability explanation and a compensating control. Findings are not dismissed solely to restore a green status.

## Monthly verification

On the first business day of each month, maintainers verify:

1. Every intended workflow remains enabled.
2. The latest scheduled run completed successfully, or a newly added schedule is explicitly awaiting its first run.
3. Required branch checks still include the repository aggregate and the shared scanner aggregate where live.
4. Code-scanning, Dependabot, and secret-scanning alerts are either zero or have a documented disposition.
5. Reusable workflow pins and external Action allowlists still name exact approved revisions.
6. Repository-specific exceptions still match the language, source scope, and replacement controls.

## Verification log

| Date | Result | Notes |
| --- | --- | --- |
| 2026-08-27 | Rollout baseline complete | Eight live public callers passed pull-request and exact-`main` validation with zero open alerts. First scheduled executions and the Windows Admin Toolkit default-branch activation remain to be recorded. |
