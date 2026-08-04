# Homebrew Tap

A custom [Homebrew tap][homebrew-taps] for personal use.

## Add the tap

The repository `developing-tools/homebrew-tap` has the short tap name
`developing-tools/tap`.

```sh
brew tap developing-tools/tap
```

## Install packages

Install a formula:

```sh
brew install developing-tools/tap/FORMULA_NAME
```

Install a cask:

```sh
brew install --cask developing-tools/tap/CASK_NAME
```

For example, install Alacritty with:

```sh
brew install --cask developing-tools/tap/alacritty
```

When a formula provides a compatible bottle, Homebrew selects and installs it
automatically. Otherwise, Homebrew builds the formula from source.

## macOS support

This tap currently aims to support the two most recent major macOS releases. If
you encounter an issue on another macOS version, please [open an issue][issues]
with the relevant details, and we will be happy to consider it on a case-by-case
basis.

## Repository layout

- `Casks/` contains macOS application definitions.
- `Formula/` contains source-build package definitions when formulae are added.
- Bottle metadata lives in the corresponding formula's `bottle do` block;
  bottle archives are published as release or package assets rather than
  committed to the source tree.

The packages currently available are defined by the Ruby files in those
directories. See the [contribution guide][contributing] to add or update one.

## Update packages

```sh
brew update
brew upgrade developing-tools/tap/FORMULA_NAME
brew upgrade --cask developing-tools/tap/CASK_NAME
```

## Uninstall packages

```sh
brew uninstall developing-tools/tap/FORMULA_NAME
brew uninstall --cask developing-tools/tap/CASK_NAME
```

Remove the tap when it is no longer needed:

```sh
brew untap developing-tools/tap
```

## Documentation

- [Homebrew taps][homebrew-taps]
- [Formula Cookbook][formula-cookbook]
- [Cask Cookbook][cask-cookbook]
- [Bottles][bottles]

## License

This repository is available under the [MIT License][license].

[bottles]: https://docs.brew.sh/Bottles
[cask-cookbook]: https://docs.brew.sh/Cask-Cookbook
[contributing]: CONTRIBUTING.md
[formula-cookbook]: https://docs.brew.sh/Formula-Cookbook
[homebrew-taps]: https://docs.brew.sh/Taps
[issues]: https://github.com/developing-tools/homebrew-tap/issues
[license]: LICENSE
