# tw-clean

Keep Your Tweets Clean

## required

- [twitter/twurl](https://github.com/twitter/twurl) (authorized)
    - [cympfh/tw](https://github.com/cympfh/tw)
- [jq](https://stedolan.github.io/jq/)

## usage examples

```bash
tw-clean --name cympfh --margin 1800 --interval 60 --rule '.text | startswith("@")'
```

Remove all `cympfh` 's tweets (authorized in `twurl`) older than `1800` sec (=30min) and which matches the rule every `60` sec.
The rule is written in `jq`.

```bash
--rule (.extended_entities.media | length) == 0
```

no media (images)
