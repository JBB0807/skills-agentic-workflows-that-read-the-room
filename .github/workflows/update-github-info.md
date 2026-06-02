---
name: Update GitHub Info
on:
  workflow_dispatch:
permissions:
  contents: read
  pull-requests: read
tools:
  edit:
  web-fetch:
safe-outputs:
  create-pull-request:
    draft: true
    fallback-as-issue: false
network:
  allowed:
    - awesome-copilot.github.com
    - github.blog
    - github.com
---

# Update GitHub Info

Update the GitHub Info page with fresh items from the GitHub Blog, GitHub Changelog, and Awesome Copilot workflows, then open a pull request for Mona to review instead of writing directly to `main`.

## Instructions

1. Read `notes/mona-notes.md` first and follow those editorial guidelines closely.
2. Fetch all of these pages:
   - https://github.blog/latest/
   - https://github.blog/changelog/
  - https://awesome-copilot.github.com/workflows/
3. Review `site/content/github-info.md` and update only the `Latest GitHub Updates` section unless the notes explicitly justify a broader edit.
4. Keep updates short, practical, and useful for developers learning GitHub faster.
5. Mention the source for each new item you add, using GitHub Blog, GitHub Changelog, or Awesome Copilot workflows.
6. Remove stale items when needed so the section stays current.
7. Do not push directly to `main`. Propose the content change with the safe output `create-pull-request`.
8. Open a pull request for Mona to review.

## Pull Request Requirements

- Title: `chore: update GitHub info`
- Include a brief summary of what was added, updated, or removed.
- Include links to the GitHub Blog, GitHub Changelog, or Awesome Copilot workflows entries that informed the update.
- Ask Mona to review the pull request before merge.

## Usage

Run this workflow on its daily schedule or trigger it manually with `workflow_dispatch`.