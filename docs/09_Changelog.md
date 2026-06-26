# 09 — Changelog

## v1.0.0 — Initial Release

Supported Unreal Engine versions:

- Unreal Engine 5.7
- Unreal Engine 5.8

---

### Added

- Dockable Material Instance Pro editor window
- Toolbar entry for quick access
- Project scan for Material Instance Constants under `/Game`
- Folder scan workflow
- Material Instance result list
- Details panel for selected Material Instances
- Scalar parameter display and editing
- Vector/color parameter display and editing
- Texture parameter display and editing
- Parent material reassignment
- Save workflow for edited Material Instances
- CSV export for Material Instance parameter data
- CSV import for supported parameter edits
- Broken parent detection
- No-overrides detection
- Broken Parent filter
- No Overrides filter
- Has Switches filter
- Layer filter
- Parameter type filter
- Static switch display and filtering
- JSON audit report output
- CSV audit report output
- `MIPAudit` commandlet
- `-ScanFolder` commandlet option
- `-FailOnBroken` commandlet option
- `-FailOnNoOverrides` commandlet option

---

### Notes

Material Instance Pro is an editor-only plugin.

It does not include runtime gameplay code and is not included in packaged runtime builds.

---

### Important terminology

The plugin detects **No Overrides**, not true unused assets.

No Overrides means:

```text
The Material Instance has no active parameter overrides.
```

Unused would mean:

```text
The asset is not referenced anywhere in the project.
```

v1.0.0 does not perform asset reference usage analysis.
