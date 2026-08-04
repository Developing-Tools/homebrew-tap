<!-- Use this template to update an existing cask, formula, or formula bottle. -->

## Package update

### Type

- [ ] Cask
- [ ] Formula
- [ ] Bottle for a formula

- Package name:
- Current version/revision:
- Proposed version/revision:
- Release notes:
- Source/download URL:
- SHA-256:

## Upstream or build changes

<!-- Summarize dependency, build, signing, packaging, or artifact-layout changes. -->

## Compatibility

- Operating-system requirements changed: <!-- No, or explain. -->
- Supported architectures changed: <!-- No, or explain. -->
- Tested on: <!-- Include the OS version and architecture. -->

## Bottle changes

<!-- Complete for bottle changes; otherwise write "Not applicable". -->

- Formula revision:
- Bottle tag:
- Cellar:
- Rebuild:
- Root URL:
- Bottle filename:
- Bottle SHA-256:

## Checklist

<!-- Complete "All package types" and the subsection matching the selected type. -->

### All package types

- [ ] The version or revision matches the upstream release or reproducible build.
- [ ] Every changed checksum was verified against the exact referenced artifact.
- [ ] An unchanged version with a new checksum is explained above.
- [ ] Release notes were reviewed for compatibility and packaging changes.
- [ ] `brew livecheck developing-tools/tap/PACKAGE_NAME` reports the expected release, when applicable.
- [ ] `brew style developing-tools/tap` passes.

### Cask

- [ ] Declared apps, binaries, completions, and manpages still exist.
- [ ] `brew audit --cask --strict developing-tools/tap/CASK_NAME` passes.
- [ ] Installation, launch, and uninstallation were tested.

### Formula

- [ ] Dependencies, patches, build steps, and tests remain correct.
- [ ] `brew audit --formula --strict developing-tools/tap/FORMULA_NAME` passes.
- [ ] Source installation and `brew test developing-tools/tap/FORMULA_NAME` pass.

### Bottle

- [ ] The bottle was built from the exact formula revision being updated.
- [ ] Platform, cellar, rebuild, and checksum values came from `brew bottle` output.
- [ ] The archive is available beneath `root_url` at the expected filename.
- [ ] Installation and testing with `--force-bottle` pass.

## Additional notes

<!-- Add anything reviewers should know, or write "None". -->
