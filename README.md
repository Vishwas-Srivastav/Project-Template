# Project Engineering Template

> A lightweight, reusable GitHub Project Engineering Template with proactive 4-tier guardrails, automated CI checks, conventional commits, and professional engineering defaults.

---

## Overview & Purpose

**Project Engineering Template** provides a robust, clean, and production-ready starting point for new software projects without enterprise bureaucracy or over-engineering.

It enforces engineering quality through **active guardrails** (local Git hooks + CI validation + platform rulesets) to keep development fast, reliable, and secure.

---

## Key Features

- **<FEATURE_1>:** <Description of feature 1>
- **<FEATURE_2>:** <Description of feature 2>
- **<FEATURE_3>:** <Description of feature 3>
- **Engineering Guardrails:** Automated local Git hooks, CI branch & commit validation, secret hygiene scanning, and UI standards enforcement.

---

## Technology Stack

- **Primary Language / Runtime:** `<TECHNOLOGY>` (e.g., Node.js 20+ / Python 3.11+ / Go 1.22+)
- **Framework:** `<FRAMEWORK>` (e.g., Express / FastAPI / Next.js / Standard Library)
- **Testing:** `<TEST_FRAMEWORK>` (e.g., Jest / Pytest / Go testing)
- **CI/CD & Guardrails:** GitHub Actions, Gitleaks, Shell-based Guardrail Suite
- **Code Standards:** EditorConfig, Conventional Commits

---

## Prerequisites

Ensure you have the following installed locally:

- Git (v2.30+)
- `<RUNTIME_TOOLCHAIN>` (e.g., Node.js v20+ / Python v3.11+ / Go 1.22+)
- `<PACKAGE_MANAGER>` (e.g., npm / pip / pnpm)

---

## Quick Start & Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Vishwas-Srivastav/Project-Template.git
   cd Project-Template
   ```

2. **Initialize Local Engineering Guardrails:**
   ```bash
   ./scripts/setup-guardrails.sh
   ```
   *Enables pre-commit, commit-msg, and pre-push hooks to catch issues before push.*

3. **Set up local environment variables:**
   ```bash
   cp .env.example .env
   ```
   *Edit `.env` with your local development settings.*

4. **Install dependencies:**
   ```bash
   <INSTALL_COMMAND>
   # Example: npm install  OR  pip install -r requirements.txt  OR  go mod download
   ```

5. **Run the development server / application:**
   ```bash
   <DEV_START_COMMAND>
   # Example: npm run dev  OR  python main.py  OR  go run main.go
   ```

---

## Development Workflow & Guardrail Commands

| Task | Command | Description |
| :--- | :--- | :--- |
| **Check Guardrails** | `./scripts/check-guardrails.sh` | Runs full suite: branch, commits, secrets, UI & code quality |
| **Start Dev Server** | `<DEV_COMMAND>` | Starts local application in hot-reload mode |
| **Run Linting** | `<LINT_COMMAND>` | Validates code formatting and static analysis rules |
| **Run Tests** | `<TEST_COMMAND>` | Executes automated unit and integration tests |
| **Build Production** | `<BUILD_COMMAND>` | Compiles and packages production artifacts |

---

## Engineering Guardrails & Standards

Our development process is protected by a 4-tier guardrail system. Read [docs/GUARDRAILS.md](file:///Users/vishwassrivastav/Desktop/Work/Project%20Template/docs/GUARDRAILS.md) for full architecture.

- **Branch Naming:** Format branches as `<PROJECT_INITIALS>-<NUMBER>` (e.g., `WSAI-01` for WebscribeAI, `UC-01` for Unclutter, `ML-01` for Memory Lens, or `feature/WSAI-01`).
- **Commit Convention:** Use [Conventional Commits](https://www.conventionalcommits.org/) (e.g., `feat:`, `fix:`, `docs:`, `chore:`).
- **PR Standards:** All changes must go through a pull request with completed testing notes. Direct push to `main` is disabled.
- **UI Standards:** Follow [docs/UI_GUIDELINES.md](file:///Users/vishwassrivastav/Desktop/Work/Project%20Template/docs/UI_GUIDELINES.md). Interfaces must use SVG icons (no emoji icons), accessible typography, and clean layouts.
- **Security:** Never commit credentials. Read [SECURITY.md](file:///Users/vishwassrivastav/Desktop/Work/Project%20Template/SECURITY.md).

For full details, review [CONTRIBUTING.md](file:///Users/vishwassrivastav/Desktop/Work/Project%20Template/CONTRIBUTING.md).

---

## Template Setup for New Projects

When using this repository as a template for a new project:

1. **Click "Use this template"** > **"Create a new repository"** in GitHub.
2. **Configure GitHub Branch Protection** on `main` following [docs/GITHUB_SETTINGS.md](file:///Users/vishwassrivastav/Desktop/Work/Project%20Template/docs/GITHUB_SETTINGS.md).
3. **Run `./scripts/setup-guardrails.sh`** on your local machine.
4. **Replace placeholders** in `README.md`, `LICENSE`, `.env.example`, and `.github/workflows/ci.yml` (`<PROJECT_NAME>`, `<TECHNOLOGY>`, `<INSTALL_COMMAND>`, etc.).
5. **Update CI steps** in `.github/workflows/ci.yml` to run your language-specific lint/test/build scripts.

---

## License

Distributed under the MIT License. See [LICENSE](file:///Users/vishwassrivastav/Desktop/Work/Project%20Template/LICENSE) for more information.
