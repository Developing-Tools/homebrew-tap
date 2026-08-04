# Contributing

Thanks for helping maintain this custom tap. Contributions should be small,
easy to review, and traceable to an upstream release or reproducible build.

## Choose your change

| Package type | Definition or metadata | Pull request template |
| --- | --- | --- |
| Cask | `Casks/<token>.rb` | [`new-package.md`][new-package-template] |
| Formula | `Formula/<token>.rb` | [`new-package.md`][new-package-template] |
| Formula bottle | A `bottle do` block in `Formula/<token>.rb` | [`new-package.md`][new-package-template] |
| Existing package or bottle | Update its current definition | [`update-package.md`][update-package-template] |

GitHub supports multiple pull request templates through its `template` query
parameter. Add `template=new-package.md` or `template=update-package.md` to the
compare URL's query string when opening a pull request.

## General requirements

- Use an official upstream homepage and source or download URL.
- Prefer versioned HTTPS URLs and verify every SHA-256 checksum.
- Check release notes for operating-system, architecture, signing, dependency,
  and packaging changes.
- Keep unrelated package changes out of the pull request.
- Explain any checksum change for an unchanged version; never accept a
  republished artifact silently.
- Follow Homebrew's established naming and stanza ordering.

## Casks

Use a lowercase, hyphenated token that matches the filename. For example, the
`example-app` cask belongs in `Casks/example-app.rb`.

Before submitting a cask:

- Confirm the declared minimum macOS version and supported architectures.
- Use `version :latest` and `sha256 :no_check` only when upstream makes a
  stable checksum impractical.
- Verify that every declared app, binary, completion, and manpage exists in the
  downloaded artifact.
- Add a focused `zap` stanza containing only files created by the application.
- Follow the [Homebrew Cask Cookbook][cask-cookbook].

When updating a cask, mount or inspect the new artifact to ensure its internal
layout still matches every declared artifact path.

## Formulae

Formulae belong in `Formula/`. Their class name must correspond to the filename;
for example, `Formula/example-app.rb` defines `class ExampleApp < Formula`.

Before submitting a formula:

- Use a stable upstream source archive rather than a precompiled application.
- Declare the license and all build-time and runtime dependencies.
- Install into Homebrew-provided paths such as `bin`, `lib`, and `share`.
- Include a meaningful `test do` block that exercises the installed software.
- Build and test from source in a clean environment.
- Follow the [Homebrew Formula Cookbook][formula-cookbook].

When updating a formula, review build-system and dependency changes, then rerun
its installation and test from source.

## Bottles

A bottle is a precompiled binary package for a formula, not a standalone
definition. Its checksums and platform tags live in the formula's `bottle do`
block, while the `.tar.gz` bottle archives are hosted at the configured
`root_url`.

Build bottle metadata with Homebrew rather than writing it by hand:

```sh
brew install --build-bottle developing-tools/tap/FORMULA_NAME
brew bottle developing-tools/tap/FORMULA_NAME
```

Before submitting bottle metadata:

- Build from the exact formula revision being bottled.
- Preserve the generated platform tag, cellar value, filename, and SHA-256.
- Publish the archive at a stable HTTPS location matching `root_url`.
- Use `rebuild` when replacing bottle metadata without changing the formula
  version or revision.
- Test that Homebrew can fetch and install the bottle with `--force-bottle`.
- Follow Homebrew's [Bottle documentation][bottles].

## Verify checksums

Calculate a checksum from the exact source, cask artifact, or bottle archive:

```sh
shasum -a 256 path/to/artifact
```

Compare the complete 64-character result with the package definition. When
upstream publishes a trusted SHA-256 digest, verify that it matches the local
result.

## Run local checks

First tap the local checkout:

```sh
brew tap developing-tools/tap /absolute/path/to/homebrew-tap
brew style developing-tools/tap
```

For a cask:

```sh
brew audit --cask --strict developing-tools/tap/CASK_NAME
brew install --cask developing-tools/tap/CASK_NAME
brew uninstall --cask developing-tools/tap/CASK_NAME
```

For a formula:

```sh
brew audit --formula --strict developing-tools/tap/FORMULA_NAME
brew install --build-from-source developing-tools/tap/FORMULA_NAME
brew test developing-tools/tap/FORMULA_NAME
brew uninstall developing-tools/tap/FORMULA_NAME
```

For a formula with bottle metadata:

```sh
brew fetch --force-bottle developing-tools/tap/FORMULA_NAME
brew install --force-bottle developing-tools/tap/FORMULA_NAME
brew test developing-tools/tap/FORMULA_NAME
brew uninstall developing-tools/tap/FORMULA_NAME
```

Run `brew livecheck developing-tools/tap/PACKAGE_NAME` when the definition has a
`livecheck` block.

## Continuous integration

Pull requests run the checks configured in `.github/workflows/`. The current
package set is checked for style and tap syntax, strict audit rules, and its
installation and uninstallation lifecycle. Formula and bottle coverage will be
added when those package types are introduced.

CI complements local testing; it does not replace verifying the release source,
checksums, reproducibility, or installed behavior.

## Pull request guidelines

- Use `Add <Package Name> <type>` for a new definition.
- Use `Update <Package Name> to <version>` for a version update.
- Use `Bottle <Package Name> for <platform>` for bottle-only metadata.
- Keep one package addition or update per pull request.
- Complete the appropriate template and include the operating system and
  architecture used for testing.
- Link the upstream release and every source, download, or bottle artifact.
- Resolve applicable style, audit, build, test, installation, and uninstallation
  failures before requesting review.

[bottles]: https://docs.brew.sh/Bottles
[cask-cookbook]: https://docs.brew.sh/Cask-Cookbook
[formula-cookbook]: https://docs.brew.sh/Formula-Cookbook
[new-package-template]: .github/PULL_REQUEST_TEMPLATE/new-package.md
[update-package-template]: .github/PULL_REQUEST_TEMPLATE/update-package.md
