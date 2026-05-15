Description of the project.

## Installation

### Download

This repository can be downloaded through GitHub by either using the website or terminal. To download on the website, navigate to the top of this page, click the green `Clone or download` button, and select `Download ZIP`. To install using the terminal, type:

```bash
git clone https://github.com/<org>/<project-name>.git
cd <project-name>
```

### Python dependencies

This repository uses Python 3.12. We recommend managing your environment with [Conda-forge](https://conda-forge.org)'s installer [Miniforge](https://conda-forge.org/download/).

Run the following from this repository's directory to create a virtual environment and install dependencies with Miniforge:

```bash
conda env create -f environment.yaml
conda activate <project-name>
```

The [environment.yaml](./environment.yaml) file specifies the Python version and delegates package installation to pip using [pyproject.toml](./pyproject.toml). No separate `pip install` step is needed.

Or, if you prefer not to use conda, you can use a standard [virtual environment](https://docs.python.org/3/tutorial/venv.html):

```bash
python3.12 -m venv venv
source venv/bin/activate
```

If using VS Code, open the repository folder and select the interpreter via **Command Palette → Python: Select Interpreter**, then choose `<project-name>` from the list.

Then install dependencies using one of the following two options:

#### Reproducible install (recommended)

Install from [requirements-lock.txt](./requirements-lock.txt) to get the exact package versions used in the verified environment:

```bash
pip install -r requirements-lock.txt
```

#### Standard install

Install directly from [pyproject.toml](pyproject.toml) with the latest compatible versions:

```bash
pip install .
```

A new requirements lock file can be generated with:

```bash
pip-compile --output-file=requirements-lock.txt pyproject.toml
```

## Testing

We use [pytest](https://docs.pytest.org/en/stable/) for testing. From the root directory, run:

```bash
pytest tests/
