# Security Policy

## Supported Versions

This repository hosts interactive Katacoda learning scenarios (Markdown + shell
scripts). The scenarios are documentation, not a deployed software package, so
"supported" means *the latest commit on the default branch* is what the
OpenSSF Scorecard, Dependabot, and `actions/dependency-review-action` monitor.

| Branch  | Supported |
| ------- | --------- |
| `main`  | :white_check_mark: |
| older   | :x:                |

## Reporting a Vulnerability

If you discover a security issue in any scenario content (e.g. an example
command that suggests an unsafe practice) or in the repository's automation
(`.github/workflows/*`), please report it privately so we can fix it before
public disclosure.

- **Email:** `security@akax.dev` (PGP key on request)
- **GitHub:** open a private security advisory at
  <https://github.com/joseguzman1337/katacoda-scenarios/security/advisories/new>
- **Response target:** initial acknowledgement within 72 hours; triage and
  fix or documented decline within 14 days for confirmed issues.

## Safe Harbor

We will not pursue legal action against researchers who:

- Make a good-faith effort to avoid privacy violations, data destruction, or
  service disruption.
- Only interact with accounts they own or have explicit permission to access.
- Stop testing immediately and contact us if they encounter user data.
- Give us a reasonable window to address the issue before public disclosure
  (coordinated disclosure, 90 days default).

We will recognise reporters in the fix commit (or anonymously, on request).

## Scope

In scope:

- Workflow files under `.github/workflows/`
- Scorecard / Dependabot / dependency-review configuration
- Markdown scenarios that recommend unsafe shell commands

Out of scope:

- Third-party Katacoda infrastructure (report to <https://katacoda.com>)
- The upstream `katacoda/scenario-example` template
- Issues already tracked in a public advisory

## Automated Security Tooling

This repository uses the following automated controls (see
`docs/security` and the workflow files for details):

- `actions/dependency-review-action` on every pull request
- OpenSSF Scorecard on every push to `main` (`.github/workflows/scorecards.yml`)
- Dependabot alerts + automated security fixes (enabled on the repository)
- Branch protection on `main` (`enforce_admins=true`,
  `require_code_owner_reviews=true`, `required_linear_history=true`,
  `required_conversation_resolution=true`)
