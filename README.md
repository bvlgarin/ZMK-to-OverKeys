# OverKeys Converter for ZMK

### Automatically convert ZMK keyboard layouts to OverKeys JSON

<br />

## About The Project

**OverKeys Converter for ZMK** is a Python script that transforms ZMK firmware keymap files (`.dtsi` or `.keymap`) into the JSON format required by [OverKeys](https://github.com/conventoangelo/OverKeys) — a keyboard layout visualizer for Windows.

If you're using a programmable keyboard with ZMK firmware (Corne, Lily58, Sofle, or any split keyboard) and want to visualize your layers in OverKeys, this converter does all the heavy lifting for you.

### Why use this converter?

- **Manual conversion is tedious** – One command converts everything
- **ZMK syntax doesn't match OverKeys** – Full behavior mapping (`&kp`, `&mt`, `&lt`, `&mo`, `&td`, etc.)
- **Multiple layers need proper triggers** – Auto-detects layer type (held/toggle) and assigns F14-F18
- **Russian layout setup takes time** – Auto-generated from your base layer (ЙЦУКЕН)

## Features

- **Full ZMK Support** – Converts `&kp`, `&mt`, `&lt`, `&mo`, `&tog`, `&lt_tog`, `&hm`, `&td`, `&bt`, `&out`, `&bootloader`, `&sys_reset`
- **Auto Layer Discovery** – Finds all layers via `display-name` in your ZMK keymap
- **Smart Classification** – Automatically assigns F14-F18 triggers based on layer names
- **Hold vs Toggle Detection** – Distinguishes between momentary (`held`) and toggle layers
- **Russian Layout Generation** – Auto-creates ЙЦУКЕН layout from your base layer
- **42-Key Matrix Support** – Standard 4×12 matrix with thumb cluster (positions 36-42)
- **Bluetooth Command Handling** – Properly parses `&bt BT_CLR` and `&bt BT_SEL N`
- **Tap-Dance Recognition** – Smart mapping for `&td*` patterns
- **Zero Dependencies** – Pure Python 3.6+, no external packages required

## Getting Started

### Installation



---

## Файл: `docs/documentation.md`

# Documentation

Complete documentation for the **ZMK to OverKeys Converter**.

## Table of Contents

- [Getting Started](getting-started.md)
- [Supported Behaviors](supported-behaviors.md)
- [Layer Detection](layer-detection.md)
- [Output Format](output-format.md)
- [Russian Layout Generation](russian-layout.md)
- [Tap-Dance Recognition]([tap-dance.md](https://github.com/bvlgarin/ZMK-to-OverKeys/blob/main/documentation/tap-dance.md#tap-dance-recognition))
- [Bluetooth Command Handling](bluetooth.md)
- [Matrix Layout](output-format.md#matrix-layout-42-keys)
- [Contributing](contributing.md)

## Quick Links

| Section | Description |
|---------|-------------|
| [Installation](getting-started.md#installation) | How to install the converter |
| [Usage](getting-started.md#usage) | Basic usage examples |
| [Behavior Mapping](supported-behaviors.md) | Complete ZMK to OverKeys mapping |
| [Layer Triggers](layer-detection.md) | How F14-F18 triggers are assigned |
| [Russian Layout](russian-layout.md) | Auto-generated ЙЦУКЕН layout |
| [Tap-Dance](tap-dance.md) | Supported tap-dance patterns |
| [Bluetooth](bluetooth.md) | BT_CLR and BT_SEL handling |

## Example: Complete Conversion

See [Getting Started - Quick Start Example](getting-started.md#quick-start-example) for a complete walkthrough.

## Adding to OverKeys

Once you have generated the `.overkeys.txt` file:

1. Open OverKeys on your Windows system
2. Go to **Settings → User Layouts**
3. Copy the entire `"userLayouts": [...]` block from the generated file
4. Paste it into your OverKeys `settings.json` or user configuration
5. Set `"defaultUserLayout"` to your base layer name (e.g., `"DEFAULT"`)
6. Save and restart OverKeys


**to be continued


