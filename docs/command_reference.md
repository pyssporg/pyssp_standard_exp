# Command Reference

This page is for maintainers and contributors who need the common repository commands.

There is currently no end-user CLI. Interaction is through the Python API.

## Environment

Use the repo-local virtual environment when it exists:

```bash
. venv/bin/activate
```

Install the package in editable mode with maintainer tools:

```bash
pip install -e ".[dev]"
```

## Tests

Run the full test suite:

```bash
pytest
```

Run one focused test module:

```bash
pytest tests/ssp1/facade/test_ssv_ssp1.py
```

Run one test by name:

```bash
pytest tests/ssp1/orchestration/test_ssp.py -k external_parameter
```

## Lint

Lint the package and tests with ruff:

```bash
ruff check src tests
```

The configuration is the repo-root `ruff.toml`. Ruff is not part of the `[dev]`
extra, so install it with `pip install ruff` when it is not already available.

## Documentation

Build the documentation locally (requires the `[dev]` extra):

```bash
pip install -e ".[dev]"
sphinx-build docs _build
```

## Packaging

Install the package from the repo:

```bash
pip install .
```

Build source and wheel distributions:

```bash
python -m build
```

After packaging changes, install the built wheel in a fresh environment and verify the public imports:

```bash
python -m venv /tmp/pyssp_standard_install
/tmp/pyssp_standard_install/bin/python -m pip install dist/*.whl
/tmp/pyssp_standard_install/bin/python -c "from pyssp_standard.facades.fmu import FMU; from pyssp_standard import SSD, SSP, SSV"
```
