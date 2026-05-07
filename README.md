# OverKeys Converter for ZMK

**Automatically convert ZMK keyboard layouts to OverKeys JSON**

---

## About The Project

**OverKeys Converter for ZMK** is a Python script that transforms ZMK firmware keymap files (.dtsi or .keymap) into the JSON format required by [OverKeys](https://github.com/conventoangelo/OverKeys) — a keyboard layout visualizer for Windows.

If you're using a programmable keyboard with ZMK firmware (Corne, Lily58, Sofle, or any split keyboard) and want to visualize your layers in OverKeys, this converter does all the heavy lifting for you.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Features

- Full ZMK Support (&kp, &mt, &lt, &mo, &tog, &td, &bt)
- Auto Layer Discovery via display-name
- Smart Classification with F14-F18 triggers
- Russian Layout Generation (ЙЦУКЕН)
- 42-Key Matrix Support
- Zero Dependencies

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Getting Started

### Installation

You can use the converter in several ways:

1. **Using Git Clone (Recommended)**

   ```bash
   git clone https://github.com/bvlgarin/zmk-to-overkeys.git
   cd zmk-to-overkeys
   ```

2. **Download the script directly**

   ```bash
   curl -O https://raw.githubusercontent.com/bvlgarin/zmk-to-overkeys/main/scripts/zmk_to_overkeys.py
   chmod +x zmk_to_overkeys.py
   ```

For detailed installation instructions, see the [Getting Started Guide](docs/getting-started.md).

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Basic Usage

```bash
python zmk_to_overkeys.py path/to/your/keymap.keymap
```

#### Example

```bash
python zmk_to_overkeys.py config/corne.keymap
```

**Output:** config/corne.overkeys.txt — ready to copy into OverKeys.

### Requirements

- Python 3.6 or higher
- ZMK keymap file (.dtsi or .keymap format)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Documentation

Complete documentation for **ZMK to OverKeys Converter** is available in the [docs/](docs/) folder:

### Getting Started (Docs)

- [Installation Guide](docs/getting-started.md#installation)
- [Basic Usage](docs/getting-started.md#usage)
- [Requirements](docs/getting-started.md#requirements)

### User Guide

- [Bluetooth Command Handling](docs/bluetooth.md)
- [Layer Detection](docs/layer-detection.md)
- [Output Format](docs/output-format.md)
- [Russian Layout Generation](docs/russian-layout.md)
- [Supported Behaviors](docs/supported-behaviors.md)
- [Tap-Dance Recognition](docs/tap-dance.md)


### Reference

- [Complete Documentation](docs/documentation.md)
- [Contributing Guide](docs/contributing.md)
- [Changelog](changelog.md)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Example

See the [complete conversion example](examples/example.md) for a detailed walkthrough with ZMK code and OverKeys JSON output.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Adding to OverKeys

Once you have generated the .overkeys.txt file:

1. Open OverKeys on your Windows system
2. Go to **Settings → User Layouts**
3. Copy the entire "userLayouts": [...] block from the generated file
4. Paste it into your OverKeys settings.json or user configuration
5. Set "defaultUserLayout" to your base layer name (e.g., "DEFAULT")
6. Save and restart OverKeys

Your ZMK layers will now be available in OverKeys!

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contributing

Contributions are what make the open-source community such an amazing place to learn and collaborate. Any contributions to **ZMK to OverKeys Converter** are greatly appreciated.

If you have suggestions for improvements, bug fixes, or new features, please feel free to open an issue or submit a pull request.

See [Contributing Guide](docs/contributing.md) for more details.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## License

Distributed under the MIT License. See LICENSE file for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Acknowledgments

- [OverKeys](https://github.com/conventoangelo/OverKeys) – The amazing keyboard visualizer that makes this converter useful
- [ZMK Firmware](https://zmk.dev/) – The powerful open-source firmware for programmable keyboards
- [ZMK Documentation](https://zmk.dev/docs) – For behavior definitions and key codes

<p align="right">(<a href="#readme-top">back to top</a>)</p>
