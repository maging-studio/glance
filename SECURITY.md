# Security

## Reporting a vulnerability

Please report security issues privately rather than in a public issue.

Use GitHub's [private vulnerability reporting](https://github.com/maging-studio/glance/security/advisories/new)
on this repository. You'll get a reply within a few days.

Useful things to include: the Glance and macOS versions, what an attacker would
gain, and a document or file that demonstrates it.

## What Glance does on your machine

- **Documents are read locally.** Rendering — including LaTeX and Mermaid —
  happens on-device. Nothing about a document's contents is uploaded.
- **Network access** is used for three things: checking for updates, downloading
  an update you accept, and loading images a document references over `http(s)`.
- **The Quick Look extension is sandboxed**, as macOS requires. It carries a
  read-only exception for `/Users/` and `/Volumes/` so that relative image
  references inside a previewed document resolve.
- **The app is signed with a Developer ID and notarized by Apple.** Updates are
  delivered by [Sparkle](https://sparkle-project.org) and verified against an
  EdDSA signature and the developer's team identity before installing.

## Supported versions

Fixes go into the latest release. If you're on an older build, update first —
[Releases](https://github.com/maging-studio/glance/releases/latest).
