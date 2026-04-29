
**Output:** `config/corne.overkeys.txt` — ready to copy into OverKeys.

### Requirements

- Python 3.6 or higher
- ZMK keymap file (`.dtsi` or `.keymap` format)

For detailed usage instructions, see the [Documentation](#documentation) section below.

[*back to top*](#)

---

## Documentation

Complete documentation for the **ZMK to OverKeys Converter** is available in this README:

### Getting Started
- [Installation](#installation)
- [Usage](#usage)
- [Requirements](#requirements)

### User Guide
- [Supported Behaviors](#supported-behaviors)
- [Layer Detection](#layer-detection)
- [Output Format](#output-format)

### Advanced Features
- [Russian Layout](#russian-layout-generation)
- [Tap-Dance](#tap-dance-recognition)
- [Bluetooth](#bluetooth-command-handling)
- [Matrix Layout](#matrix-layout)

[*back to top*](#)

---

## Supported Behaviors

| ZMK Behavior | Description | OverKeys Output |
|---|---|---|
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
| `&none` | None | `""` (empty) |

[*back to top*](#)

---

## Layer Detection

The converter automatically assigns F-key triggers based on layer name keywords:

| Layer Name Keywords | Trigger | Type |
|---|---|---|
| `lower`, `lwr`, `num`, `sym`, `number`, `symbols`, `pad` | `F14` | held |
| `raise`, `rse`, `nav`, `navi`, `navigation`, `mov`, `cursor` | `F15` | held |
| `fbuttons`, `fbt`, `fun`, `func`, `function`, `fkeys` | `F16` | held |
| `adjust`, `adj`, `settings`, `set`, `config` | `F17` | held |
| `ru`, `rus`, `russian`, `lang` | `F18` | toggle |

> **Note:** Base layers (`base`, `default`, `qwerty`, `main`, `colemak`, `dvorak`, `workman`) receive no trigger — they become the default layout.

For custom layer names, the converter uses heuristics to determine the appropriate trigger. Unknown layer names default to no trigger.

[*back to top*](#)

---

## Russian Layout Generation

If no Russian language layer is found in your keymap, the converter automatically generates one based on your base layer.

The Russian layout uses the standard ЙЦУКЕН phonetic mapping:

| English | Russian | English | Russian |
|---|---|---|---|
| `Q` | `Й` | `A` | `Ф` |
| `W` | `Ц` | `S` | `Ы` |
| `E` | `У` | `D` | `В` |
| `R` | `К` | `F` | `А` |
| `T` | `Е` | `G` | `П` |
| `Y` | `Н` | `H` | `Р` |
| `U` | `Г` | `J` | `О` |
| `I` | `Ш` | `K` | `Л` |
| `O` | `Щ` | `L` | `Д` |
| `P` | `З` | `;` | `Ж` |
| `[` | `Х` | `'` | `Э` |
| `]` | `Ъ` | `,` | `Б` |
| `.` | `Ю` | `/` | `.` |

The generated Russian layer is assigned:
- **Trigger:** `F18`
- **Type:** `toggle`

[*back to top*](#)

---

## Tap-Dance Recognition

The converter recognizes tap-dance patterns and maps them intelligently:

| ZMK Tap-Dance | OverKeys Output |
|---|---|
| `&tdJ` | `J` |
| `&tdF` | `F` |
| `&tdTaskmgr` | `ESC` |
| `&td_tsk_mngr` | `ESC` |
| `&tdLCMD` | `ENT` |
| `&td_lcmd` | `ENT` |
| `&tdRCMD` | `SPC` |
| `&td_rcmd` | `SPC` |
| `&td_e` | `E` |
| `&td_w` | `W` |
| `&td_i` | `I` |
| `&td_o` | `O` |
| `&td_custom_name` | `CUS` (truncated to 3 chars) |

For custom tap-dance names not in the predefined map, the converter extracts the first 3 characters of the name.

[*back to top*](#)

---

## Bluetooth Command Handling

The converter properly handles Bluetooth commands that span multiple tokens:

| ZMK Command | OverKeys Output |
|---|---|
| `&bt BT_CLR` | `BT CLR` |
| `&bt BT_SEL 0` | `BT 0` |
| `&bt BT_SEL 1` | `BT 1` |
| `&bt BT_SEL 2` | `BT 2` |
| `&bt BT_SEL 3` | `BT 3` |
| `&bt BT_SEL 4` | `BT 4` |
| `&bt BT_SEL 5` | `BT 5` |

[*back to top*](#)

---

## Output Format

The script generates a file with this structure:
