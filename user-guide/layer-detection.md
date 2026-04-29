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
