# Community-maintained fork of CakePHP 2

Piece of Cake 2 is a community-maintained fork of CakePHP 2.x, providing PHP 8.x compatibility for existing legacy applications.

> [!IMPORTANT]
> This fork is only for maintaining existing legacy applications. Do not use CakePHP 2.x for new projects - use [CakePHP 5.x](https://cakephp.org/) instead.

## Documentation

- [pieceofcake2.github.io](https://pieceofcake2.github.io/) ([日本語](https://pieceofcake2.github.io/ja/)) - Project website with every package and its documentation site
- [CakePHP 2 Book](https://pieceofcake2.github.io/docs/) ([Markdown](https://github.com/pieceofcake2/docs/blob/2.x/docs/en/index.md)) - The CakePHP 2 Cookbook, updated for Piece of Cake 2 (English / Japanese)

## Features

- **PHP 8.x Support**: Full compatibility with modern PHP versions
- **Security Fixes**: Critical security vulnerabilities are addressed
- **Gradual Migration Path**: Supports incremental migration to CakePHP 5.x
- **Legacy Application Maintenance**: Keep your existing applications running safely

## Resources

Names link to the documentation site of each package (English, with a Japanese translation under `/ja/`), or to the GitHub repository where the package has no documentation site. "Markdown" links to the Markdown source of the documentation, which AI tools can read directly.

### Core Repositories

- [CakePHP](https://github.com/pieceofcake2/cakephp) - CakePHP 2.x framework
- [App Skeleton](https://pieceofcake2.github.io/app/) ([Markdown](https://github.com/pieceofcake2/app/blob/2.x/docs/README.md)) - Application skeleton
- [Plugin Skeleton](https://github.com/pieceofcake2/plugin) - Plugin skeleton
- [Bake Plugin](https://pieceofcake2.github.io/bake/) ([Markdown](https://github.com/pieceofcake2/bake/blob/1.x/docs/README.md)) - Code generation tool
- [Upgrade Plugin](https://pieceofcake2.github.io/upgrade/) ([Markdown](https://github.com/pieceofcake2/upgrade/blob/1.x/docs/README.md)) - Upgrade utility (CakePHP 1.3 to 2.0)

### Development Tools

- [PHPStan CakePHP](https://pieceofcake2.github.io/phpstan-cakephp2/) ([Markdown](https://github.com/pieceofcake2/phpstan-cakephp2/blob/main/docs/README.md)) - PHPStan extension for static analysis
- [PHPCS CakePHP2](https://pieceofcake2.github.io/phpcs-cakephp2/) ([Markdown](https://github.com/pieceofcake2/phpcs-cakephp2/blob/main/docs/README.md)) - PHP_CodeSniffer standard for CakePHP 2
- [Panther](https://pieceofcake2.github.io/panther/) ([Markdown](https://github.com/pieceofcake2/panther/blob/1.x/docs/README.md)) - End-to-End tests with Symfony Panther

### Maintained Plugins

All plugins are compatible with PHP 8.x.

#### Debugging

- [DebugKit Plugin](https://pieceofcake2.github.io/debug_kit/) ([Markdown](https://github.com/pieceofcake2/debug_kit/blob/2.x/docs/README.md)) - Debug toolbar

#### Infrastructure

- [Aws Plugin](https://pieceofcake2.github.io/aws/) ([Markdown](https://github.com/pieceofcake2/aws/blob/1.x/docs/README.md)) - AWS SDK integration
- [AsyncAws Plugin](https://pieceofcake2.github.io/async-aws/) ([Markdown](https://github.com/pieceofcake2/async-aws/blob/1.x/docs/README.md)) - AsyncAws integration, a lighter alternative to the Aws plugin
- [Bref Plugin](https://github.com/pieceofcake2/bref) - AWS Lambda deployment with Bref

#### Logging & Monitoring

- [Monolog Plugin](https://pieceofcake2.github.io/monolog/) ([Markdown](https://github.com/pieceofcake2/monolog/blob/2.x/docs/README.md)) - Monolog integration
- [Sentry Plugin](https://pieceofcake2.github.io/sentry/) ([Markdown](https://github.com/pieceofcake2/sentry/blob/1.x/docs/README.md)) - Error tracking and monitoring

#### Templating

- [TwigView Plugin](https://pieceofcake2.github.io/twig-view/) ([Markdown](https://github.com/pieceofcake2/twig-view/blob/2.x/docs/README.md)) - Twig template engine
- [CsvView Plugin](https://pieceofcake2.github.io/csv-view/) ([Markdown](https://github.com/pieceofcake2/csv-view/blob/2.x/docs/README.md)) - CSV view class

#### View Helpers

- [Markdown Plugin](https://pieceofcake2.github.io/markdown/) ([Markdown](https://github.com/pieceofcake2/markdown/blob/2.x/docs/README.md)) - Markdown helper
- [MenuBuilder Plugin](https://pieceofcake2.github.io/menu_builder/) ([Markdown](https://github.com/pieceofcake2/menu_builder/blob/2.x/docs/README.md)) - Navigation menu helper
- [Vite Plugin](https://pieceofcake2.github.io/vite/) ([Markdown](https://github.com/pieceofcake2/vite/blob/1.x/docs/README.md)) - Vite asset helper with dev server support
- [WebpackEncore Plugin](https://pieceofcake2.github.io/webpack-encore/) ([Markdown](https://github.com/pieceofcake2/webpack-encore/blob/1.x/docs/README.md)) - Webpack Encore asset helper

#### Forms & Validation

- [Xform Plugin](https://pieceofcake2.github.io/xform/) ([Markdown](https://github.com/pieceofcake2/xform/blob/2.x/docs/README.md)) - Extended form helper
- [Cakeplus Plugin](https://pieceofcake2.github.io/cakeplus/) ([Markdown](https://github.com/pieceofcake2/cakeplus/blob/2.x/docs/README.md)) - Form utilities and enhancements
- [Captcha Plugin](https://pieceofcake2.github.io/captcha/) ([Markdown](https://github.com/pieceofcake2/captcha/blob/1.x/docs/README.md)) - CAPTCHA widget and server-side verification with Cloudflare Turnstile (default), Google reCAPTCHA v2/v3 or hCaptcha
- [Purifiable Plugin](https://pieceofcake2.github.io/purifiable/) ([Markdown](https://github.com/pieceofcake2/purifiable/blob/1.x/docs/README.md)) - HTML sanitization of model fields with HTML Purifier

#### Database

- [Datasources Plugin](https://pieceofcake2.github.io/datasources/) ([Markdown](https://github.com/pieceofcake2/datasources/blob/2.x/docs/README.md)) - Additional datasources (CSV / TSV files, arrays and more)

#### Authentication and Authorization

- [Authenticate Plugin](https://pieceofcake2.github.io/authenticate/) ([Markdown](https://github.com/pieceofcake2/authenticate/blob/1.x/docs/README.md)) - Authentication classes
- [AclExtras Plugin](https://pieceofcake2.github.io/acl_extras/) ([Markdown](https://github.com/pieceofcake2/acl_extras/blob/2.x/docs/README.md)) - Console tools for managing ACL tables
- [AclMenu Plugin](https://pieceofcake2.github.io/acl_menu/) ([Markdown](https://github.com/pieceofcake2/acl_menu/blob/1.x/docs/README.md)) - Navigation menus of the actions allowed by ACL
- [Totp Plugin](https://pieceofcake2.github.io/totp/) ([Markdown](https://github.com/pieceofcake2/totp/blob/1.x/docs/README.md)) - Two-factor authentication with one-time passwords (TOTP)

#### Files

- [Upload Plugin](https://pieceofcake2.github.io/upload/) ([Markdown](https://github.com/pieceofcake2/upload/blob/2.x/docs/README.md)) - File upload handling
- [Imagine Plugin](https://pieceofcake2.github.io/imagine/) ([Markdown](https://github.com/pieceofcake2/imagine/blob/1.x/docs/README.md)) - Image processing library wrapper
- [CakePdf Plugin](https://pieceofcake2.github.io/cakepdf/) ([Markdown](https://github.com/pieceofcake2/cakepdf/blob/1.x/docs/README.md)) - PDF generation

#### SEO

- [Seo Plugin](https://pieceofcake2.github.io/seo/) ([Markdown](https://github.com/pieceofcake2/seo/blob/6.x/docs/README.md)) - Search engine optimization
- [Sitemap Plugin](https://pieceofcake2.github.io/sitemap/) ([Markdown](https://github.com/pieceofcake2/sitemap/blob/1.x/docs/README.md)) - Sitemap generation

#### I18n

- [Localized Plugin](https://pieceofcake2.github.io/localized/) ([Markdown](https://github.com/pieceofcake2/localized/blob/2.x/docs/README.md)) - Localization utilities

## Contributing

This project is maintained by the community. We welcome:

- Bug reports, especially PHP 8.x compatibility issues
- Security vulnerability reports
- Pull requests for fixes and improvements

*Keep your legacy applications running smoothly while preparing for the future*
