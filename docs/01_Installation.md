# 01 — Installation

## Requirements

- Unreal Engine 5.7 or 5.8
- Windows, Mac, or Linux editor environment
- Unreal Engine project with Material Instance Constants
- Editor-only plugin — no runtime dependency

---

## Choose the correct engine package

Material Instance Pro is distributed per Unreal Engine version.

Use the package that matches your project:

| Unreal Engine version | Plugin package |
|----------------------|----------------|
| Unreal Engine 5.7 | Material Instance Pro for UE 5.7 |
| Unreal Engine 5.8 | Material Instance Pro for UE 5.8 |

Do not install the UE 5.7 package into a UE 5.8 engine version unless you are intentionally testing compatibility yourself.

---

## Install from Fab

1. Purchase or add **Material Instance Pro** on Fab.
2. Open the Epic Games Launcher.
3. Go to **Library → Fab Library**.
4. Find **Material Instance Pro**.
5. Click **Install to Engine** next to the matching Unreal Engine installation.
6. Open or restart your Unreal Engine project.

---

## Install manually from ZIP

1. Download the plugin ZIP for your Unreal Engine version.
2. Extract the ZIP.

You should get a folder named:

```text
MaterialInstancePro
```

3. Copy the folder into one of these locations:

Engine-wide install:

```text
[UE_5.7 or UE_5.8]/Engine/Plugins/Marketplace/MaterialInstancePro/
```

Project-only install:

```text
[YourProject]/Plugins/MaterialInstancePro/
```

4. Restart Unreal Editor.

---

## Enable the plugin

1. Open your project in Unreal Editor.
2. Go to **Edit → Plugins**.
3. Search for:

```text
Material Instance Pro
```

4. Enable the plugin.
5. Restart the editor if prompted.

---

## Open the tool

After restart, open the tool from the toolbar or menu.

Toolbar:

```text
Material Instance Pro button
```

Menu:

```text
Tools → Material Instance Pro
```

The tool opens as a dockable Unreal Editor tab.

---

## Module information

| Module | Type |
|--------|------|
| MaterialInstancePro | Editor |

This plugin does not contain a runtime module.
