# Glide Optimizer Manipulator

[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE)
[![Packagist Version](https://img.shields.io/packagist/v/zestic/glide-optimizer.svg?style=flat-square)](https://packagist.org/packages/zestic/glide-optimizer)

This manipulator uses spatie/image-optimizer package to minify resources.

Forked from https://github.com/infinityweb/glide-optimizer

## Installation

- Recommend convert packages:
Look in the [Spatie installation instructions](https://github.com/spatie/image-optimizer?tab=readme-ov-file#installation)

- Require this package with composer:
```bash
composer require zestic/glide-optimizer
```

## Usage

```php
$server = League\Glide\ServerFactory::create([
    'source' => 'path/to/source/folder',
    'cache' => 'path/to/cache/folder',
]);

$manipulators = $server->getApi()->getManipulators();
$manipulators[] = new Zestic\Glide\Optimizer\OptimizerManipulator();

$server->getApi()->setManipulators($manipulators);
```


For better optimization use imagick driver.
