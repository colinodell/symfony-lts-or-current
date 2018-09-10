Enforcing LTS or Current Versions of the Symfony Components
===========================================================

Using `symfony/symfony` makes Composer install all Symfony Components, all in
the same version. But when using the standalone packages, Composer might
install dependencies in a different major version (`symfony/http-kernel` v3.4
is compatible with `symfony/event-dispatcher` v4.0 for instance).

This is fine if you don't want to stick to Symfony LTS versions and if your
code does not use these transitive dependencies.

This package allows you to force Composer to always use an LTS or current
version of Symfony Components, whether they are explicitly listed as a
project's dependency or installed transitively.

Note that this package is meant to be used by projects. Library authors SHOULD
NOT use it, except maybe in the `"require-dev"` Composer section.

This is similar to how [`symfony/lts`](https://github.com/symfony/lts) works,
but instead allows mixing and matching of different major versions provided
they are all LTS or current. See <https://symfony.com/roadmap> for the latest
information on supported versions.

Usage
-----

Use the Composer command line:

```bash
composer require colinodell/symfony-lts-or-current dev-master
```

Versioning Policy
------------------

Because support for LTS and current versions changes over time, this package
is only available as `dev-master`.
