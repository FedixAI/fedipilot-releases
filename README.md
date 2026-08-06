# FediPilot — downloads

AI-powered workpaper and tax preparation for Australian accountants.

**Download the latest version from the [Releases page](../../releases).**

| Platform | File |
| --- | --- |
| Windows 10/11 (x64) | `FediPilotSetup-x64-<version>.exe` |
| macOS (Apple Silicon) | `FediPilot-darwin-arm64-<version>.zip` |

After installing, FediPilot updates itself: it checks for new versions on
startup and hourly, and offers a one-click update when one is available. You
only download from this page once.

## About the installers

Builds are currently **unsigned**, so the operating system will warn you the
first time:

- **Windows** — SmartScreen shows "Windows protected your PC". Click **More
  info** → **Run anyway**.
- **macOS** — Gatekeeper refuses a double-click. **Right-click** the app →
  **Open** → **Open**.

`SHA256SUMS.txt` is attached to every release so you can verify a download.

## What is in this repository

Only the built installers and `releases.json`, the manifest the auto-updater
reads. **The source code is not here** — it lives in a private repository. This
repository exists because a download link and an auto-updater both have to be
reachable without a login.

## The update manifest

`releases.json` lives on the [`feed`](../../tree/feed) branch, not here. It is
written only by the `publish-feed` workflow, which validates it before it goes
live -- see that branch for why.
