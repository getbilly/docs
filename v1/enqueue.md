# Enqueue

We use Enqueue to handle how WordPress loads Scripts and Styles for your plugin. To enqueue you must supply the minimum of a Source and a Name. The Source takes a URL, to use a relative path from `resources/assets` folder we wrap with the `Helper::assetUrl()` function.

You can enqueue scripts and styles in one of three places, Front (theme), Admin, Login.

## Front

```php
<?php 

$enqueue->front([
	'as'   => 'plugin',
	'src'  => Helper::assetUrl('css/style.css'),
]);
```

## Admin

```php
<?php 

$enqueue->admin([
	'as'   => 'plugin-admin',
	'src'  => Helper::assetUrl('js/plugin-admin.js'),
    'uses' => ['jquery']
]);
```

## Login

```php
<?php 

$enqueue->login([
	...
]);
```