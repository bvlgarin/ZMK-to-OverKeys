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

```bash
curl -O https://raw.githubusercontent.com/bvlgarin/zmk-to-overkeys/main/zmk_to_overkeys.py
chmod +x zmk_to_overkeys.py


dtsi
default_layer {
    display-name = "BASE";
    bindings = <
        &kp Q    &kp W    &kp E    &kp R    &kp T    &kp Y    &kp U    &kp I    &kp O    &kp P
        &kp A    &kp S    &kp D    &kp F    &kp G    &kp H    &kp J    &kp K    &kp L
        &kp Z    &kp X    &kp C    &kp V    &kp B    &kp N    &kp M    &kp BSPC
        &kp LGUI &kp LALT &kp SPACE &mo 1   &mo 2    &kp RET
    >;
};

lower_layer {
    display-name = "LOWER";
    bindings = <
        &kp N1   &kp N2   &kp N3   &kp N4   &kp N5   &kp N6   &kp N7   &kp N8   &kp N9   &kp N0
        &kp EXCL &kp AT   &kp HASH &kp DLLR &kp PRCNT &kp CARET &kp AMPS &kp ASTRK &kp LPAR &kp RPAR
        &trans   &kp MINUS &kp EQUAL &kp LBKT &kp RBKT &kp BSLH &kp GRAVE
        &trans   &trans   &trans   &trans   &mo 1    &trans
    >;
};
