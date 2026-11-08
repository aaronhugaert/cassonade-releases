# Cassonade releases

Cassonade is a lean visual interface for agentic workflows: git worktrees, local pull request review, and local-first Jira and Confluence changes, all kept as plain files in git. This repository only distributes the app. **It contains no source code**: just this README and the workflow that builds each release.

## Download

Get the latest version from the [latest release](../../releases/latest). No GitHub login is needed.

| Your computer | File |
| --- | --- |
| Windows (64-bit) | `Cassonade-Setup-<version>-x64.exe` |
| Mac with Apple silicon (M1 and later) | `Cassonade-<version>-arm64.dmg` |
| Mac with an Intel processor | `Cassonade-<version>-x64.dmg` |

`SHA256SUMS` on each release lists the checksum of every file. You need git installed and nothing else.

## First launch

The installers are not signed with a Windows or Apple certificate, so both systems warn once.

- **Windows:** "Windows protected your PC" appears. Click *More info*, then *Run anyway*.
- **macOS:** open the dmg and drag Cassonade to Applications. The first launch is blocked: open System Settings, Privacy & Security, and click *Open Anyway*. Or run this once in a terminal:

  ```bash
  xattr -dr com.apple.quarantine /Applications/Cassonade.app
  ```

## Updates

The app updates itself. It checks this repository's latest release, verifies the download against a signature made with the project's update key (the matching public key is built into the app), and installs it when you quit or when you click *Restart to update*. Releases with breaking changes ask first. Nothing unsigned is ever installed.

## About this repository

Releases are built here by GitHub Actions from the project's private source repository, so the build does not use private-repository minutes. The release workflow is in `.github/workflows/release.yml`; `.github/workflows/icon-check.yml` compiles and previews the macOS icon. The installers contain the app's bundled JavaScript, as any desktop app does; the source tree is not published.
