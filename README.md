# Glide Optimizer Manipulator

[![Author](http://img.shields.io/badge/author-@yannikfirre-blue.svg?style=flat-square)](https://github.com/InfinityWebMe)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE)
[![Packagist Version](https://img.shields.io/packagist/v/infinityweb/glide-optimizer.svg?style=flat-square)](https://packagist.org/packages/infinityweb/glide-optimizer)

This manipulator uses ps/image-optimizer package to minify resources.

## Installation

```bash
composer require infinityweb/glide-optimizer
```

## Usage

```php

    use League\Glide\Responses\SymfonyResponseFactory;
    use League\Flysystem\Filesystem;

    $cache = new Filesystem('cache/');
    $source = new Filesystem('source/');

    $imageManager = new Intervention\Image\ImageManager([
        'driver' => 'imagick',
    ]);

    $manipulators = [
        new League\Glide\Manipulators\Size(2000 * 2000),
        new League\Glide\Manipulators\Encode(),
        new Infinityweb\Glide\Optimizer\OptimizerManipulator(),
    ];

    // Setup Glide server
    $server = new League\Glide\Server(
            $source, $cache, new League\Glide\Api\Api($imageManager, $manipulators)
    );

```