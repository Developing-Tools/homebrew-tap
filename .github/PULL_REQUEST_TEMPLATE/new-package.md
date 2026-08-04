<!-- Use this template for a new cask, formula, or formula bottle. -->

## New package

### Type

- [ ] Cask
- [ ] Formula
- [ ] Bottle for a formula

<!-- What does this add, and why is it useful in this personal tap? -->

## Source

- Package name:
- Homepage:
- Release or source tag:
- Source/download URL:
- Version:
- SHA-256:
- License: <!-- Required for formulae; include when known for casks. -->

## Compatibility

- Operating systems:
- Minimum macOS version, if applicable:
- Architectures:
- Tested on: <!-- Include the OS version and architecture. -->

## Bottle details

<!-- Complete for a bottle; otherwise write "Not applicable". -->

- Formula revision:
- Bottle tag:
- Cellar:
- Root URL:
- Bottle filename:
- Bottle SHA-256:

## Checklist

<!-- Complete "All package types" and the subsection matching the selected type. -->

### All package types

- [ ] The name and definition filename follow Homebrew conventions.
- [ ] URLs use official upstream or controlled bottle hosting over HTTPS.
- [ ] Every checksum was calculated from the exact referenced artifact.
- [ ] Operating-system and architecture support were verified.
- [ ] `brew style developing-tools/tap` passes.

### Cask

- [ ] Declared apps, binaries, completions, and manpages exist in the artifact.
- [ ] `brew audit --cask --strict developing-tools/tap/CASK_NAME` passes.
- [ ] Installation, launch, and uninstallation were tested.

### Formula

- [ ] All build and runtime dependencies and the license are declared.
- [ ] The formula has a meaningful `test do` block.
- [ ] `brew audit --formula --strict developing-tools/tap/FORMULA_NAME` passes.
- [ ] Source installation and `brew test developing-tools/tap/FORMULA_NAME` pass.

### Bottle

- [ ] The bottle was built from the exact formula revision in this pull request.
- [ ] Platform, cellar, and checksum metadata came from `brew bottle` output.
- [ ] The archive is available beneath `root_url` at the expected filename.
- [ ] Installation and testing with `--force-bottle` pass.

## Additional notes

<!-- Include signing, reproducibility, packaging, or hosting details reviewers should know. -->
