# retide

Opinionated log housekeeping tool with dry-run support

Small but I use it weekly.

## Features

- Dry-run mode shows what would happen, touches nothing
- Exit codes friendly for cron and CI
- Archive matched logs into a timestamped .tar.gz
- Filter by age (--older-than) or size (--larger-than)
- Scan directories for log files by glob pattern

## Examples

```bash
# show what would be cleaned, change nothing
logwash ./logs --older-than 30 --dry-run

# archive logs older than 30 days
logwash ./logs --older-than 30 --archive ./backup
```

## Installation

```bash
pip install -r requirements.txt
python -m logwash --help
```

## Project structure

```text
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   └── bug_report.md
│   ├── workflows/
│   │   └── ci.yml
│   └── pull_request_template.md
├── docs/
│   ├── configuration.md
│   ├── development.md
│   ├── faq.md
│   └── usage.md
├── examples/
│   └── quickstart.md
├── logwash/
│   ├── __init__.py
│   ├── __main__.py
│   ├── cli.py
│   └── utils.py
├── tests/
│   └── test_cli.py
├── .gitignore
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── pyproject.toml
└── requirements.txt
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```

## Notes

- mostly stable, edge cases remain

## License

MIT. Do whatever you want.
