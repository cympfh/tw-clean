# tw-clean

Keep Your Tweets Clean

## required

- [twitter/twurl](https://github.com/twitter/twurl)
- [cympfh/tw](https://github.com/cympfh/tw) 
- [jq](https://stedolan.github.io/jq/)

## usage examples

```bash
tw-clean --name cympfh --margin 1800 --interval 60 --rule '.text | startswith("@")'
```

Remove all `cympfh` 's tweets (authorized in `twurl`) older than `1800` sec (=30min) and which matches the rule every `60` sec.

### Rules

The rule is written in `jq`.

#### Examples

Remove all tweets without media/images

```bash
--rule (.extended_entities.media | length) == 0
```

Tweets (without media/images) OR (text starts with `.`)

```bash
--rule (.extended_entities.media | length) == 0 or (.text | startswith("."))
```

Tweets NOT (text start with `@`)

```bash
--rule (.text | startswith("@") | not)
```

# tw-trim

Just Recent `n` tweets will remain.
