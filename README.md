# jsonl-runner

Feed a thousand prompts, get a thousand answers

Built for my own use; public in case it helps someone.

## Install

```bash
pip install -r requirements.txt
export OPENAI_API_KEY=sk-...
```

## What it does

- Retries failed items with backoff, logs them aside
- Idempotent: skips ids already present in the output
- Concurrent workers with a rate ceiling
- JSONL in, JSONL out: stream-safe for huge inputs

## Usage

```bash
python batch.py prompts.jsonl -o answers.jsonl --workers 4
```

## Project structure

```text
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   └── bug_report.md
│   ├── dependabot.yml
│   └── pull_request_template.md
├── docs/
│   └── development.md
├── tests/
│   └── test_smoke.py
├── .editorconfig
├── .gitattributes
├── .gitignore
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── SECURITY.md
├── batch.py
├── prompts.sample.jsonl
└── requirements.txt
```

## Notes

- mostly stable, edge cases remain

## License

MIT. Do whatever you want.
