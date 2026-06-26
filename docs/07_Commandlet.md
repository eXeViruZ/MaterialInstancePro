# 07 — Commandlet

## Overview

Material Instance Pro includes a headless audit commandlet for automated reporting.

This is useful for:

- CI checks
- Build validation
- Automated content audits
- Nightly reports
- Team pipelines

The commandlet can run without opening the Unreal Editor UI.

---

## Commandlet name

```text
MIPAudit
```

---

## Basic usage

```bash
UnrealEditor-Cmd.exe "[YourProject].uproject" -run=MIPAudit
```

---

## Recommended Windows example

Use the UnrealEditor-Cmd.exe path from the engine version you are auditing. For UE 5.8, replace `UE_5.7` with your `UE_5.8` installation path.


```bat
"E:\UE_5.7\Engine\Binaries\Win64\UnrealEditor-Cmd.exe" "G:\YourProject\YourProject.uproject" -run=MIPAudit -Format=json -OutputDir="G:\YourProject\MIPReports" -unattended -nop4
```

---

## Options

| Flag | Description |
|------|-------------|
| `-Format=json` | Write a JSON audit report |
| `-Format=csv` | Write a CSV audit report |
| `-OutputDir="Path"` | Output directory for generated report files |
| `-ScanFolder=/Game/Path` | Scan only Material Instances under a specific package path |
| `-FailOnBroken` | Return a failing exit code when broken parent references are found |
| `-FailOnNoOverrides` | Return a failing exit code when no-overrides Material Instances are found |
| `-FailOnUnused` | Deprecated alias for `-FailOnNoOverrides` |

---

## Output filenames

Reports are written with timestamped filenames.

Examples:

```text
MIPAudit_20260626_191907.json
MIPAudit_20260626_192004.csv
```

---

## JSON example

```bat
"E:\UE_5.7\Engine\Binaries\Win64\UnrealEditor-Cmd.exe" "G:\YourProject\YourProject.uproject" -run=MIPAudit -Format=json -ScanFolder=/Game/Materials -OutputDir="G:\YourProject\MIPReports" -unattended -nop4
```

---

## CSV example

```bat
"E:\UE_5.7\Engine\Binaries\Win64\UnrealEditor-Cmd.exe" "G:\YourProject\YourProject.uproject" -run=MIPAudit -Format=csv -ScanFolder=/Game/Materials -OutputDir="G:\YourProject\MIPReports" -unattended -nop4
```

---

## Fail on broken parent

```bat
"E:\UE_5.7\Engine\Binaries\Win64\UnrealEditor-Cmd.exe" "G:\YourProject\YourProject.uproject" -run=MIPAudit -Format=json -ScanFolder=/Game/Materials -FailOnBroken -OutputDir="G:\YourProject\MIPReports" -unattended -nop4
```

If broken parent Material Instances are found, the commandlet returns a failing exit code.

---

## Exit codes

| Code | Meaning |
|------|---------|
| `0` | Pass |
| `1` | Broken parent found and `-FailOnBroken` was set |
| `2` | No-overrides Material Instances found and `-FailOnNoOverrides` was set |
| `3` | Both fail conditions were triggered |

---

## Report categories

The commandlet separates audit categories:

| Category | Meaning |
|----------|---------|
| `broken_parent` | Material Instances with missing or invalid parent references |
| `no_overrides` | Material Instances with no active parameter overrides |

Broken parent assets are not duplicated as no-overrides results.

---

## CI example

```yaml
- name: Run Material Instance Pro audit
  run: |
    "$env:UE_PATH\Engine\Binaries\Win64\UnrealEditor-Cmd.exe" "$env:PROJECT_PATH" `
      -run=MIPAudit `
      -Format=json `
      -ScanFolder=/Game/Materials `
      -FailOnBroken `
      -OutputDir="$env:GITHUB_WORKSPACE\MIPReports" `
      -unattended `
      -nop4
```

---

## Notes

Use `-FailOnBroken` for strict production checks.

Use `-FailOnNoOverrides` only if your project treats no-overrides Material Instances as content issues. Some teams intentionally keep placeholder or inheritance-only Material Instances.
