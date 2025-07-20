# Python Template

A modern Python package template with Poetry, pre-commit hooks, and GitHub Actions CI/CD.

## Features

- 📦 **Poetry** for dependency management and packaging
- 🔧 **Pre-commit hooks** for code quality (Black, isort, Flake8, MyPy)
- 🧪 **Pytest** with coverage reporting
- 🚀 **GitHub Actions** for automated testing and checks
- 📋 **PR template** and contributing guidelines
- 🐍 **Python 3.12+** support

## Quick Start

### Using This Template

1. **Click "Use this template"** on GitHub or clone the repository:
   ```bash
   git clone <your-repo-url>
   cd python-template
   ```

2. **Install Poetry** (if not already installed):
   ```bash
   curl -sSL https://install.python-poetry.org | python3 -
   ```

3. **Install dependencies**:
   ```bash
   poetry install
   ```

4. **Set up pre-commit hooks**:
   ```bash
   poetry run pre-commit install
   ```

5. **Customize for your project**:
   - Update `pyproject.toml` with your project details
   - Rename the `python_template` directory to your package name
   - Update this README with your project information

## Development

### Running Tests
```bash
poetry run pytest
poetry run pytest --cov=python_template  # With coverage
```

### Code Quality
```bash
poetry run black .              # Format code
poetry run isort .              # Sort imports
poetry run flake8              # Lint code
poetry run mypy .              # Type check
poetry run pre-commit run --all-files  # Run all hooks
```

### Project Structure
```
python-template/
├── python_template/          # Main package (rename this)
├── tests/                    # Test directory
├── .github/                  # GitHub templates and workflows
├── .pre-commit-config.yaml   # Pre-commit configuration
├── pyproject.toml           # Project configuration
└── README.md
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for development workflow and guidelines.

## License

[Add your license information here]
