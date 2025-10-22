# Contributing to SM - Change Admin Colors

Thank you for your interest in contributing to this WordPress plugin! This document provides guidelines and instructions for contributing.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Workflow](#development-workflow)
- [Commit Guidelines](#commit-guidelines)
- [Pull Request Process](#pull-request-process)
- [Coding Standards](#coding-standards)
- [Testing](#testing)

## Code of Conduct

By participating in this project, you agree to maintain a respectful and inclusive environment for all contributors.

## Getting Started

### Prerequisites

- PHP 7.4 or higher
- Node.js 20.18.1 or higher
- pnpm 9.0.0 or higher
- Git
- WordPress 5.0 or higher

### Initial Setup

1. **Fork the repository** on GitHub

2. **Clone your fork**:

   ```bash
   git clone git@github.com:YOUR_USERNAME/smarty-change-admin-colors.git
   cd smarty-change-admin-colors
   ```

3. **Add upstream remote**:

   ```bash
   git remote add upstream git@github.com:mnestorov/smarty-change-admin-colors.git
   ```

4. **Install Node.js dependencies**:

   ```bash
   pnpm install
   ```

5. **Install Composer dependencies**:

   ```bash
   composer install
   ```

## Development Workflow

### Branching Strategy

- `main` - Stable production releases
- `develop` - Pre-release development branch
- `feature/*` - New features
- `fix/*` - Bug fixes
- `docs/*` - Documentation updates

### Creating a Feature Branch

```bash
git checkout main
git pull upstream main
git checkout -b feature/your-feature-name
```

### Keeping Your Fork Updated

```bash
git checkout main
git pull upstream main
git push origin main
```

## Commit Guidelines

This project uses [Conventional Commits](https://conventionalcommits.org/) for automated versioning and changelog generation.

### Commit Message Format

```text
<type>(<scope>): <subject>

<body>

<footer>
```

### Commit Types

- `feat` - New feature (minor version bump)
- `fix` - Bug fix (patch version bump)
- `docs` - Documentation changes (patch version bump)
- `style` - Code style changes (patch version bump)
- `refactor` - Code refactoring (patch version bump)
- `perf` - Performance improvements (patch version bump)
- `test` - Test additions/changes (no release)
- `chore` - Maintenance tasks (no release)
- `ci` - CI/CD changes (no release)
- `build` - Build system changes (no release)
- `revert` - Revert previous commit (patch version bump)

### Breaking Changes

For major version bumps, include `BREAKING CHANGE:` in the commit footer:

```bash
git commit -m "feat: redesign color scheme system

BREAKING CHANGE: The color configuration API has changed.
Custom color filters must be updated to use the new format."
```

### Using Interactive Commits

We recommend using Commitizen for properly formatted commits:

```bash
pnpm run commit
```

This will guide you through creating a valid commit message.

### Commit Message Rules

- Subject must be lowercase
- Subject must not end with a period
- Header max 200 characters
- Body must have leading blank line
- Footer must have leading blank line

### Examples

**Feature:**

```bash
git commit -m "feat: add ability to customize environment label text"
```

**Bug Fix:**

```bash
git commit -m "fix: resolve admin bar color not applying on multisite"
```

**Documentation:**

```bash
git commit -m "docs: update installation instructions with composer method"
```

**Multiple Changes:**

```bash
git commit -m "feat: enhance color picker functionality

- Add color picker UI in settings
- Support custom hex colors
- Add color preview
- Save colors to user meta

Closes #123"
```

## Pull Request Process

### Before Submitting

1. **Ensure your code follows WordPress Coding Standards**:

   ```bash
   composer run lint
   ```

2. **Fix any coding standard issues**:

   ```bash
   composer run format
   ```

3. **Test your changes** in a WordPress environment

4. **Update documentation** if needed

5. **Ensure all commits follow conventional format**

### Submitting a Pull Request

1. **Push your branch** to your fork:

   ```bash
   git push origin feature/your-feature-name
   ```

2. **Create a Pull Request** on GitHub:
   - Go to your fork on GitHub
   - Click "Pull Request" button
   - Select your branch
   - Fill in the PR template

3. **PR Title Format**:
   - Use conventional commit format
   - Example: `feat: add custom color picker`

4. **PR Description** should include:
   - What changes were made
   - Why the changes are needed
   - Related issue numbers (if any)
   - Screenshots (for UI changes)
   - Testing instructions

### PR Review Process

- Maintainers will review your PR
- Address any requested changes
- Once approved, maintainers will merge
- Semantic-release will automatically create a release

## Coding Standards

### PHP Code Style

This project follows [WordPress Coding Standards](https://developer.wordpress.org/coding-standards/wordpress-coding-standards/php/).

**Check code style:**

```bash
composer run lint
```

**Auto-fix issues:**

```bash
composer run format
```

### Best Practices

- Use WordPress core functions when available
- Prefix all functions with `smarty_`
- Escape all output using appropriate functions (`esc_html`, `esc_attr`, etc.)
- Sanitize all input
- Use nonces for form submissions
- Follow WordPress naming conventions
- Add inline documentation for functions
- Keep functions focused and small

### File Organization

```text
smarty-change-admin-colors/
├── smarty-change-admin-colors.php  # Main plugin file
├── README.md                        # Plugin documentation
├── CONTRIBUTING.md                  # This file
├── CHANGELOG.md                     # Auto-generated by semantic-release
├── LICENSE                          # GPL-2.0+ license
├── composer.json                    # PHP dependencies
├── package.json                     # Node.js dependencies
└── .github/
    └── workflows/
        └── release.yml              # Automated release workflow
```

## Testing

### Manual Testing

1. **Install the plugin** in a WordPress environment
2. **Test all environments**:
   - Local (orange)
   - Development (blue)
   - Staging (purple)
   - Production (green)
3. **Test in different scenarios**:
   - Single site
   - Multisite
   - Different WordPress versions
   - Different PHP versions

### Testing Environment Types

Set the environment in `wp-config.php`:

```php
define('WP_ENVIRONMENT_TYPE', 'local');      // Orange
define('WP_ENVIRONMENT_TYPE', 'development'); // Blue
define('WP_ENVIRONMENT_TYPE', 'staging');     // Purple
define('WP_ENVIRONMENT_TYPE', 'production');  // Green
```

## Reporting Issues

### Bug Reports

When reporting bugs, include:

- WordPress version
- PHP version
- Plugin version
- Environment type
- Steps to reproduce
- Expected behavior
- Actual behavior
- Screenshots (if applicable)
- Error messages (if any)

### Feature Requests

When requesting features, include:

- Clear description of the feature
- Use case and benefits
- Possible implementation approach
- Examples from other plugins (if applicable)

## Questions?

- **Issues**: [GitHub Issues](https://github.com/mnestorov/smarty-change-admin-colors/issues)
- **Discussions**: [GitHub Discussions](https://github.com/mnestorov/smarty-change-admin-colors/discussions)
- **Email**: <mbnestorov@gmail.com>

## License

By contributing, you agree that your contributions will be licensed under the GPL-2.0+ License.

## Recognition

Contributors will be recognized in release notes and the project README.

Thank you for contributing! 🎉
