# Security Policy

This policy applies to all repositories in the [pieceofcake2](https://github.com/pieceofcake2)
organization, including [pieceofcake2/cakephp](https://github.com/pieceofcake2/cakephp)
and the plugin forks, unless a repository has its own `SECURITY.md`.

## Supported Versions

Security fixes are released for the latest release of each package.
For `pieceofcake2/cakephp`, this is the latest `2.x` release.

The original CakePHP 2.x reached End of Life in June 2021 and no longer receives
security fixes from the CakePHP team. Vulnerabilities found in the original
CakePHP 2.x that also affect this fork are in scope.

## Reporting a Vulnerability

**Please do not report security vulnerabilities through public GitHub issues,
pull requests or discussions.**

Report them privately with GitHub's private vulnerability reporting:

1. Open the repository that is affected (for example
   [pieceofcake2/cakephp](https://github.com/pieceofcake2/cakephp)).
2. Go to the **Security** tab and click **Report a vulnerability**.

Please include as much of the following as you can:

- The affected package and version
- The type of issue (e.g. XSS, CSRF, SQL injection)
- The affected file(s) and code location
- Steps to reproduce, or a proof of concept
- The impact, including how an attacker could exploit the issue

## Disclosure Process

1. We confirm the report and determine the affected versions.
2. We prepare a fix and release it.
3. We publish a GitHub security advisory, and request a CVE when appropriate.

Please keep the details private until a fix has been released.

Fixed vulnerabilities are listed in the documentation:
https://pieceofcake2.github.io/docs/security/fixes.html
