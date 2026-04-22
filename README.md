# zBépo

> Variante personnelle du [bépo](https://bepo.fr) — chiffres en base, symboles de programmation en shift. Version **0.5.0**.

Layout décrit avec [Kalamine](https://github.com/OneDeadKey/kalamine), géométrie ISO côté source, locale `fr`. Le diagramme ci-dessous montre le rendu sur un **clavier physique QWERTY ANSI** (ç est sur la touche backslash, la rangée du bas n'a pas de touche 102ND).

## Pourquoi cette variante

Le bépo standard place les chiffres sur la couche Shift du pavé numérique, héritage de la logique « lettres accentuées en base » (`1 → "`, `2 → «`, etc.). En usage programmation / saisie technique, cela impose une pression Shift permanente pour taper des chiffres, et les symboles courants en code (`+`, `-`, `*`, `/`, `=`, `@`, `%`, `$`, `#`) se retrouvent éparpillés sur les couches AltGr.

zBépo inverse cette logique :

- **Chiffres en base**, accessibles directement.
- **Symboles de programmation sur la couche Shift** du pavé numérique, regroupés et mémorisables.
- **Home row bépo intacte** (`a u i e , c t s r n`) — on garde l'ergonomie du bépo pour la saisie française.
- **Barre d'espace multi-fonction** : `-`, `_`, espace insécable sans quitter la home row.

C'est un compromis pour un usage mixte code + français, pas un remplacement du bépo.

## Layout

Chaque case montre les 4 couches d'une touche :

```
┌─────┐
│ S A │   S = Shift              A = Shift + AltGr
│ b a │   b = base               a = AltGr
└─────┘
```

```
┌─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────────┐
│ #   │ $ ¯ │   ´ │   ˇ │ ` ` │     │ @   │ +   │ -   │ /   │ *   │ =   │ %   │         │
│     │ 1   │ 2   │ 3   │ 4   │ 5   │ 6   │ 7   │ 8   │ 9   │ 0 ° │     │     │  Bksp   │
└─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────────┘
┌─────────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┐
│         │ B   │ É   │ P   │ O Œ │ È   │ !   │ V   │ D   │ L   │ J   │ Z   │ W   │ Ç   │
│   Tab   │ b | │ é & │ p   │ o œ │ è   │ ^   │ v [ │ d ] │ l   │ j   │ z   │ w   │ ç   │
└─────────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┘
┌──────────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬──────────┐
│          │ A   │ U   │ I   │ E £ │ ;   │ C   │ T   │ S   │ R   │ N   │ M   │          │
│   Caps   │ a æ │ u ù │ i ¨ │ e € │ ,   │ c { │ t } │ s ( │ r ) │ n ~ │ m   │  Enter   │
└──────────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴──────────┘
┌─────────────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────────────┐
│             │ À   │ Y   │ X « │ : » │ K   │ ?   │ Q   │ G   │ H   │ F   │             │
│    Shift    │ à / │ y \ │ x < │ . > │ k = │ '   │ q " │ g   │ h   │ f   │    Shift    │
└─────────────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────────────┘
┌───────┬───────┬───────┬───────────────────────────────┬───────┬───────┬───────┬───────┐
│       │       │       │                               │       │       │       │       │
│ Ctrl  │ Super │ Alt   │            Espace             │ AltGr │ Super │ Menu  │ Ctrl  │
└───────┴───────┴───────┴───────────────────────────────┴───────┴───────┴───────┴───────┘
```

### Barre d'espace

| Combo | Sortie |
|-------|--------|
| Espace | espace |
| Shift + Espace | `-` tiret |
| AltGr + Espace | `_` underscore |
| Shift + AltGr + Espace | espace insécable (U+00A0) |

### Touches mortes

Les symboles ci-dessous sont des **dead keys** : appuie sur la touche morte, puis sur la lettre à accentuer.

| Signe | Nom | Position | Exemple |
|-------|-----|----------|---------|
| `¯` | macron | Shift+AltGr + `1` | `¯` + `a` → `ā` |
| `´` | accent aigu | Shift+AltGr + `2` | `´` + `e` → `é` |
| `ˇ` | caron | Shift+AltGr + `3` | `ˇ` + `s` → `š` |
| `` ` `` | accent grave | Shift+AltGr + `4` | `` ` `` + `a` → `à` |
| `^` | circonflexe | base, touche `!` (au-dessus du 7) | `^` + `a` → `â` |
| `¨` | tréma | AltGr + `i` | `¨` + `e` → `ë` |
| `~` | tilde | AltGr + `n` | `~` + `n` → `ñ` |

> Sur la touche `4`, l'accent grave apparaît deux fois : à gauche la grave **littérale** (Shift+4), à droite la grave **morte** (Shift+AltGr+4).

## Build

Avec [Kalamine](https://github.com/OneDeadKey/kalamine) installé :

```sh
pip install kalamine
kalamine build zbepo.toml
```

Sortie :

| Fichier | Plateforme |
|---------|------------|
| `zbepo.klc` | Windows — installable via MSKLC |
| `zbepo.xkb_symbols` / `zbepo.xkb_keymap` | Linux — XKB |
| `zbepo.keylayout` | macOS |
| `zbepo.ahk` | Windows user-space (AutoHotkey, pas besoin de driver) |
| `zbepo.svg` | aperçu visuel |

## Installation

### Windows (MSKLC)

1. Installer [Microsoft Keyboard Layout Creator](https://www.microsoft.com/en-us/download/details.aspx?id=102134).
2. `File → Load Source File…` → `zbepo.klc`.
3. `Project → Build DLL and Setup Package` → lancer le `setup.exe` généré.
4. Ajouter la disposition dans **Paramètres Windows → Heure et langue → Langue → Français → Options → Ajouter un clavier → zBépo**.

Alternative sans driver : exécuter `zbepo.ahk` avec [AutoHotkey](https://www.autohotkey.com/) (pas de droits admin requis, mais interception user-space — peut mal interagir avec certains jeux).

### Linux (XKB)

```sh
sudo cp zbepo.xkb_symbols /usr/share/X11/xkb/symbols/zbepo
setxkbmap zbepo
```

Pour persister : éditer `/etc/default/keyboard` (Debian/Ubuntu) ou la conf de l'environnement de bureau.

### macOS

1. Copier `zbepo.keylayout` dans `~/Library/Keyboard Layouts/`.
2. **Réglages Système → Clavier → Sources de saisie → + → Autres → zBépo**.

### Android (clavier physique BT/USB)

Voir **[zelmano/bepo-android](https://github.com/zelmano/bepo-android)** — APK prêt à sideloader, layout identique à celui-ci.

Le format Android `.kcm` n'est pas généré par Kalamine ; il est maintenu à part.

## Statut

Projet personnel. Pas de support officiel, pas d'attente de PRs. N'hésite pas à fork si tu veux t'en inspirer.

## Licence

MIT.
