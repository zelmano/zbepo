# zBépo

A personal variant of the [bépo](https://bepo.fr) keyboard layout, designed for French text entry and programming. The key design decisions relative to standard bépo:

- **Digits on the base layer** — no Shift required for `0`–`9`
- **Programming symbols on the Shift layer** of the number row (`$`, `@`, `+`, `-`, `/`, `*`, `=`, `%`, ...)
- **Space bar** provides hyphen (`-`), underscore (`_`), and non-breaking space without leaving the home position

The layout is described using [Kalamine](https://github.com/OneDeadKey/kalamine) and targets ISO geometry.

## Layout

```
┌─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┐
│ #   │ $   │     │     │ `   │     │ @   │ +   │ -   │ /   │ *   │ =   │ %   │
│     │ 1   │ 2   │ 3   │ 4   │ 5   │ 6   │ 7   │ 8   │ 9   │ 0   │     │     │
├─────┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┤
│        │ B   │ É   │ P   │ O   │ È   │ !   │ V   │ D   │ L   │ J   │ Z   │ W │
│ Tab    │ b   │ é   │ p   │ o   │ è   │*^   │ v   │ d   │ l   │ j   │ z   │ w │
├────────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬─┤
│         │ A   │ U   │ I   │ E   │ ;   │ C   │ T   │ S   │ R   │ N   │ M   │Ç │
│ Caps    │ a   │ u   │ i   │ e   │ ,   │ c   │ t   │ s   │ r   │ n   │ m   │ç │
├─────────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬───┴──┤
│          │ À   │ Y   │ X   │ :   │ K   │ ?   │ Q   │ G   │ H   │ F   │      │
│ Shift    │ à   │ y   │ x   │ .   │ k   │ '   │ q   │ g   │ h   │ f   │Shift │
└──────────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴──────┘
```

**AltGr layer highlights:**

| Key | AltGr | Shift+AltGr |
|-----|-------|-------------|
| `e` | `€` | `£` |
| `o` | `œ` | `Œ` |
| `a` | `æ` | |
| `u` | `ù` | |
| `i` | `◌̈` dead diaeresis | |
| `n` | `◌̃` dead tilde | |
| `c` | `{` | |
| `t` | `}` | |
| `s` | `(` | |
| `r` | `)` | |
| `d` | `[` | |
| `l` | `]` | |
| `b` | `\|` | |
| `é` | `&` | |
| `y` | `\\` | |
| `x` | `<` | `«` |
| `.` | `>` | `»` |
| `k` | `=` | |
| `q` | `"` | |

**Space bar:**

| Combo | Output |
|-------|--------|
| Space | space |
| Shift+Space | `-` hyphen |
| AltGr+Space | `_` underscore |
| Shift+AltGr+Space | non-breaking space (`\u00A0`) |

## Files

- `zbepo.toml` — Kalamine layout descriptor, source of truth

## Building

With [Kalamine](https://github.com/OneDeadKey/kalamine) installed:

```sh
kalamine build zbepo.toml
```

This produces platform-specific keyboard drivers:

| File | Platform |
|------|----------|
| `.klc` | Windows (MSKLC / wkalamine) |
| `.xkb_keymap` / `.xkb_symbols` | Linux (XKB) |
| `.keylayout` | macOS |
| `.ahk` | Windows user-space (AutoHotkey) |

For Android (physical keyboard via Bluetooth or USB), see [zelmano/bepo-android](https://github.com/zelmano/bepo-android).

## License

MIT
