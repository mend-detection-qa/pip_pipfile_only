# Test Case: Pip with Pipfile Only

## Package Manager
Pip (Pipenv-style)

## Python Version Detection
- **Source**: Pipfile (PRIORITY #4)
- **Expected Version**: 3.9 (from python_version) or 3.9.18 (from python_full_version)
- **Note**: No higher priority files present

## Files Present
- requirements.txt - Dependencies
- Pipfile - Contains both python_version = "3.9" and python_full_version = "3.9.18"
- Pipfile.lock - Pipenv lock file

## Test Purpose
Test Pipfile version detection with both python_version and python_full_version fields.
Validates handling of Pipenv projects (pip-based but uses Pipfile).

## Edge Case
Pipfile contains TWO version fields:
- python_version = "3.9" (major.minor)
- python_full_version = "3.9.18" (major.minor.patch)

Tool should handle both formats correctly.
