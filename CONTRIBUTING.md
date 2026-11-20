# Contributing Guidelines & Engineering Standards

Thank you for your interest in contributing to our repositories! To ensure code quality, maintainability, and architectural sanity, we maintain strict engineering and review standards.

Please read this document carefully before opening an issue or submitting a pull request.

---

## 🏛️ 1. Code of Conduct & Respect

All participants are required to adhere to our [Code of Conduct](CODE_OF_CONDUCT.md). 
We expect all interactions in issues, pull requests, and discussions to remain professional, constructive, and technically grounded. 
**Insults, demanding language, ad-hominem attacks, or toxic entitlement will result in immediate thread locking and account blocking.**

---

## 📋 2. Issue-First Workflow (Mandatory)

Before writing code or opening a Pull Request:

1. **Check Existing Issues**: Make sure the bug or feature hasn't already been reported or rejected.
2. **Open an Issue First**:
   - For **Bug Reports**: Provide complete reproduction steps, exact operating system/environment details, clean stack traces/logs, and expected vs actual behavior.
   - For **Feature Requests / Architectural Changes**: Clearly articulate the problem, use-case, and proposed design before implementing anything.
3. **Wait for Maintainer Approval**: Do not invest hours in massive refactors, dependency additions, or paradigm changes without maintainer sign-off. **Unsolicited PRs rewriting core architecture will be closed without review.**

---

## 🛠️ 3. Pull Request Requirements

To be considered for review, every Pull Request must meet the following criteria:

* **Single Responsibility**: One PR should address one specific issue or feature. Avoid combining unrelated bug fixes, formatting tweaks, or new features in a single diff.
* **Keep Diffs Reviewable**: Strive for minimal, focused diffs. Massive PRs (+1,000s of lines without prior agreement) create high review latency.
* **Pass All Quality Gates**:
  - Code must compile/build with zero errors and zero new warnings.
  - Existing tests must pass, and new tests must be added to cover your changes.
  - Code must adhere to the repository's linter and formatter settings (e.g., `cargo fmt` / `clippy` for Rust, `ruff` / `black` for Python, `mvn test` / spotless for Java).
* **No Unnecessary Dependencies**: Every external dependency introduces maintenance overhead and attack surface. Justify any new third-party dependency in the PR description.
* **Clean Git History**: Commits must have clear, descriptive imperative messages (e.g., `feat(core): add cache invalidation hook`, `fix(cli): resolve race condition in file watcher`).

---

## 🤖 4. AI-Assisted and Agent Contributions

We welcome developers using modern engineering tools, including AI code assistants, **provided they are guided by human competence and rigorous verification**.

However, we enforce a strict **Zero-Slop Policy**:
* If an AI was used to assist in the PR, it **must be explicitly disclosed**.
* You, the human contributor, assume **100% responsibility** for every single line of code submitted.
* PRs containing hallucinated APIs, non-compiling boilerplate, fake methods, or unchecked AI output will be closed immediately as spam.
* Detailed requirements for automated tools and AI agents are documented in [AGENTS.md](AGENTS.md).

---

## 🚀 5. Development & Review Process

1. Fork the repository and create your feature branch from the repository's default branch (`git checkout -b feat/my-improvement`).
2. Implement your changes following existing codebase conventions and design patterns.
3. Verify your changes locally with automated tests and builds.
4. Submit your Pull Request referencing the approved issue (`Closes #123`).
5. Maintainers will review your PR and provide technical feedback. Please address comments promptly and professionally.
