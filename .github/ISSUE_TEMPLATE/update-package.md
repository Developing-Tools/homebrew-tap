---
name: Request a package update
about: Request an update to an existing cask, formula, or bottle
title: "Update: "
labels: enhancement
assignees: ""
---

<!-- Use this template to request an update to an existing package. -->

## Package update

### Type

- [ ] Cask
- [ ] Formula
- [ ] Bottle for a formula

- Package name:
- Current version/revision:
- Requested version/revision:
- Release page or release notes:
- Source/download URL:
- SHA-256 source: <!-- Published checksum, release API digest, or locally calculated. -->
- Upstream license: <!-- Include the SPDX identifier and license URL when available. -->

## Reason for the update

<!-- Explain why this update is wanted. Mention fixes, features, security
changes, compatibility requirements, or broken behavior in the current version. -->

## Upstream changes

- Artifact names or layout changed: <!-- No, or explain. -->
- Installation or build process changed: <!-- No, or explain. -->
- Dependencies changed: <!-- No, or explain. -->
- Upstream license or redistribution terms changed: <!-- No, or explain. -->
- Signing or notarization changed: <!-- No, or explain. -->
- Minimum macOS version changed: <!-- No, or explain. -->
- Supported architectures changed: <!-- No, or explain. -->

## Package scripts

- Must any `preflight`, `postflight`, `uninstall`, `zap`, or other custom script
  logic be added or changed? <!-- No, or explain. -->
- If yes, provide the proposed commands and their purpose:
- What files or system settings would those commands change?
- How are those changes reversed during uninstall or zap?

## Automatic updates

- Does this package already have a dedicated automatic-update workflow?
- Should one be added or changed as part of this update? <!-- Yes or no, with a reason. -->

<!-- Complete the remaining questions when an updater should be added or changed. -->

- Release metadata source: <!-- For example, a GitHub release API endpoint. -->
- Stable-release selection rule: <!-- Include how prereleases are excluded. -->
- Version extraction rule:
- Artifact selection rule: <!-- Include OS/architecture filename patterns. -->
- SHA-256 source or calculation method:
- Files and fields the workflow should update:
- Pre-update processing or scripts: <!-- Write "None" when unnecessary. -->
- Post-update validation or scripts: <!-- Write "None" when unnecessary. -->
- How should an existing open, closed, or superseded update PR be handled?

## Verification

- Tested macOS version and architecture:
- Installation tested: <!-- Yes, no, or not yet. -->
- Uninstallation tested: <!-- Yes, no, or not yet. -->
- Upstream signature or checksum verified: <!-- Yes, no, or not provided. -->

## Additional context

<!-- Add logs, screenshots, related issues, or anything else useful to reviewing
and implementing the update. -->
