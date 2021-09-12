# coefficient-cookiecutter

[Cookiecutter](https://github.com/cookiecutter/cookiecutter) template for Coefficient projects.

  - GitHub repo: [https://github.com/CoefficientSystems/coefficient-cookiecutter/]


## Usage

```bash
# Install cookiecutter
pipx install cookiecutter

# Install from local
cookiecutter /path/to/coefficient-cookiecutter/

# Install from repo
cookiecutter https://github.com/CoefficientSystems/coefficient-cookiecutter
```

## Contributing

This cookiecutter project is self-referential (!) and conforms to the guidelines outlined in the
generated cookiecutter documentation. Please refer to [{{cookiecutter.repo_name}}/README.md] and
[{{cookiecutter.repo_name}}/docs/] for advice on how to contribute.


## Manual test

```bash
pipx install cookiecutter
cookiecutter /path/to/coefficient-cookiecutter/
# Use project defaults
cd coefficient-project

# Install Python & dependencies
pyenv shell $(cat .python-version)
python -V  # check this is the correct version of Python
mkvirtualenv $(cat .venv)
python -V  # check this is the correct version of Python
python -m pip install --upgrade pip
poetry install --no-root --remove-untracked

# Run tests
pytest

# Test towncrier (if installed)
towncrier create 123.added --edit
# Write something, save, close
towncrier build --version=0.2
# Confirm your update is now in CHANGELOG.md

# Clean up
deactivate
rmvirtualenv $(cat .venv)
cd ..
rm -r ./coefficient-project
```
