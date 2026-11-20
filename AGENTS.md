# Engineering Standards for AI Agents & Automated Contributors (AGENTS.md)

This document establishes the binding engineering guidelines for any **Autonomous Agent**, **LLM-assisted developer**, or **Automated CI/CD Workflow** submitting issues, pull requests, or code reviews to our repositories.

---

## 🧭 Core Principles

1. **Human Ownership & Accountability**:
   Automated agents and AI models do not hold legal or technical accountability. The human author whose credentials push the code or open the PR assumes **full responsibility** for the correctness, performance, security, and maintenance of the changes.

2. **Transparent Disclosure**:
   In accordance with open source best practices, contributors must explicitly disclose the involvement of AI agents or LLMs in the PR description:
   ```markdown
   ### 🤖 AI Assistance Disclosure
   - Tools used: [e.g., Claude Code, Cursor, Copilot, Custom Agent]
   - Human verification: Fully reviewed, locally compiled, and all unit tests passed.
   ```

3. **Zero AI Slop & Anti-Hallucination Policy**:
   PRs containing any of the following will be **immediately closed without review, marked as spam, and may result in a contributor block**:
   * Hallucinated dependencies, APIs, or standard library methods that do not exist.
   * "Plumbing without water": empty boilerplate files, dummy implementations, or unneeded scaffolding.
   * Unrequested refactoring of working code without functional or performance justification.
   * Broken builds, compiler warnings, or failing tests.
   * Repetitive, generic AI apologies or circular explanations in discussion threads.

---

## 🧪 Verification & Evidence Requirement

Every PR submitted with AI assistance **must include verifiable evidence of local execution**:

* **Compilation**: Zero compilation errors and zero compiler warnings.
* **Test Suite**: Output or confirmation that the test suite passed locally:
  - Rust: `cargo test --all`
  - Python: `pytest`
  - Java: `mvn test` or `./gradlew test`
  - TypeScript/Node: `npm test` or `pnpm test`
* **Formatting & Linting**: Clean formatting matching repository standards:
  - Rust: `cargo fmt --check` and `cargo clippy -- -D warnings`
  - Python: `ruff check` and `ruff format --check`
* **Performance / Benchmarks**: If claiming performance improvements, attach reproducible benchmark output.

---

## 🚫 Forbidden AI Behaviors

* **Unsolicited Mass PRs**: Automated bots opening batch PRs across multiple repositories without maintainer pre-approval.
* **Automated Issue Scraping**: Opening generic "I noticed your repo could use X" issues without actionable, deeply grounded engineering context.
* **Review Spam**: Posting automated LLM code reviews on PRs unless specifically invited by the repository maintainers.
* **Ignoring Codebase Conventions**: Re-inventing architectural patterns already established in the repository.

---

## 🏛️ Code of Conduct Compliance

All interactions generated or facilitated by AI tools must strictly adhere to our [Code of Conduct](CODE_OF_CONDUCT.md). Hostile, entitled, or automated spam responses will lead to immediate repository-level and organization-level blocking.
