# orcastudio-repack

Arch/CachyOS PKGBUILD repack of [OrcaStudio](https://github.com/jarczakpawel/OrcaStudio) (Bambu Studio fork with OrcaSlicer changes and restored BambuNetwork support) from the upstream AppImage release.

## Install

```bash
makepkg -si
```

Requires `pacman`-based distro and `sudo`. Package installs to `/opt/orcastudio` with `orcastudio` in `/usr/bin`, hicolor icon, and desktop entry.

## Update

Edit `_tag` in `PKGBUILD` to the new release tag, update `sha256sums` (`makepkg -g`), rebuild.

Not affiliated with upstream. AGPL-3.0-only — see upstream.
