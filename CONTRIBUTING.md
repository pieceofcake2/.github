# Contributing to Piece of Cake 2

Thank you for your interest in contributing. This guide applies to all
repositories in the [pieceofcake2](https://github.com/pieceofcake2)
organization, unless a repository has its own `CONTRIBUTING.md`.

## Scope

Piece of Cake 2 maintains CakePHP 2.x and its plugins for existing
applications. Contributions should focus on:

- PHP 8.x compatibility
- Bug fixes and security fixes
- Supporting a gradual migration path to CakePHP 5

New features are generally not added. If you are not sure whether a change
fits, open an issue first and ask.

## Reporting Issues

Open an issue in the repository the problem belongs to, for example
[pieceofcake2/cakephp](https://github.com/pieceofcake2/cakephp/issues) for the
framework. Please include:

- The PHP version and the package versions you use
- What you did, what you expected and what happened instead
- A minimal piece of code that reproduces the problem, if possible

**Do not report security vulnerabilities in public issues.** See the
[security policy](SECURITY.md).

## Pull Requests

1. Fork the repository and create a branch from the default branch
   (for example `2.x` or `1.x`).
2. Install the dependencies:

   ```bash
   composer install
   ```

3. Make your change, and add or update tests for it.
4. Before you open the pull request, make sure that all of these pass:

   ```bash
   vendor/bin/phpcs     # coding standard (no errors and no warnings)
   vendor/bin/phpunit   # tests
   composer validate --strict
   ```

   Run PHPStan as well if the repository has a PHPStan configuration.
5. If the repository has `CHANGELOG.md` or `UPGRADE.md`, describe your change
   in the `Unreleased` section. Explain changes in behavior and what users
   need to do.
6. Open the pull request against the default branch, with a short summary of
   the change and how you tested it.

### Coding Standard

Code follows the [CakePHP coding standard](https://github.com/cakephp/cakephp-codesniffer)
(`cakephp/cakephp-codesniffer` ^5.0), with the CakePHP 2 specific exclusions
defined in each repository's `phpcs.xml`. Use `vendor/bin/phpcbf` to fix most
violations automatically.

See [Coding Standards](https://pieceofcake2.github.io/docs/contributing/cakephp-coding-conventions)
in the documentation for details.

### Tests

Tests run on PHPUnit 9.6. Most repositories can run their tests with SQLite;
see the repository's README and `phpunit.xml.dist` for the database
configuration it expects.

## Documentation

The documentation at https://pieceofcake2.github.io/docs/ is maintained in
[pieceofcake2/docs](https://github.com/pieceofcake2/docs). Changes to the
English pages (`docs/en`) should also be made to the Japanese pages
(`docs/ja`). See the repository's README for the editing guidelines.

## License

By contributing, you agree that your contributions will be licensed under the
license of the repository you contribute to.
