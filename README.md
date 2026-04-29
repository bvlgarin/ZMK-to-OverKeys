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


### Installation

```bash
# Download the script
curl -O https://raw.githubusercontent.com/YOUR_REPO/zmk_to_overkeys.py
chmod +x zmk_to_overkeys.py

### Usage
```bash
python zmk_to_overkeys.py config/corne.keymap

### Example Output
"userLayouts": [
    {
        "name": "DEFAULT",
        "keys": [["Q","W","E","R","T","Y","U","I","O","P","",""], ...],
        "trigger": "",
        "type": ""
    },
    {
        "name": "LOWER",
        "keys": [["1","2","3","4","5","6","7","8","9","0","",""], ...],
        "trigger": "F14",
        "type": "held"
    }
],
"defaultUserLayout": "DEFAULT"

### Requirements
Python 3.6+
ZMK keymap file in .dtsi or .keymap format








<a id="readme-top"></a>

<div align="center">
  <h1 align="center">ZMK to OverKeys Converter</h1>
  
  <p align="center">
    <a href="https://github.com/YOUR_USERNAME/zmk-to-overkeys/releases/latest">
      <img src="https://img.shields.io/github/v/release/YOUR_USERNAME/zmk-to-overkeys?label=Release&style=for-the-badge&logo=github&logoColor=FAFBFE&labelColor=10151D&color=A87FFB" alt="Release">
    </a>
    <a href="https://github.com/YOUR_USERNAME/zmk-to-overkeys/releases">
      <img src="https://img.shields.io/github/downloads/YOUR_USERNAME/zmk-to-overkeys/total?label=Downloads&style=for-the-badge&logo=github&logoColor=FAFBFE&labelColor=10151D&color=A87FFB" alt="Downloads">
    </a>
    <a href="https://github.com/YOUR_USERNAME/zmk-to-overkeys/blob/main/LICENSE">
      <img src="https://img.shields.io/github/license/YOUR_USERNAME/zmk-to-overkeys?style=for-the-badge&logo=github&logoColor=FAFBFE&labelColor=10151D&color=A87FFB" alt="License">
    </a>
    <a href="https://github.com/YOUR_USERNAME/zmk-to-overkeys/stargazers">
      <img src="https://img.shields.io/github/stars/YOUR_USERNAME/zmk-to-overkeys?style=for-the-badge&logo=github&logoColor=FAFBFE&labelColor=10151D&color=A87FFB" alt="Stars">
    </a>
  </p>

  <h3 align="center">Automatically convert ZMK keyboard layouts to OverKeys JSON format</h3>

  <p align="center">
    <a href="#quick-start">Quick Start</a> ·
    <a href="#features">Features</a> ·
    <a href="#supported-behaviors">ZMK Support</a> ·
    <a href="#documentation">Docs</a> ·
    <a href="#contributing">Contributing</a>
  </p>
</div>

---

## About The Project

