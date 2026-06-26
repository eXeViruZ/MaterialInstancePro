# 05 — CSV Import and Export

## Overview

Material Instance Pro can export Material Instance parameter data to CSV and import edited CSV values back into existing Material Instances.

This is useful for:

- Reviewing values outside Unreal Editor
- Bulk-adjusting parameter values
- Sharing parameter data with team members
- Versioning parameter snapshots
- Comparing Material Instance values

---

## Export CSV

1. Scan and load Material Instances.
2. Click:

```text
Export CSV
```

3. Choose a save location.
4. Open the CSV in a text editor or spreadsheet tool.

---

## Import CSV

1. Export a CSV first.
2. Edit supported value fields.
3. Save the CSV.
4. In Material Instance Pro, click:

```text
Import CSV
```

5. Select the edited CSV.
6. Review the result.
7. Save modified Material Instances.

---

## Recommended editor

For best results, edit CSV files in:

- Visual Studio Code
- Notepad++
- Rider
- Another plain text editor

Spreadsheet software can change formatting, quoting, decimal symbols, or asset paths. Use it carefully.

---

## CSV columns

Typical CSV columns include:

```text
AssetName
PackagePath
ParentMaterial
ParentBroken
ParameterName
ParameterType
Association
LayerIndex
LayerName
Value
Overridden
```

The exact columns may depend on the exported data.

---

## Supported parameter types

CSV import/export supports active override data for:

| Type | Supported |
|------|-----------|
| Scalar | Yes |
| Vector/Color | Yes |
| Texture | Yes |
| Parent Material | Exported as asset data |
| Static Switch | Display/export only in v1.0.0 |

---

## Texture paths

Texture values should use Unreal object paths.

Example:

```text
/Game/MIP_Test/T_Test_B.T_Test_B
```

Do not use file paths such as:

```text
C:\Textures\albedo.png
```

Do not use raw `.uasset` file paths.

---

## CSV does not create new assets

CSV import modifies existing Material Instances.

It does not create new Material Instances, materials, textures, or folders.

---

## Safety notes

Before importing a large CSV:

1. Use source control.
2. Test on a small folder first.
3. Review the changed assets.
4. Save only when the result is correct.

---

## Common import mistakes

| Problem | Fix |
|---------|-----|
| Texture value not applied | Use Unreal object path, not disk path |
| Asset not found | Confirm the Material Instance still exists |
| Parameter not changed | Confirm the parameter is an active override |
| CSV opened in Excel changed data | Re-export and edit in a plain text editor |
