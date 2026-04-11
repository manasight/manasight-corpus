# manasight-corpus

Sanitized MTG Arena game log corpus for testing [manasight-parser](https://github.com/manasight/manasight-parser), the log parsing engine behind [Manasight](https://manasight.gg).

## What is this?

This repository contains sanitized `Player.log` captures from MTG Arena. These files serve as a real-world test corpus for parser smoke testing, ensuring compatibility across game modes, patch versions, and edge cases.

All log files have personally identifiable information (account IDs, display names, tokens) removed via [manasight-parser](https://github.com/manasight/manasight-parser)'s `scrub` module.

## How it works

### Adding logs

1. Fork the repo, sanitize your `Player.log` with manasight-parser's `scrub` binary, compress it (`gzip`), and place it in `corpus/`
2. Open a PR — CI auto-sanitizes files via [`check-log-sanitization.yml`](.github/workflows/check-log-sanitization.yml) and validates naming conventions
3. See [CONTRIBUTING.md](CONTRIBUTING.md) for details

### Release publishing

When a PR that adds or updates `corpus/` files is merged to `main`, [`publish-corpus.yml`](.github/workflows/publish-corpus.yml) automatically:
1. Bundles all `corpus/*.log.gz` files into a tarball
2. Creates a new GitHub release with an auto-incremented tag (`manasight-corpus-v1`, `v2`, ...)

### Automatic parser baseline updates

After publishing a release, the workflow triggers [manasight-parser](https://github.com/manasight/manasight-parser)'s smoke test CI via `repository_dispatch`. The full pipeline:

```
corpus PR merged → publish-corpus.yml → GitHub Release
                                       → repository_dispatch → parser smoke test
                                                              → ratchet comparison
                                                              → baseline PR (if improved)
```

This means new log files flow through to parser coverage updates without manual intervention.

### Secrets

| Secret | Repo | Purpose |
|--------|------|---------|
| `PARSER_DISPATCH_TOKEN` | manasight-corpus | PAT with `contents: write` on manasight-parser, used to trigger `repository_dispatch` |
| `BASELINE_PR_TOKEN` | manasight-parser | PAT used by parser CI to open baseline update PRs |

## Repository structure

```text
manasight-corpus/
├── corpus/           # Sanitized .log.gz files
├── CONTRIBUTING.md   # How to contribute log files
├── README.md
├── LICENSE-MIT
└── LICENSE-APACHE
```

## Contributing

We welcome log file contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for how to sanitize and submit your MTG Arena logs.

## License

Licensed under either of

- Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE) or <http://www.apache.org/licenses/LICENSE-2.0>)
- MIT license ([LICENSE-MIT](LICENSE-MIT) or <http://opensource.org/licenses/MIT>)

at your option.

> This project is not affiliated with, endorsed by, or associated with Wizards of the Coast, Hasbro, or Magic: The Gathering Arena. All trademarks are the property of their respective owners.
