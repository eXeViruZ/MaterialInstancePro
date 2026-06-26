# 02 — Getting Started

## Overview

Material Instance Pro provides a dockable editor window for scanning and editing Material Instance Constants.

The main workflow is:

1. Scan your project or a selected folder.
2. Load the scan results.
3. Select a Material Instance.
4. Review active parameters and audit state.
5. Enter edit mode if changes are needed.
6. Save modified Material Instances.

---

## First scan

Open the Material Instance Pro tab and click:

```text
Scan Project
```

This scans Material Instance Constants under:

```text
/Game
```

Engine content and plugin content are excluded from the project scan.

---

## Folder scan

To scan a specific content folder:

1. Select a folder in the Content Browser.
2. Open Material Instance Pro.
3. Click:

```text
Scan Folder...
```

4. Load the results.

This is useful when you only want to inspect a specific asset group such as characters, props, environments, or materials.

---

## Load results

After scanning, click:

```text
Load
```

The left panel shows the scanned Material Instances.

The right panel shows details and parameters for the selected Material Instance.

---

## Result list

Each result can show information such as:

- Asset name
- Package path
- Parent material
- Parameter count
- Broken parent state
- No-overrides state
- Static switch availability
- Layer information, if present

---

## Details panel

When you select a Material Instance, the details panel shows its editable data and detected parameters.

Supported parameter display:

- Scalar parameters
- Vector and color parameters
- Texture parameters
- Static switch parameters
- Parent material reference

---

## Saving changes

Changes are only final when saved.

After editing, use:

```text
Save
```

or save the affected assets through the Unreal Editor.

For safety, Material Instance Pro uses editor transactions where supported, so changes can participate in Unreal Editor undo/redo behavior.
