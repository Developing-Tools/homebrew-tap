---
name: Request a new package
about: Propose a new cask, formula, or bottle for the tap
title: "Add: "
labels: enhancement
assignees: ""
---

<!-- Use this template to request a new cask, formula, or formula bottle. -->

## Package request

### Type

- [ ] Cask
- [ ] Formula
- [ ] Bottle for a formula

- Package name:
- Proposed token: <!-- The lowercase filename without .rb. -->
- Homepage:
- Upstream license: <!-- Include the SPDX identifier and license URL when available. -->
- Redistribution restrictions or special terms: <!-- Write "None" when unknown or inapplicable. -->

## Why should this be added?

<!-- Explain why the package is useful in this personal tap. Mention why an
official Homebrew cask or formula does not meet the need, if one exists. -->

## Upstream source

- Latest stable version:
- Release page:
- Source/download URL:
- SHA-256 source: <!-- Published checksum, release API digest, or locally calculated. -->
- Upstream repository:

<!-- List every artifact when URLs or checksums differ by OS or architecture. -->

## Installation

- Installed artifacts: <!-- For example, an app, binary, manpage, or library. -->
- Build system and dependencies: <!-- Required for formulae; otherwise write "Not applicable". -->
- Minimum macOS version, if applicable:
- Supported architectures:
- Caveats or configuration required after installation:

## Package scripts

- Does the package require `preflight`, `postflight`, `uninstall`, `zap`, or
  other custom script logic? <!-- Yes or no. -->
- If yes, provide the proposed commands and explain why declarative Homebrew
  stanzas are insufficient:
- What files or system settings would those commands change?
- How are those changes reversed during uninstall or zap?

## Automatic updates

- Is a dedicated automatic-update workflow needed? <!-- Yes or no. -->

<!-- If no, explain how updates should be detected, such as a livecheck block,
and skip the remaining questions in this section. -->

- Release metadata source: <!-- For example, a GitHub release API endpoint. -->
- Stable-release selection rule: <!-- Include how prereleases are excluded. -->
- Version extraction rule: <!-- For example, remove a leading "v" from the tag. -->
- Artifact selection rule: <!-- Include OS/architecture filename patterns. -->
- SHA-256 source or calculation method:
- Files and fields the workflow should update:
- Pre-update processing or scripts: <!-- Write "None" when unnecessary. -->
- Post-update validation or scripts: <!-- Write "None" when unnecessary. -->
- Authentication, rate-limit, or release-publication concerns:

## Verification

- Tested macOS version and architecture:
- Installation tested: <!-- Yes, no, or not yet. -->
- Uninstallation tested: <!-- Yes, no, or not yet. -->
- Upstream signature or checksum verified: <!-- Yes, no, or not provided. -->

## Additional context

<!-- Add release notes, screenshots, related issues, or anything else useful to
reviewing and implementing the request. -->
