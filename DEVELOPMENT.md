# Development

## Getting Started

This tutorial shows you how to:
- Set up your development environment,
- Run scripts using `hatch`,
- Build the `phoenix` package.

### Set Up Development Environment

Set up your development environment using `pyenv` and `virtualenvwrapper`. We currently support Python 3.8 and above. Install a supported Python version, e.g., `3.10.8`, with
```shell
export PHOENIX_PYTHON_VERSION=<your-supported-python-version-here>
pyenv install $PHOENIX_PYTHON_VERSION
```
Set the global `pyenv` version with
```shell
pyenv global $PHOENIX_PYTHON_VERSION
```
Create a new virtual environment with
```shell
mkvirtualenv phoenix-env
```
Install `phoenix` in development mode (using the `-e` flag) and with development dependencies (using the `[dev]` extra) by running
```shell
pip install -e '.[dev]'
```
from the repository root.

### Learn to Run Scripts with `hatch`

`hatch` is the project management tool used to build `phoenix`. After installing and activating the `phoenix-env` virtual environment, view the project environments, dependencies and scripts defined in `pyproject.toml` with
```shell
hatch env show
```
Scripts belonging to the various environments can be run with
```shell
hatch run <env-name>:<script-name>
```
For example, you can check types with
```shell
hatch run type:check
```
You can fix styles with
```shell
hatch run style:fix
```
You can run tests with coverage with
```shell
hatch run test:coverage
```

### Build the `phoenix` Package

To build `phoenix`, run
```shell
hatch build
```
If successful, a source distribution (a tarball) and a Python `wheel` will appear in the `dist` folder at the repo base directory.

### Install the Built Package

We recommend using a separate virtual environment (e.g., `phoenix-test-env`) for installing and testing the builds created above.

To install `phoenix` from the source distribution (i.e., tarball), run
```shell
pip install /path/to/source/distribution/tarball.tar.gz
```

To install `phoenix` from the Python `wheel`, you must first install `wheel` with
```shell
pip install wheel
```
Then run
```shell
pip install /path/to/wheel.whl
```
(You should only install one of the source distribution or the `wheel` at a time.)

To make sure everything works, install `jupyter` with
```shell
pip install jupyter
```
and run the notebooks in the `examples` directory.

## Useful Resources
- [Hatch Quickstart](https://hatch.pypa.io/latest/)
- [Hatch CLI Reference](https://hatch.pypa.io/latest/cli/reference/)