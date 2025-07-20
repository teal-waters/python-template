# Contributing Guide

Thank you for your interest in contributing to this project! This guide outlines the best practices for contributing using a single-branch (main) workflow.

## Development Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd python-template
   ```

2. **Install Poetry** (if not already installed)
   ```bash
   curl -sSL https://install.python-poetry.org | python3 -
   ```

3. **Install dependencies**
   ```bash
   poetry install
   ```

4. **Install pre-commit hooks**
   ```bash
   poetry run pre-commit install
   ```

## Git Workflow (Feature Branch)

This project uses a **feature branch workflow** with `main` as the production branch that all changes are merged into via pull requests.

### Making Changes

1. **Start with the latest main**
   ```bash
   git checkout main
   git pull origin main
   ```

2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   # or for bug fixes
   git checkout -b fix/issue-description
   ```

3. **Make your changes on the feature branch**
   - Edit files as needed
   - Add new features or fix bugs
   - Follow the coding standards (enforced by pre-commit hooks)

4. **Test your changes**
   ```bash
   poetry run pytest
   poetry run pre-commit run --all-files
   ```

5. **Commit your changes**
   ```bash
   git add .
   git commit -m "descriptive commit message"
   ```

6. **Push your feature branch**
   ```bash
   git push origin feature/your-feature-name
   ```

7. **Open a pull request** targeting the `main` branch

### Commit Message Guidelines

- Use the present tense ("Add feature" not "Added feature")
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
- Limit the first line to 72 characters or less
- Reference issues and pull requests liberally after the first line

**Examples:**
```
Add user authentication system

Implement JWT-based authentication with login/logout endpoints.
Includes password hashing and session management.

Fixes #123
```

### Pull Request Process

1. **Open a pull request** from your feature branch targeting `main`
   - Use the provided PR template
   - Provide a clear description of your changes
   - Link any related issues

2. **Address review feedback**
   - Make changes on your feature branch
   - Push additional commits to update the PR
   ```bash
   git add .
   git commit -m "Address review feedback"
   git push origin feature/your-feature-name
   ```

3. **Merge requirements**
   - All CI checks must pass
   - At least one approving review required
   - No merge conflicts with main

4. **After merge, clean up**
   ```bash
   git checkout main
   git pull origin main
   git branch -d feature/your-feature-name
   git push origin --delete feature/your-feature-name
   ```

### Branch Naming Conventions

- `feature/description` - New features
- `fix/description` - Bug fixes
- `docs/description` - Documentation updates
- `refactor/description` - Code refactoring
- `test/description` - Test improvements

Examples:
- `feature/user-authentication`
- `fix/memory-leak-in-parser`
- `docs/api-documentation`

## Code Quality Standards

### Pre-commit Hooks
This project uses pre-commit hooks to ensure code quality. The following checks run automatically:

- **Black**: Code formatting
- **isort**: Import sorting
- **Flake8**: Linting
- **MyPy**: Type checking
- **YAML/TOML validation**
- **Trailing whitespace removal**

### Running Quality Checks Manually

```bash
# Format code
poetry run black .

# Sort imports
poetry run isort .

# Run linter
poetry run flake8

# Type checking
poetry run mypy .

# Run all pre-commit hooks
poetry run pre-commit run --all-files
```

### Testing

- Write tests for all new functionality
- Maintain test coverage above 80%
- Run tests locally before committing:
  ```bash
  poetry run pytest
  poetry run pytest --cov=python_template
  ```

## Project Structure

```
python-template/
├── python_template/          # Main package directory
│   ├── __init__.py
│   └── ...
├── tests/                    # Test directory
│   ├── __init__.py
│   └── ...
├── .github/                  # GitHub templates and workflows
│   ├── workflows/
│   └── pull_request_template.md
├── .pre-commit-config.yaml   # Pre-commit configuration
├── pyproject.toml           # Project configuration and dependencies
├── README.md
└── CONTRIBUTING.md
```

## Troubleshooting

### Pre-commit Hook Failures
If pre-commit hooks fail:
1. Review the error messages
2. Fix the issues (or let tools like Black fix them automatically)
3. Re-add and commit your changes

### Poetry Issues
- Update Poetry: `poetry self update`
- Clear cache: `poetry cache clear pypi --all`
- Reinstall dependencies: `poetry install --remove-untracked`

## Getting Help

- Open an issue for bugs or feature requests
- Check existing issues before creating new ones
- Be descriptive in issue titles and descriptions

## Code of Conduct

- Be respectful and inclusive
- Focus on constructive feedback
- Help maintain a positive community environment
