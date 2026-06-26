# 08 — Troubleshooting

## The plugin does not appear in the toolbar

Check the following:

1. The plugin is installed in the correct folder.
2. The plugin is enabled under **Edit → Plugins**.
3. Unreal Editor was restarted after enabling the plugin.
4. The installed version matches your Unreal Engine version.

---

## Scan Project finds no assets

Material Instance Pro scans Material Instance Constants, not normal master materials.

Check whether your assets are Material Instances:

```text
MI_Example
```

not only master materials:

```text
M_Example
```

Also confirm that your Material Instances are under:

```text
/Game
```

---

## Scan Project finds Engine or plugin content

Project scan is intended to scan:

```text
/Game
```

If unexpected content appears, check whether assets were copied into your project content folder or whether you used a folder scan on a broader path.

---

## A parameter is not visible

Material Instance Pro focuses on active Material Instance override data.

Check the following:

1. The parameter exists in the parent material.
2. The parameter is exposed as a real material parameter.
3. The override is active in the Material Instance.
4. The parent material is not broken.
5. The parameter is not stale or orphaned data from an old parent.

---

## No Overrides result seems wrong

No Overrides means the Material Instance has no active parameter overrides.

It does not mean the asset is unused.

If the Material Instance should contain parameters, open it in Unreal Editor and check whether the override checkboxes are enabled.

---

## Broken Parent is detected

This means the parent material reference is missing or invalid.

Possible fixes:

1. Reassign a valid parent material.
2. Restore the missing parent asset.
3. Reimport or migrate the missing dependency.
4. Remove the broken test asset if it was created only for validation.

---

## Texture import from CSV does not work

Texture values must use Unreal object paths.

Correct:

```text
/Game/MIP_Test/T_Test_B.T_Test_B
```

Incorrect:

```text
C:\Textures\T_Test_B.png
```

Incorrect:

```text
/Game/MIP_Test/T_Test_B.uasset
```

---

## CSV import changed nothing

Check:

1. The target Material Instance still exists.
2. The parameter name is unchanged.
3. The parameter type is correct.
4. The value format is valid.
5. The parameter is an active override.
6. The CSV was not reformatted by spreadsheet software.

---

## Static switches are visible but not editable

This is expected in v1.0.0.

Material Instance Pro displays and filters static switch parameters, but does not edit static switches in v1.0.0.

---

## Layer dropdown only shows Any

This is expected if the material does not use Material Layers or layer-associated parameters.

Normal global parameters do not create layer entries.

---

## Commandlet returns exit code 1

Exit code `1` means:

```text
-FailOnBroken was set and broken parent Material Instances were found.
```

This is expected behavior if your project contains broken parent references.

---

## Commandlet returns exit code 2

Exit code `2` means:

```text
-FailOnNoOverrides was set and no-overrides Material Instances were found.
```

This is expected behavior if your project contains Material Instances without active overrides.

---

## Build or packaging fails while Live Coding is active

Close Unreal Editor before packaging the plugin.

If Live Coding is active, disable it or close the editor before running:

```text
RunUAT BuildPlugin
```

---

## Need support?

Use the Discord support link:

```text
https://discord.gg/vgpmnN6nCR
```

When reporting an issue, include:

- Unreal Engine version
- Plugin version
- Steps to reproduce
- Screenshots if relevant
- Commandlet log if the issue is commandlet-related