**ZMK to OverKeys Converter** is a Python script that automatically transforms ZMK firmware keymap files (`.dtsi` or `.keymap`) into the JSON format required by [OverKeys](https://github.com/conventoangelo/OverKeys) — a keyboard layout visualizer for Windows.

If you're using a programmable keyboard with ZMK firmware (Corne, Lily58, Sofle, or any split keyboard) and want to visualize your layers in OverKeys, this converter does all the heavy lifting for you.

### Why use this converter?

| Problem | Solution |
|---------|----------|
| Manual conversion is tedious | One command converts everything |
| ZMK syntax doesn't match OverKeys | Full behavior mapping (`&kp`, `&mt`, `&lt`, `&mo`, `&td`, etc.) |
| Multiple layers need proper triggers | Auto-detects layer type (held/toggle) and assigns F14-F18 |
| Russian layout setup takes time | Auto-generated from your base layer (ЙЦУКЕН) |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

## Features

- **Full ZMK Support** — Converts `&kp`, `&mt`, `&lt`, `&mo`, `&tog`, `&lt_tog`, `&hm`, `&td`, `&bt`, `&out`, `&bootloader`, `&sys_reset`
- **Auto Layer Discovery** — Finds all layers via `display-name` in your ZMK keymap
- **Smart Classification** — Automatically assigns F14-F18 triggers based on layer names
- **Hold vs Toggle Detection** — Distinguishes between momentary (`held`) and toggle layers
- **Russian Layout Generation** — Auto-creates ЙЦУКЕН layout from your base layer
- **42-Key Matrix Support** — Standard 4×12 matrix with thumb cluster (positions 36-42)
- **Bluetooth Command Handling** — Properly parses `&bt BT_CLR` and `&bt BT_SEL N`
- **Tap-Dance Recognition** — Smart mapping for `&td*` patterns
- **Zero Dependencies** — Pure Python 3.6+, no external packages required

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

## Supported Behaviors

| ZMK Behavior | Description | OverKeys Output |
|--------------|-------------|-----------------|
| `&kp A` | Key press | `A` |
| `&mt LSHIFT A` | Mod-tap | `A` |
| `&lt 1 SPACE` | Layer-tap | `SPC` |
| `&mo 1` | Momentary layer | `MO(1)` |
| `&tog 1` | Toggle layer | `TG(1)` |
| `&lt_tog 1 A` | Layer-tap toggle | `A` |
| `&hm LCTRL A` | Hold-mod | `A` |
| `&tdJ` | Tap-dance | `J` |
| `&bt BT_CLR` | Bluetooth clear | `BT CLR` |
| `&bt BT_SEL 0` | Bluetooth select | `BT 0` |
| `&out USB` | Output selection | `USB` |
| `&bootloader` | Bootloader mode | `BOOT` |
| `&sys_reset` | System reset | `RST` |
| `&trans` | Transparent | `""` (empty) |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

## Layer Detection

The converter automatically assigns F-key triggers based on layer name keywords:

| Layer Name Keywords | Trigger | Type |
|---------------------|---------|------|
| `lower`, `lwr`, `num`, `sym`, `number`, `symbols`, `pad` | `F14` | `held` |
| `raise`, `rse`, `nav`, `navi`, `navigation`, `mov`, `cursor` | `F15` | `held` |
| `fbuttons`, `fbt`, `fun`, `func`, `function`, `fkeys` | `F16` | `held` |
| `adjust`, `adj`, `settings`, `set`, `config` | `F17` | `held` |
| `ru`, `rus`, `russian`, `lang` | `F18` | `toggle` |

> **Note:** Base layers (`base`, `default`, `qwerty`, `main`, `colemak`, `dvorak`, `workman`) receive no trigger — they become the default layout.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

## Quick Start

### Installation

```bash
# Download the script
curl -O https://raw.githubusercontent.com/YOUR_USERNAME/zmk-to-overkeys/main/zmk_to_overkeys.py
chmod +x zmk_to_overkeys.py
Usage
bash
python zmk_to_overkeys.py path/to/your/keymap.keymap
Example
bash
python zmk_to_overkeys.py config/corne.keymap
Output: config/corne.overkeys.txt — ready to copy into OverKeys.

<p align="right">(<a href="#readme-top">back to top</a>)</p>
Usage Examples
Basic ZMK Keymap
Input (corne.keymap):

dts
default_layer {
    display-name = "BASE";
    bindings = <
        &kp Q    &kp W    &kp E    &kp R    &kp T
        &kp A    &kp S    &kp D    &kp F    &kp G
        &kp Z    &kp X    &kp C    &kp V    &kp B
        &kp SPACE  &mo 1   &kp RET
    >;
};

lower_layer {
    display-name = "LOWER";
    bindings = <
        &kp N1   &kp N2   &kp N3   &kp N4   &kp N5
        &kp EXCL &kp AT   &kp HASH &kp DLLR &kp PRCNT
        &trans   &kp MINUS &kp EQUAL &kp BSPC
    >;
};
Output (OverKeys JSON):

json
"userLayouts": [
    {
        "name": "DEFAULT",
        "keys": [
            ["Q","W","E","R","T","Y","U","I","O","P","",""],
            ["A","S","D","F","G","H","J","K","L","","",""],
            ["Z","X","C","V","B","N","M","BSPC","","","",""],
            ["LGUI","LALT","SPC","MO(1)","ENT","","","","","","",""]
        ],
        "trigger": "",
        "type": ""
    },
    {
        "name": "LOWER",
        "keys": [
            ["1","2","3","4","5","6","7","8","9","0","",""],
            ["!","@","#","$","%","^","&","*","(",")","",""],
            ["","-","=","[","]","\\","`","","","","",""],
            ["","","","","","","","","","","",""]
        ],
        "trigger": "F14",
        "type": "held"
    }
],
"defaultUserLayout": "DEFAULT"
Advanced Examples
dts
&mt LSHIFT A     →  A
&tdJ             →  J
&bt BT_SEL 0     →  BT 0
&mo 1            →  MO(1)
&tog 2           →  TG(2)
&lt_tog 1 SPACE  →  SPC
<p align="right">(<a href="#readme-top">back to top</a>)</p>
Output Format
The script generates a file with this structure:

javascript
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
        "name": "RUSSIAN",
        "keys": [ /* Auto-generated ЙЦУКЕН */ ],
        "trigger": "F18",
        "type": "toggle"
    }
],
"defaultUserLayout": "DEFAULT"
Matrix Layout (42 keys)
text
Row 0:  [0]  [1]  [2]  [3]  [4]  [5]  [6]  [7]  [8]  [9]  [10] [11]
Row 1:  [12] [13] [14] [15] [16] [17] [18] [19] [20] [21] [22] [23]
Row 2:  [24] [25] [26] [27] [28] [29] [30] [31] [32] [33] [34] [35]
Row 3:  [36] [37] [38] [39] [40] [41] [42] [43] [44] [45] [46] [47]
        ↑ Thumb cluster occupies columns 3-8 (indices 38-44)
<p align="right">(<a href="#readme-top">back to top</a>)</p>
Documentation
Adding to OverKeys
Run the converter on your ZMK keymap

Open the generated .overkeys.txt file

Copy the "userLayouts": [...] block

Paste into your OverKeys settings.json

Set "defaultUserLayout" to your base layer name

Requirements
Python 3.6 or higher

ZMK keymap file (.dtsi or .keymap format)

<p align="right">(<a href="#readme-top">back to top</a>)</p>
Contributing
Contributions are welcome!

How to Help
Report bugs — Open an issue with your ZMK keymap file

Suggest features — New layer detection patterns, additional key mappings

Submit PRs — Fix bugs or add support for more ZMK behaviors

Share your layout — Show how the converter works with your keyboard

Development Setup
bash
git clone https://github.com/YOUR_USERNAME/zmk-to-overkeys.git
cd zmk-to-overkeys
python zmk_to_overkeys.py test/fixtures/sample.keymap
Planned Features
Support for 34-key (3×10) matrices

Support for 56-key (5×12) matrices

German/French/Spanish layout generation

GUI drag-and-drop interface

<p align="right">(<a href="#readme-top">back to top</a>)</p>
License
Distributed under the MIT License. See LICENSE file for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>
