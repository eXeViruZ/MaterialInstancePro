# 06 — Audit Reports

## Overview

Material Instance Pro includes audit checks for common Material Instance maintenance problems.

v1.0.0 focuses on:

- Broken parent references
- Material Instances with no active overrides

---

## Broken Parent

A broken parent means a Material Instance has a missing or invalid parent material reference.

This can happen after:

- Deleting a parent material
- Moving assets incorrectly
- Migrating content between projects
- Removing dependencies
- Importing partial content folders

Broken parent assets should be reviewed because they may render incorrectly or fail to behave as expected.

---

## No Overrides

A no-overrides Material Instance has no active parameter overrides.

This means it inherits all values from its parent material or parent Material Instance.

This can be useful to detect because such an instance may be unnecessary, incorrectly configured, or intentionally used as a placeholder.

---

## No Overrides is not Unused

Important:

```text
No Overrides is not the same as Unused.
```

Material Instance Pro does not perform reference scanning to determine whether an asset is used somewhere in the project.

Definitions:

| Term | Meaning |
|------|---------|
| No Overrides | The Material Instance has no active parameter overrides |
| Unused | The asset is not referenced or used anywhere |

v1.0.0 detects **No Overrides**, not true unused assets.

---

## Static Switch reporting

Material Instance Pro can display and filter Material Instances with static switch parameters.

Static switch editing is not part of v1.0.0.

---

## JSON reports

The commandlet can write JSON audit reports.

Example fields:

```json
{
  "timestamp": "2026-06-26T19:20:04",
  "scanned_count": 2,
  "scan_time_sec": 0.0018,
  "broken_parent_count": 1,
  "no_overrides_count": 1,
  "broken_parent": [],
  "no_overrides": []
}
```

---

## CSV reports

CSV audit reports use issue rows.

Example:

```csv
AssetName,PackagePath,IssueType,ParentMaterial
MI_Test_BrokenParent.MI_Test_BrokenParent,/Game/MIP_Test/MI_Test_BrokenParent.MI_Test_BrokenParent,BrokenParent,
MI_Test_NoOverrides.MI_Test_NoOverrides,/Game/MIP_Test/MI_Test_NoOverrides.MI_Test_NoOverrides,NoOverrides,
```

---

## Recommended workflow

1. Run a project or folder scan.
2. Review Broken Parent results first.
3. Review No Overrides results second.
4. Fix or confirm each result.
5. Export reports if needed for documentation or team review.
