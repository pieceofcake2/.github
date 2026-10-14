# Contributing to Piece of Cake 2

Thank you for your interest in contributing. This guide applies to all
repositories in the [pieceofcake2](https://github.com/pieceofcake2)
organization, unless a repository has its own `CONTRIBUTING.md`. It is the
canonical contribution guide; the
[Contributing](https://pieceofcake2.github.io/docs/contributing) chapter of the
documentation links here.

## Scope

Piece of Cake 2 maintains CakePHP 2.x and its plugins for existing
applications. The original CakePHP 2.x reached its end of life, and the
CakePHP team no longer accepts issues or pull requests for it, so
contributions go to the `pieceofcake2/*` repositories. Contributions should
focus on:

- PHP 8.x compatibility
- Bug fixes and security fixes
- Keeping the tests passing on all supported PHP versions and databases
- Supporting a gradual migration path to CakePHP 5, for example with the
  modern directory layout that both CakePHP 2 and CakePHP 5 can use

New features are generally not added. For new projects, use CakePHP 5. If you
are not sure whether a change fits, open an issue first and ask.

## Reporting Issues

Open an issue in the repository the problem belongs to:

- [pieceofcake2/cakephp](https://github.com/pieceofcake2/cakephp/issues) for
  the framework
- [pieceofcake2/app](https://github.com/pieceofcake2/app/issues) for the
  application skeleton, and the other `pieceofcake2/*` repositories for Bake
  and the maintained plugins
- [pieceofcake2/docs](https://github.com/pieceofcake2/docs/issues) for the
  documentation

Do not report problems with the fork to cakephp/cakephp; CakePHP 2.x is no
longer maintained there.

Before you open an issue, search the existing issues, and check the
repository's `CHANGELOG.md` and `UPGRADE.md` (for the framework, also
[Migrating from CakePHP 2.10](https://pieceofcake2.github.io/docs/appendices/migrating-from-cakephp-2-10)):
the behavior you see may be an intended change of the fork.

Please include:

- The PHP version, the database, and the versions of the packages you use
  (`pieceofcake2/cakephp` and any plugin involved)
- What you did, what you expected and what happened instead, with the full
  error message
- A minimal piece of code or a test case that reproduces the problem, if
  possible. An issue that can be reproduced is much more likely to be fixed.

Do not use issues for general support questions; ask them on
[Stack Overflow](https://stackoverflow.com/questions/tagged/cakephp) instead.

### Reporting Security Issues

**Do not report security vulnerabilities in public issues, pull requests or
discussions.** Report them privately with GitHub's private vulnerability
reporting (the **Security** tab of the affected repository, then **Report a
vulnerability**). See the [security policy](SECURITY.md) for what to include
and how reports are handled. Vulnerabilities in the original CakePHP 2.x that
also affect the fork are in scope.

## Pull Requests

### Initial Setup

You need:

- Git
- PHP 8.0 or newer, with the `mbstring` extension (strongly recommended) and
  the PDO driver for the database you want to test against
- [Composer](https://getcomposer.org)
- For the framework's database tests: MySQL, PostgreSQL or SQL Server, or
  Docker to run them (SQLite needs no server)

PHPUnit, PHP_CodeSniffer with the CakePHP ruleset, and PHPStan (where the
repository uses it) are development dependencies, so Composer installs them.

Fork the repository on GitHub, clone your fork, and add the original
repository as the `upstream` remote so that you can stay up to date:

```bash
git clone git@github.com:YOURNAME/cakephp.git
cd cakephp
git remote add upstream https://github.com/pieceofcake2/cakephp.git
composer install
```

The framework's development dependencies require `pieceofcake2/cakephp` itself,
so on a branch whose name Composer can't map to a version (for example
`fix/something`), tell Composer which version the checkout is, as CI does:

```bash
COMPOSER_ROOT_VERSION=2.12.x-dev composer install
```

### Running the Tests

Tests run on PHPUnit 9.6:

```bash
vendor/bin/phpunit
```

Most plugin repositories run their tests with SQLite; see the repository's
README and `phpunit.xml.dist` for the configuration it expects.

The framework's test suite runs against the
[pieceofcake2/app](https://github.com/pieceofcake2/app) skeleton, which
Composer installs into `vendor/pieceofcake2/app` as a development dependency.
Copy the test database configuration into it:

```bash
cp tests/config/database.php vendor/pieceofcake2/app/config/
```

This configuration selects the database from the `DB` environment variable:
`mysql` (the default), `mysql80`, `pgsql`, `sqlite` or `sqlsrv`. SQLite uses
an in-memory database, so it needs no database server:

```bash
DB=sqlite vendor/bin/phpunit
```

For the other databases, start a server with the credentials and database
names listed in `tests/config/database.php` (the `compose.yml` file defines
Docker containers for all supported database servers), then set `DB`
accordingly:

```bash
DB=pgsql vendor/bin/phpunit
```

To run a single test file, pass its path to PHPUnit:

```bash
DB=sqlite vendor/bin/phpunit tests/TestCase/Utility/HashTest.php
```

Continuous integration runs the test suite on every supported PHP version and
database, and runs `phpcs`, for every pull request.

### Working on a Change

1. Create a topic branch from the default branch of the repository (for
   example `2.x` or `1.x`), with a descriptive name such as `fix-1234` or
   `php84-deprecations`:

   ```bash
   git fetch upstream
   git checkout -b fix-1234 upstream/2.x
   ```

2. Make your change:
   - Add or update tests. A bug fix needs a test that fails without the fix.
   - Follow the [coding standard](#coding-standard).
   - Keep the public API intact; see [Backwards Compatibility](#backwards-compatibility).
   - Keep your commits logical, with clear and concise commit messages.
3. Before you open the pull request, make sure that all of these pass:

   ```bash
   vendor/bin/phpcs     # coding standard (no errors and no warnings)
   vendor/bin/phpunit   # tests
   composer validate --strict
   ```

   Run PHPStan as well (`vendor/bin/phpstan`) if the repository has a PHPStan
   configuration.
4. If the repository has `CHANGELOG.md` or `UPGRADE.md`, describe your change
   under a `## Unreleased` heading at the top (add it if it is not there yet).
   Explain changes in behavior and what users need to do; migration steps go
   to `UPGRADE.md`.
5. If the default branch has moved on, update your branch with
   `git fetch upstream` and `git rebase upstream/2.x`, resolve any conflicts,
   and run the checks again.
6. Push the branch to your fork and open the pull request against the default
   branch, with a short summary of the change, how you tested it, and a link
   to the related issue if there is one.

Pull requests are reviewed by the maintainers and merged with a merge commit.

### Coding Standard

Code follows the [CakePHP coding standard](https://github.com/cakephp/cakephp-codesniffer)
(`cakephp/cakephp-codesniffer` ^5.0, based on PSR-12), with the CakePHP 2
specific exclusions defined in each repository's `phpcs.xml`. `phpcs` is the
authority: the change must pass `vendor/bin/phpcs` with no errors and no
warnings. Use `vendor/bin/phpcbf` to fix most violations automatically.

All code and comments are written in English. See
[Coding Standards](https://pieceofcake2.github.io/docs/contributing/cakephp-coding-conventions)
in the documentation for a description of the rules.

### Backwards Compatibility

Applications upgrade without changing their code wherever possible, so keep
the public API of CakePHP 2 intact:

- Do not remove or rename public classes, interfaces, methods or properties.
- Do not add required arguments to existing methods. If you need a new
  argument, add it with a default value at the end of the argument list.
- Do not reduce the visibility of methods or properties, and do not make
  classes or methods `final` or `abstract`.
- Do not add native return types to methods that applications may override,
  since overriding methods without them would then cause fatal errors.
- Avoid removing or renaming protected methods and properties. Applications
  extend framework classes often.

If a change that affects applications cannot be avoided, for example because
a newer PHP version or a security fix requires it, describe it in
`CHANGELOG.md` and the migration steps in `UPGRADE.md`.

## Branches and Releases

Each repository has a single maintained branch, its default branch (`2.x` for
the framework). Bug fixes, security fixes and compatibility changes are all
made on this branch, and pull requests target it. There are no separate
maintenance, development or feature branches.

Releases are tags on the default branch, published as GitHub releases and on
Packagist. For the framework, see the
[CHANGELOG](https://github.com/pieceofcake2/cakephp/blob/2.x/CHANGELOG.md) and
the [UPGRADE guide](https://github.com/pieceofcake2/cakephp/blob/2.x/UPGRADE.md).

## Documentation

The documentation at https://pieceofcake2.github.io/docs/ is maintained in
[pieceofcake2/docs](https://github.com/pieceofcake2/docs). Changes to the
English pages (`docs/en`) should also be made to the Japanese pages
(`docs/ja`). See the repository's
[README](https://github.com/pieceofcake2/docs#readme) for local preview and
the editing guidelines.

## License

By contributing, you agree that your contributions will be licensed under the
license of the repository you contribute to (MIT for the framework and most
plugins).
