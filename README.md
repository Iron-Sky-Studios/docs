<div align="center">
    <h1>Docs</h1>
    <p>All things documentation</p>
    <p>
        <a href="https://github.com/Iron-Sky-Studios/docs/issues/new">Report Bug</a>
        ·
        <a href="https://github.com/Iron-Sky-Studios/docs/issues/new">Request Feature</a>
        ·
        <a href="https://github.com/Iron-Sky-Studios/docs/discussions">Ask Question</a>
    </p>
</div>

<br>

### Supported Python version

```bash
python==3.11
```

<br>

## Setup
### Install Python Dependencies

```bash
python3 -m venv .venv

# Linux/Mac
. .venv/bin/activate

# Windows
. .venv/Scripts/activate

python3 -m pip install -r requirements.txt
```

### Install Pre-commit Hook

```bash
pre-commit install
```

<br>

## Running on local

```bash
mkdocs serve
```

<br>

## Manual Deployment to Github Pages

```bash
mkdocs gh-deploy
```
