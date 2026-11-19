# HSK Pastel

A warm pastel theme for [Zed](https://zed.dev), built around clay, cream and warm charcoal tones. Ships with two variants:

- **HSK Pastel Dark** — near-black warm background with soft pastel syntax colors
- **HSK Pastel Light** — cream background with deeper, readable accents

## Install

Open Zed → `zed: extensions` → search for **HSK Pastel** → Install.
Then run `theme selector: toggle` and pick a variant.

To follow your OS appearance:

```json
"theme": {
  "mode": "system",
  "light": "HSK Pastel Light",
  "dark": "HSK Pastel Dark"
}
```

## Palette highlights

| Element | Dark | Light |
|---|---|---|
| Keywords (`const`, `class`, `import`) | `#E8A189` | `#C26A4C` |
| Control flow (`if`, `return`, `throw`) — italic | `#F28C7A` | `#B0452F` |
| Functions | `#A9C6E8` | `#4F7CB0` |
| Types | `#A7D3C4` | `#3F8A78` |
| Strings | `#B5CFA8` | `#5F8A52` |
| Numbers / booleans | `#86D9D0` | `#2B8A84` |
| `const` variables | `#E8D5B5` | `#7E6447` |
| `let` variables | `#B9B5F2` | `#5B55B5` |
| Parameters — italic | `#F7A8B8` | `#B5476A` |
| `this` / built-ins — italic | `#D7B0EE` | `#9150A8` |

## Optional: richer variable highlighting

The theme defines distinct styles for parameters, `const` vs `let`, built-ins, static variables and function definitions (bold). Zed only applies most of them when **semantic tokens** are enabled. Add this to your `settings.json`:

```json
"semantic_tokens": "combined",
"global_lsp_settings": {
  "semantic_token_rules": [
    { "token_type": "function", "token_modifiers": ["declaration"], "style": ["function.definition", "function"] },
    { "token_type": "method", "token_modifiers": ["declaration"], "style": ["function.definition", "function.method", "function"] },
    { "token_type": "parameter", "style": ["variable.parameter"] },
    { "token_type": "property", "style": ["variable.member", "property"] },
    { "token_type": "variable", "token_modifiers": ["defaultLibrary"], "style": ["variable.builtin", "variable.special"] },
    { "token_type": "variable", "token_modifiers": ["static"], "style": ["variable.static"] },
    { "token_type": "variable", "token_modifiers": ["readonly"], "style": ["variable.readonly"] },
    { "token_type": "variable", "token_modifiers": ["mutable"], "style": ["variable.mutable"] },
    { "token_type": "variable", "style": ["variable"] }
  ]
}
```

Then run `editor: restart language server`.

## License

[Apache License 2.0](LICENSE)
