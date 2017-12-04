# Introduction

Billy is a framework written for WordPress plugin development which provides a MVC structure and OO (object orientated) programming methodologies. It follows a similar style to Laravel (and takes various assets from it to help). For that reason some documentation may link to external resources.

# Requirements

- Composer
- PHP 5.6+
- MySql

# Quick Install

1. Update the namespace in composer.json
2. Update the namespace in all files in /app, these are:
 - Helper.php
 - enqueue.php
 - loader.php
 - View.php
3. Navigate to the directory with terminal, run `composer install`.
4. Update `plugin.php` to use your plugin info at the top (leave named plugin)
5. Update `plugin.config.php` to define any constants. (leave named plugin.config)
6. Go to work!