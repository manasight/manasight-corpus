# manasight-corpus

Sanitized MTG Arena game log corpus for testing [manasight-parser](https://github.com/manasight/manasight-parser), the log parsing engine behind [Manasight](https://manasight.gg).

## What is this?

This repository contains sanitized `Player.log` captures from MTG Arena. These files serve as a real-world test corpus for parser smoke testing, ensuring compatibility across game modes, patch versions, and edge cases.

All log files have personally identifiable information (account IDs, display names, tokens) removed via the parser's `scrub` module.

## How the corpus is consumed

- **CI smoke tests** — [manasight-parser](https://github.com/manasight/manasight-parser) runs its parser against every file in this corpus to catch regressions
- **Release tarballs** — tagged releases bundle the corpus for offline testing

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
