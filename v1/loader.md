# Loader

We can utilise actions and filters through out the plugin by declaring it in the action.php file. This uses a loader to make sure everything is loaded at the right time.

## Actions

The action method is used whenever you'd use a action within WordPress, for example, to add a menu item to the admin you may do something like this.

```php
<?php 

$loader->action([
  'method' => 'admin_menu',
  'uses'   => [__NAMESPACE__ . '\Controllers\AdminController', 'menu']
]);
```

When WordPress triggers the action `admin_menu`, this will find the controller `app\Controllers\AdminController` and reference the `menu` function within it. 

## Filters

The filter method is used whenever you'd use a filter within WordPress, for example, to modify the output of `the_content` we may do something along the lines of this.

```php
<?php 

$loader->filter([
  'method' => 'the_content',
  'uses'   => [__NAMESPACE__ . '\Controllers\AdminController', 'content']
]);
```

When WordPress triggers the action `the_content`, this will find the controller `app\Controllers\AdminController` and reference the `content` function within it. 

## Available Arguments

The accepted arguments for the both actions and filters are are:

|Key|Purpose|
|---|---|
|method|Refers to the method of the action.|
|uses|Refers to the function you want to use.|
|priority|The priority of the action.|
|args|Any arguments you need to pass|

