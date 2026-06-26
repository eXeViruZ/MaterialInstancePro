# 04 — Batch Editing

## Overview

Material Instance Pro can edit values on existing Material Instance Constants.

Supported edit targets in v1.0.0:

- Scalar parameters
- Vector and color parameters
- Texture parameters
- Parent material reference

---

## Enter edit mode

1. Scan and load Material Instances.
2. Select a Material Instance.
3. Enter edit mode.
4. Change the desired values.
5. Save the asset.

---

## Scalar parameters

Scalar parameters are numeric values such as:

```text
Roughness
Metallic
Specular
Opacity
```

Use the numeric input field to adjust the value.

---

## Vector and color parameters

Vector parameters are commonly used for colors and RGBA values.

Material Instance Pro supports color editing for vector parameters.

After committing a color value, the UI refreshes the displayed value.

---

## Texture parameters

Texture parameters can be changed through the texture picker.

Example texture parameter:

```text
AlbedoTexture
```

The selected texture must be a valid Unreal texture asset.

---

## Parent material reassignment

Material Instance Pro can reassign the parent material of a Material Instance.

Use this carefully.

Recommended workflow:

1. Select the Material Instance.
2. Choose the new parent material.
3. Confirm the change.
4. Save the Material Instance.
5. Review parameters after reassignment.

Changing the parent material may change which parameters are valid for the instance.

---

## Save behavior

After editing, save the modified assets.

If you close the editor without saving, Unreal may discard unsaved asset changes.

Recommended:

```text
Save edited Material Instances before restarting the editor.
```

---

## Undo/redo

Material Instance Pro uses Unreal Editor transactions where supported.

This allows changes to participate in normal editor undo/redo workflows.

---

## Important limitation

Material Instance Pro edits active Material Instance data.

Disabled or inactive parameter overrides are not treated as editable active overrides in the main parameter list or CSV export.
