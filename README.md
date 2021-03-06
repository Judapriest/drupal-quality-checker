# Drupal Code Quality Checker
---

## Overview

Provides set of libraries to easily setup code quality checks based on [GrumPHP](https://github.com/phpro/grumphp) for Drupal module/theme/profile.

>*Note:* This library is aimed to help ecedi starterkit and distribution.


## Install

1. Add `judapriest/drupal-quality-checker` to `composer.json`: `composer require --dev judapriest/drupal-quality-checker`
2. Replace `grumphp.yml` in your project's root directory (not Drupal root directory) with `vendor/judapriest/drupal-quality-checker/grumphp.yml.dist`

That's it. Now, all tasks (listed below) run on every `git commit`.

>*Note:* As part of install, GrumPHP adds `pre-commit` hook to repository. Existing `pre-commit` might get [destroyed](https://github.com/phpro/grumphp/issues/416) when install/uninstall.

## Features

1. [PHPCS](https://github.com/squizlabs/PHP_CodeSniffer) with Drupal standard.
2. [PHPLint](http://www.icosaedro.it/phplint/)
3. [YAML Lint](http://www.yamllint.com/)
4. [Composer](https://github.com/composer/composer)
5. [JSONLint](https://jsonlint.com/)
6. [PHP Copy/Paste Detector (CPD)](https://github.com/sebastianbergmann/phpcpd)
7. [Composer Normalizer](https://packagist.org/packages/ergebnis/composer-normalize)


Long list of additional checks/validators available [here](https://github.com/phpro/grumphp/blob/master/doc/tasks.md#tasks-1).

## How to use

### Pre-configured
When installed (see #install), it's configure to run on every `git commit`. It will only analyse files you are commiting. 

### Stand alone run
You can also use `bin/grumphp run` from the root directory to analyse all existing file (minus the exclude or ignore files define in the grumphp.yml file).

## Sample

### Pass
![drupal-quality-checker-pass](https://user-images.githubusercontent.com/1220029/33808392-62b90710-dddd-11e7-9d0e-08f82e6e85b1.png)

### Fail
![drupal-quality-checker-fail](https://user-images.githubusercontent.com/1220029/33808391-62a4daec-dddd-11e7-8cf5-9c6b37f89893.png)


## Demo
Implemented in [Modal Configuration](https://github.com/vijaycs85/modal_config) module.

## Uninstall
1. You can remove the package with `composer remove judapriest/drupal-quality-checker --update-with-dependencies`.
2. Remove the `grumphp.yml` in project's root directory if it's there.
3. Modify the .git/hooks/pre-commit and .git/hooks/commit-msg if necessary
