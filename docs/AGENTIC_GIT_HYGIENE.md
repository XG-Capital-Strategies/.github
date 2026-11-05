# XGCS Agentic Git Governance v1.0

Scope: all XG-Capital-Strategies repositories, developers, agents and automation. Status: DRAFT pending review. Text files are policy, not GitHub ruleset enforcement.

## Primary principle: resume rather than proliferate
Before opening a branch, inspect the current task issue, existing PRs, branch heads, integration base, dependency handoffs and any active worktree. Continue an existing workstream and branch rather than create a fresh branch for a new conversation, model, session or retry. One active implementation branch per issue per repository by default. Genuine parallel work requires a new independently scoped sub-issue, bounded non-overlapping file ownership, named owner and documented stacked PR dependencies.

## Task admission
Every new branch must reference an issue with accountable human owner, working agent, clear scope, expected base and base SHA, exact active head SHA, touched paths, risks, validation profile, dependencies and rollback plan. Recommended branch names: feature/gh-NNN-scope, fix/gh-NNN-scope, docs/gh-NNN-scope, test/gh-NNN-scope, research/gh-NNN-scope. Other conventional prefixes can be approved. Historical branches are grandfathered; no rename churn. No tokens, sensitive material or customer identifiers in branch names.

Agents should track a single active lease record (agent identity, issue, branch, head SHA, checkpoint, expiry and coordination owner). A lease coordinates agents, not a privilege grant. Default limit: four active implementation issues per agent per repository. Exceptions must be owner-scoped and time-bounded. Unknown ownership must be reported, not guessed.

## PR admission and status
One main PR per active issue branch; stacked PRs require explicit base/dependency links. PR description must record issue, owner, existing branch research, expected base, source-pinned tests/receipts, risks, protected data, side effects, rollback and retirement disposition. Draft PRs are encouraged until accepted. A new agent must adopt existing issues/PRs, not fork final/final2/reconciled-v3 duplicates. Source-tested is never a synonym for staged or live. Do not force-push anyone else's active branch or silently change PR base.

## Branch conservation
No branch deletion on age, name, lack of PR or presumed supersession. For proposed retirement, capture exact branch head SHA, merge-base and ahead/behind relative to a known main SHA, unique commits, touched files, PR disposition, ongoing worktrees/runners/queued jobs, deployment/rollback dependencies and an explicit KEEP/ACTIVE/PORT/SUBSUMED/REVIEW classification. Unknown means KEEP. Deleting or closing work needs a separately authorized exact-SHA list and auditable receipt. Preserve production branches, historical protected evidence and all legitimate live research.

## Enforcement architecture
- Organization .github repository: default contribution/PR templates and policy; these do not force agent or API behavior.
- Repo-local AGENTS.md: must explicitly adopt policy before its agents rely on it.
- GitHub Ops: extend the EXISTING branch conservation program, issue #3159, draft PR #3255; do not start a competing janitor. A future allowlisted server-side create_branch admission guard needs authenticated issue/actor checks, regression tests and source-pinned supervisor adoption.
- Mission Control: reads organization inventory; identifies duplicate workstreams and out-of-lease branches; reports proposed reconciliation; never gains blanket repo prune/force-push/merge tools.
- GitHub rulesets/branch protection: prefer PR-based merges, no force update and branch restrictions where plan and permissions allow; 403/permission/plan failures must be recorded as NOT ENFORCED.
- Prioritize cost-controlled, bounded WhiteGIR validation instead of GitHub-hosted Actions; do not add a new always-on controller.

## Read-only weekly reconciliation
Report timestamped branch count, duplicate issue heads, active/stale PR status, source SHAs, owner/lease gaps, unique commits not contained, deployment/rollback dependencies and recommended human dispositions. No automatic deletion or public exposure of private repository details.

## Adoption truth states
POLICY_DRAFT -> POLICY_ADOPTED -> REPO_GUARDED -> GITHUB_ENFORCED (only with independently checked GitHub server-side status). Existing source holds, review gates, incident controls and repo-specific protections take precedence.

Canonical reconciliation: https://github.com/XG-Capital-Strategies/kairos-github-ops/issues/3159
Organization adoption: https://github.com/XG-Capital-Strategies/.github/issues/2
