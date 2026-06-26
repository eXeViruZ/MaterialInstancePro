# 03 — Scanning and Filtering

## Scan modes

Material Instance Pro supports two main scan workflows.

---

## Scan Project

```text
Scan Project
```

Scans Material Instance Constants under:

```text
/Game
```

This mode is intended for normal project-wide audits.

It does not scan:

```text
/Engine
```

or unrelated plugin content paths.

---

## Scan Folder

```text
Scan Folder...
```

Scans a specific project content folder.

Use this when you want to audit only a specific area, such as:

```text
/Game/Characters
/Game/Environment
/Game/Materials
/Game/MIP_Test
```

---

## Load

After scanning, click:

```text
Load
```

This loads Material Instance data into the UI.

---

## Supported asset type

Material Instance Pro focuses on:

```text
Material Instance Constant assets
```

It does not scan normal master materials as editable Material Instances.

For example:

```text
M_MasterMaterial
```

is a master material.

```text
MI_MasterMaterial_01
```

is a Material Instance and can be scanned.

---

## Filters

Material Instance Pro includes filters for narrowing large result sets.

Available filters:

| Filter | Meaning |
|--------|---------|
| Broken Parent | Shows Material Instances with missing or broken parent references |
| No Overrides | Shows Material Instances with no active parameter overrides |
| Has Switches | Shows Material Instances with static switch parameters |
| Has Layers | Shows Material Instances with layer-associated parameters |
| Layer | Filters by detected material layer |
| Type | Filters by parameter type |

---

## Broken Parent filter

Use this to find Material Instances whose parent material reference is missing or invalid.

This is useful after:

- Moving materials between projects
- Deleting parent materials
- Migrating assets
- Cleaning up content folders

---

## No Overrides filter

Use this to find Material Instances with no active parameter overrides.

Important:

```text
No Overrides does not mean unused.
```

It only means the Material Instance does not currently override any parameters from its parent.

---

## Has Switches filter

Use this to find Material Instances with static switch parameters.

Material Instance Pro displays and filters static switches.

Static switch editing is not part of v1.0.0.

---

## Layer filter

The layer dropdown only shows layer values when the scanned Material Instances contain Material Layer or layer-associated parameter data.

If your materials use only normal global parameters, the layer dropdown may only show:

```text
Any
```

That is expected behavior.
