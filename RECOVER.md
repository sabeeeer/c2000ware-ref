# C2000Ware source snapshot recovery

This repository is a source-only offline snapshot of TI C2000Ware Core SDK
v26.00.00.00.STS.

## Restore

```bash
git clone https://github.com/sabeeeer/c2000ware-ref.git
cd c2000ware-ref
git checkout v26.00.00.00-snapshot
```

The release contains split archives for environments where a full clone is
undesirable:

```text
device_support.zip
driverlib.zip
libraries.zip
utilities.zip
boards.zip
```

The release page records SHA256 digests for every asset.

## Use with ti-c2000-ccs-auto

Point the skill at the extracted or cloned SDK root:

```powershell
pwsh -NoProfile -File "$HOME/.codebuddy/skills/ti-c2000-ccs-auto/scripts/c2000ware_find.ps1" `
  -SdkRoot "<path-to-c2000ware-ref>" -List devices
```

## Scope

Included: `.c`, `.h`, `.cmd`, `.asm`, `.syscfg`, `.projectspec`, and the
original license manifest.

Excluded: compiler outputs, PDF/HTML documentation, installers, and prebuilt
libraries that are not source files. Use the official TI package when the full
SDK, documentation, installers, or binary libraries are required:
https://www.ti.com/tool/C2000WARE

## License

See `docs/manifest.html` and the original TI copyright/license headers in each
source file. This repository is an unofficial personal snapshot, not a TI
release.
