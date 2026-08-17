# GitHub Repository Settings Guide

This document outlines the recommended GitHub repository settings to configure after creating a new repository from this template.

> **Important Distinction:**
> - **In-Repository Files (Automated):** Workflows (`.github/workflows/ci.yml`), PR/Issue templates, `.editorconfig`, and `.gitignore` are tracked in code and take effect immediately.
> - **GitHub Platform Settings (Manual Configuration):** Branch protection, rulesets, template repository flags, and merge automation are repository-level settings managed through the GitHub UI or API.

---

## 1. Branch Protection & Rulesets (`main`)

To prevent accidental direct pushes and guarantee that code meets quality standards before reaching production, configure branch protection for the `main` branch.

### Recommended Steps (GitHub Rulesets)

1. Navigate to **Settings** > **Rules** > **Rulesets** (or **Settings** > **Branches** > **Branch protection rules**).
2. Click **New ruleset** (or **Add branch protection rule**).
3. **Ruleset Name:** `Protect main`
4. **Enforcement Status:** `Active`
5. **Target Branches:** Select **Default branch** (or add target pattern `main`).

### Recommended Rule Configurations

| Setting | Recommended Value | Purpose |
| :--- | :--- | :--- |
| **Restrict creations** | Enabled | Prevents direct creation of unauthorized branches matching rule |
| **Restrict deletions** | Enabled | Prevents accidental deletion of the `main` branch |
| **Block force pushes** | Enabled | Prevents history rewrites on `main` |
| **Require a pull request before merging** | Enabled | Enforces all changes to go through PR review |
| ↳ *Required approvals* | `1` | Ensures peer code review before merge |
| ↳ *Dismiss stale pull request approvals on new commits* | Enabled | Re-verifies approval when code changes |
| **Require status checks to pass** | Enabled | Blocks merging until CI checks succeed |
| ↳ *Require branches to be up to date before merging* | Enabled | Ensures testing against latest `main` commit |
| ↳ *Status checks required* | `Validate Branch & PR Conventions`<br>`Security & Secret Scan`<br>`Lint, Test & Build` | Validates naming, security, and tests |

---

## 2. Pull Request & Merge Automation

Under **Settings** > **General** > **Pull Requests**:

- **Allow merge commits:** Optional (based on team preference)
- **Allow squash merging:** Recommended (keeps `main` history clean and linear)
- **Allow rebase merging:** Optional
- **Automatically delete head branches:** **Enabled** (keeps the repository free of stale feature branches after PR merge)

---

## 3. Converting to a Template Repository

To allow other team members to create new repositories using the **"Use this template"** button:

1. Navigate to **Settings** > **General**.
2. Under the **Repository name** section, check the box labeled **"Template repository"**.
3. Save changes.

---

## 4. Security & Analysis Settings

Navigate to **Settings** > **Code security and analysis**:

- **Dependency graph:** Enabled
- **Dependabot alerts:** Enabled
- **Dependabot security updates:** Enabled
- **Secret scanning:** Enabled (where plan allows)
- **Push protection:** Enabled (blocks commits containing known secret token formats before they reach GitHub)

---

## Summary Matrix: Automated vs Repository Settings

```
+------------------------------------+---------------------------------------+
| Automated via Repository Files     | Configured via GitHub Repository UI   |
+------------------------------------+---------------------------------------+
| Branch name validation in CI       | Disabling direct push to main         |
| PR title validation in CI          | Enforcing required PR approvals       |
| Secret scanning action in CI       | Blocking force pushes to main         |
| Test, Lint, and Build execution    | Auto-deleting merged head branches    |
| PR & Issue template presentation   | Designating repository as a Template  |
| Consistent editor formatting rules | Organization secret scanning settings |
+------------------------------------+---------------------------------------+
```
