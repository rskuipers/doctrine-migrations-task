# Doctrine Migrations Task

[![Latest Stable Version](https://poser.pugx.org/soy-php/doctrine-migrations-task/v/stable)](https://packagist.org/packages/soy-php/doctrine-migrations-task) [![Total Downloads](https://poser.pugx.org/soy-php/doctrine-migrations-task/downloads)](https://packagist.org/packages/soy-php/doctrine-migrations-task) [![Latest Unstable Version](https://poser.pugx.org/soy-php/doctrine-migrations-task/v/unstable)](https://packagist.org/packages/soy-php/doctrine-migrations-task) [![License](https://poser.pugx.org/soy-php/doctrine-migrations-task/license)](https://packagist.org/packages/soy-php/doctrine-migrations-task)

## Introduction
This is a [Doctrine Migrations](https://github.com/doctrine/migrations) task for [Soy](https://github.com/soy-php/soy)

## Usage
Include `soy-php/doctrine-migrations-task` in your project with composer:

```sh
$ composer require soy-php/doctrine-migrations-task
```

Then in your recipe you can use the task as follows:
```php
<?php

$recipe = new \Soy\Recipe();

$recipe->component('default', function (\Soy\DoctrineMigrations\MigrateTask $migrateTask) {
    $migrateTask
        ->setBinary('../test/vendor/bin/doctrine-migrations')
        ->setCommandNamespace('migrations:')
        ->setConfiguration('../test/migrations.yml')
        ->setDbConfiguration('../test/db.php')
        ->setVerbose(true)
        ->run();
});

return $recipe;
```
