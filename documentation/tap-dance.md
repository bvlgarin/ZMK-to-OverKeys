# Tap-Dance Recognition

The converter recognizes tap-dance patterns and maps them intelligently.

## Supported Tap-Dance Patterns

| ZMK Tap-Dance | OverKeys Output |
|---------------|-----------------|
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

## Custom Tap-Dance Names

For custom tap-dance names not in the predefined map, the converter extracts the first 3 characters of the name:

| ZMK Tap-Dance | OverKeys Output |
|---------------|-----------------|
| `&td_custom_name` | `CUS` (truncated to 3 chars) |
| `&td_media_play` | `MED` |
| `&td_brightness` | `BRI` |

## Pattern Detection Logic

The converter uses the following logic:

1. Checks predefined mappings for exact matches
2. If no match found, extracts first 3 characters of the tap-dance name
3. Converts to uppercase for consistency

## Adding Custom Mappings

To add custom tap-dance mappings, edit the `TAP_DANCE_MAP` dictionary in the script:

```python
TAP_DANCE_MAP = {
    "tdJ": "J",
    "tdTaskmgr": "ESC",
    "td_lcmd": "ENT",
    # Add your custom mappings here
}
