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
