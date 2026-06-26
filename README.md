# Material Instance Pro

> Version 1.0.0 | Unreal Engine 5.7 / 5.8 | Editor-only

Material Instance Pro is an Unreal Engine editor plugin for working with Material Instance Constants at scale.

It helps technical artists, environment artists, material artists, and Unreal Engine teams scan Material Instances, review active parameter overrides, batch edit values, detect broken parent references, identify instances with no active overrides, and export or import parameter data through CSV.

---

## Supported Unreal Engine versions

- Unreal Engine 5.7
- Unreal Engine 5.8

Each Unreal Engine version should use the matching plugin package from Fab.

---

## What it is for

Material Instance Pro is designed for projects that contain many Material Instances and need a faster way to inspect and adjust them without opening every asset manually.

Typical use cases:

- Review Material Instance parameter overrides across a project or folder
- Batch edit scalar, vector/color, texture, and parent material values
- Find Material Instances with missing or broken parent references
- Find Material Instances with no active parameter overrides
- Export parameter data to CSV for review
- Import edited CSV values back into existing Material Instances
- Generate JSON or CSV audit reports from a commandlet

---

## What it is not

Material Instance Pro is not a runtime gameplay plugin.

It does not add gameplay systems, does not modify engine source code, and does not perform real asset usage/reference analysis.

Important distinction:

- **No Overrides** means a Material Instance has no active parameter overrides.
- **Unused** would mean an asset is not referenced anywhere in the project.

Material Instance Pro detects **No Overrides**, not true asset usage.

---

## Documentation

Full documentation is available in the [`docs`](docs/INDEX.md) folder.

| # | File | Topic |
|---|------|-------|
| 1 | [01_Installation.md](docs/01_Installation.md) | Install, enable, first launch |
| 2 | [02_Getting_Started.md](docs/02_Getting_Started.md) | UI overview, first scan |
| 3 | [03_Scanning_And_Filtering.md](docs/03_Scanning_And_Filtering.md) | Scan project/folder, filters, results |
| 4 | [04_Batch_Editing.md](docs/04_Batch_Editing.md) | Edit mode, parameters, save behavior |
| 5 | [05_CSV_Import_Export.md](docs/05_CSV_Import_Export.md) | CSV export/import workflow |
| 6 | [06_Audit_Reports.md](docs/06_Audit_Reports.md) | Broken parent and no-overrides audit |
| 7 | [07_Commandlet.md](docs/07_Commandlet.md) | Headless reports and CI usage |
| 8 | [08_Troubleshooting.md](docs/08_Troubleshooting.md) | Common issues and fixes |
| 9 | [09_Changelog.md](docs/09_Changelog.md) | Version history |

---

## Requirements

- Unreal Engine 5.7 or 5.8
- Editor-only plugin
- Supported development platforms: Windows, Mac, Linux
- Supported target build platforms: Not applicable for runtime builds

---

## Support

- Discord: https://discord.gg/vgpmnN6nCR
- GitHub Docs: https://github.com/eXeViruZ/MaterialInstancePro
- Publisher: Hanke Unreal Tools
