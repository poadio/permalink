# poad permalink

`poad.json` est lu par le CLI poad (2.38.0 et plus) pour choisir la version d'engine à proposer, par canal :

```json
{
  "engine": {
    "stable": "0.28.0",
    "beta": "0.29.0-beta.1"
  }
}
```

- `stable` : la version proposée par `poad init`, `poad start` et `poad upgrade`. La baisser revient en arrière pour les nouveaux projets ; les projets existants ne changent jamais tout seuls.
- `beta` (facultatif) : proposée aux projets du canal beta (`channel = "beta"` dans `poad/config.toml`, `POAD_CHANNEL=beta` ou `poad upgrade channel=beta`), seulement si elle est plus récente que `stable`.

Sans clé `engine`, le CLI prend le dernier engine x.y.z publié sur Docker Hub. Le CLI garde la réponse 6 heures en cache.
