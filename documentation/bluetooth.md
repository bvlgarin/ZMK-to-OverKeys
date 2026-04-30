# Bluetooth Command Handling

The converter properly handles Bluetooth commands that span multiple tokens.

## Supported Bluetooth Commands

| ZMK Command | OverKeys Output |
|-------------|-----------------|
| `&bt BT_CLR` | `BT CLR` |
| `&bt BT_SEL 0` | `BT 0` |
| `&bt BT_SEL 1` | `BT 1` |
| `&bt BT_SEL 2` | `BT 2` |
| `&bt BT_SEL 3` | `BT 3` |
| `&bt BT_SEL 4` | `BT 4` |
| `&bt BT_SEL 5` | `BT 5` |

## Parsing Logic

The converter:

1. Recognizes `&bt` as a Bluetooth behavior
2. Reads the next token to determine the command type
3. For `BT_SEL`, reads the following numeric token
4. Combines tokens into a single OverKeys-friendly string

## Examples

### In ZMK Keymap

```dts
bindings = <
    &bt BT_CLR
    &bt BT_SEL 0
    &bt BT_SEL 1
>;
