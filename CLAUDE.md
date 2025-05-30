📘 CLAUDE.md

# Cross-Repo PR Install Action

This repository contains the **`cross-repo-pr-install` composite action**, designed to install dependencies from cross-repo PRs based on markers in pull request comments.

## Purpose
When developing across multiple repositories, we often need to test a PR against changes from other repos. This action:
- Scans the PR comments for a `marker` (e.g., `requires_cli_pr`).
- If found, checks out the corresponding PR branch from the specified repository.
- Installs dependencies from the checked-out code (`source_install`).
- If no marker is found, installs a fallback (`default_install`).

---

🚀 **Ready to roll**—you can now:  
🔹 Clone or create a repo with this action structure.  
🔹 Start local iteration with **Claude-code**.  
🔹 Use the sample workflow to test cross-repo PR installs.

💬 Shall I:  
- 🏗️ Package this into a **zip or repo template** to drop into your project?  
- 📖 Expand with **matrix and error handling features**?  
Or are you all set to take it from here?

You said:
reformat the claude.md without headers
ChatGPT said:

Here’s the CLAUDE.md reformatted as requested, with the same content but no section headers:

This repository contains the nect composite action, designed to install dependencies from cross-repo PRs based on markers in pull request comments.

When developing across multiple repositories, we often need to test a PR against changes from other repos. This action scans the PR comments for a marker (e.g., requires_cli_pr). If found, it checks out the corresponding PR branch from the specified repository. It then installs dependencies from the checked-out code using source_install. If no marker is found, it installs a fallback using default_install.

To use this action in your workflow:

uses: asmacdo/nect@main
with:
  name: dandi-cli
  marker: requires_cli_pr
  default_install: pip install "dandi[test] @ git+https://github.com/dandi/dandi-cli"
  source_install: pip install -e .[test]

In your PR description or comments, include:

requires_cli_pr: https://github.com/dandi/dandi-cli/pull/123

or:

requires_cli_pr: 123

(The second form assumes the same repository if only a PR number is provided.)

For local development, use claude-code or a similar tool to extend the action for new repositories, refine install logic, and test against PRs with markers.

TODO:

Matrix support for multiple repos.

Error handling and reporting.

Optional auto-detection of PR numbers from markers without full URLs.
