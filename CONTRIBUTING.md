# Contributing to manasight-corpus

Contributions are welcome! Whether it's a bug report, a new log file, or a documentation improvement, we appreciate your help.

## Contributing Log Files

This corpus accepts sanitized MTG Arena `Player.log` captures. Each file helps improve parser reliability across game modes, patch versions, and edge cases.

### What we accept

- MTG Arena `Player.log` captures (any game mode, any patch version)
- Files must be gzip-compressed: `*.log.gz`
- File naming convention: `session_YYYY-MM-DD_HHMM[_suffix].log.gz`

### How to contribute

1. Fork the repository and create a feature branch
2. Sanitize your log file locally using [`manasight-parser`](https://github.com/manasight/manasight-parser)'s `scrub` command
3. Place the compressed file in the `corpus/` directory
4. Open a pull request against `main`

Sanitization is also applied automatically on merge, so you don't need to get it perfect — but please make a best effort to remove personal information before submitting.

### What gets sanitized

The scrub process removes personally identifiable information including:

- Account IDs and display names
- Email addresses
- Authentication tokens and session IDs

## Reporting Issues

Open a [GitHub issue](https://github.com/manasight/manasight-corpus/issues) with:

- A clear description of the problem
- Relevant details (file name, error output, etc.)

## Licensing of Contributions

By submitting a pull request, you agree that your contributions are licensed under the same terms as the project: [MIT](LICENSE-MIT) OR [Apache-2.0](LICENSE-APACHE), at the user's option.

## Code of Conduct

This project follows the [Contributor Covenant Code of Conduct](CODE_OF_CONDUCT.md).
