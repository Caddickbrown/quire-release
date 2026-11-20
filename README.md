# Quire releases

[Quire](https://github.com/Caddickbrown/quire-release/releases/latest) is a
journalling app over a plain folder of Markdown files: a terminal app
(`quire`, also installed as `jnl`), a Linux desktop app, and an app for
iPhone, iPad and Mac. Every one reads and writes the same files, so your
journal stays yours: plain text you can open in any editor.

This repository holds Quire's **releases** and its installer only. There is
no source code here.

## Install

One line, on Linux (x86_64, arm64) or a Mac (Apple silicon, Intel):

```sh
curl -fsSL https://raw.githubusercontent.com/Caddickbrown/quire-release/main/install.sh | bash
```

It downloads the latest release, checks each file against the release's
SHA-256, and asks before each step. Try `bash -s -- --dry-run` after `bash`
to see the plan without changing anything, or `--help` for every option.

## Update

- Terminal: `quire update` (`--check` only reports). It downloads the latest
  release from here and installs it only if its signature checks out.
- Linux desktop app (AppImage): Settings › About › Updates. The update is
  signature-checked before it is installed.
- `.deb` / `.rpm`: install the new package from the release with your package
  manager.

## Releases

Every release, with its notes and files, is on the
[Releases page](https://github.com/Caddickbrown/quire-release/releases):

- `quire-<target>.tar.gz`: the terminal app (`quire` and `jnl`), with a
  `.sha256`, a `.sig` and (from 1.0.1) a `.release.sig` beside it.
- `Quire_<version>_<arch>.AppImage` (with a `.sig`), `.deb` and `.rpm`: the
  Linux desktop app, listed in `SHA256SUMS-desktop-<arch>`.
- `latest.json`: what the desktop app's updater reads.

The `.sig` files are made with Quire's release key; the apps check them
against the public key they were built with. A SHA-256 only shows that a
download arrived whole.

`linux/src-tauri/icons/128x128.png` is the desktop app's icon, which the
installer uses for its launcher entry.

Quire is MIT-licensed.
