# Layer Detection

The converter automatically assigns F-key triggers based on layer name keywords.

## Trigger Mapping Table

| Layer Name Keywords | Trigger | Type |
|---------------------|---------|------|
| `lower`, `lwr`, `num`, `sym`, `number`, `symbols`, `pad` | `F14` | `held` |
| `raise`, `rse`, `nav`, `navi`, `navigation`, `mov`, `cursor` | `F15` | `held` |
| `fbuttons`, `fbt`, `fun`, `func`, `function`, `fkeys` | `F16` | `held` |
| `adjust`, `adj`, `settings`, `set`, `config` | `F17` | `held` |
| `ru`, `rus`, `russian`, `lang` | `F18` | `toggle` |

## Base Layers

Base layers receive no trigger — they become the default layout:

- `base`
- `default`
- `qwerty`
- `main`
- `colemak`
- `dvorak`
- `workman`

## Custom Layer Names

For custom layer names not in the predefined lists, the converter uses heuristics to determine the appropriate trigger:

1. **Momentary detection**: Looks for keywords like `layer`, `momentary`, `temp`, `one-shot`
2. **Toggle detection**: Looks for keywords like `toggle`, `lock`, `sticky`
3. **Default**: No trigger assigned for unknown layer names

> **Note:** Unknown layer names default to no trigger. You can manually edit the generated JSON if needed.

## Important Notes

- Base layers (`base`, `default`, `qwerty`, `main`, `colemak`, `dvorak`, `workman`) receive no trigger — they become the default layout.
- For custom layer names, the converter uses heuristics to determine the appropriate trigger.
- Unknown layer names default to no trigger.
