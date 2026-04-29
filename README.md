🔧 ZMK to OverKeys Layout Converter
A powerful converter that automatically transforms ZMK keyboard firmware keymaps into OverKeys JSON format with full layer detection, Russian layout support, and smart classification.

✨ Features
Automatic layer discovery – Finds all layers via display-name in ZMK keymap files

Intelligent layer classification – Assigns F-key triggers (F14-F18) based on layer names

Hold/Toggle detection – Distinguishes between momentary (held) and toggle layers

Complete keycode mapping – Converts 200+ ZMK keycodes to OverKeys format

Tap-dance support – Recognises &td* patterns and maps them intelligently

Russian layout generation – Auto-creates Russian layer from base layer (Cyrillic ЙЦУКЕН)

42-key matrix – Standard 4×12 matrix with thumb cluster (positions 36-42)

BT_SEL auto-fix – Handles multi-token Bluetooth selection commands






markdown
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

You can use the converter in two ways:

**1. Download the script directly**

Supported Behaviors
ZMK Behavior	Description	OverKeys Output
&kp A	Key press	A
&mt LSHIFT A	Mod-tap	A
&lt 1 SPACE	Layer-tap	SPC
&mo 1	Momentary layer	MO(1)
&tog 1	Toggle layer	TG(1)
&lt_tog 1 A	Layer-tap toggle	A
&hm LCTRL A	Hold-mod	A
&tdJ	Tap-dance	J
&bt BT_CLR	Bluetooth clear	BT CLR
&bt BT_SEL 0	Bluetooth select	BT 0
&out USB	Output selection	USB
&bootloader	Bootloader mode	BOOT
&sys_reset	System reset	RST
&trans	Transparent	"" (empty)
&none	None	"" (empty)
<p align="right">(<a href="#overkeys-converter-for-zmk">back to top</a>)</p>
Layer Detection
The converter automatically assigns F-key triggers based on layer name keywords:

Layer Name Keywords	Trigger	Type
lower, lwr, num, sym, number, symbols, pad	F14	held
raise, rse, nav, navi, navigation, mov, cursor	F15	held
fbuttons, fbt, fun, func, function, fkeys	F16	held
adjust, adj, settings, set, config	F17	held
ru, rus, russian, lang	F18	toggle
Note: Base layers (base, default, qwerty, main, colemak, dvorak, workman) receive no trigger — they become the default layout.

For custom layer names, the converter uses heuristics to determine the appropriate trigger. Unknown layer names default to no trigger.

<p align="right">(<a href="#overkeys-converter-for-zmk">back to top</a>)</p>




// ============================================================
// OverKeys Layout JSON
// Generated from: corne.keymap
// Date: 2024-01-15 14:30:00
// ============================================================

"userLayouts": [
    {
        "name": "DEFAULT",
        "keys": [ /* 4x12 matrix */ ],
        "trigger": "",
        "type": ""
    },
    {
        "name": "LOWER",
        "keys": [ /* 4x12 matrix */ ],
        "trigger": "F14",
        "type": "held"
    },
    {
        "name": "RAISE",
        "keys": [ /* 4x12 matrix */ ],
        "trigger": "F15",
        "type": "held"
    },
    {
        "name": "RUSSIAN",
        "keys": [ /* Auto-generated ЙЦУКЕН */ ],
        "trigger": "F18",
        "type": "toggle"
    }
],
"defaultUserLayout": "DEFAULT"
