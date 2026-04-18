# zbepo

Variante personnelle du layout de clavier **bépo**, conçue pour allier l'ergonomie du bépo avec un accès direct aux chiffres (sans shift) et aux symboles de programmation fréquents.

Layout décrit avec [Kalamine](https://github.com/OneDeadKey/kalamine).

## Version

0.5.0 — refonte à partir d'un descripteur TOML source.

## Source

- `zbepo.toml` — descripteur Kalamine, source de vérité du layout.

## Génération

Avec [Kalamine](https://github.com/OneDeadKey/kalamine) installé :

```bash
kalamine zbepo.toml
```

Cela produit les pilotes associés (Windows MSKLC, XKB pour Linux, Karabiner pour macOS).

## Licence

À définir.
