# Query Builder

The database query builder provides a convenient, fluent interface to creating and running database queries. It can be used to perform most database operations in your application.

## Usage

Below are some basic examples of how to use the `DB` query builder within the framework. To load the DB class within your Controllers, you'll need to add the Use first, you can do this with the following.

```php
<?php

namespace MyPlugin\Controllers;

use Billy\Framework\Framework\Facades\DB;
```

#### Retrieving All Rows
```php
$users = DB::table('users')->get();

foreach ($users as $user)
{
    var_dump($user->name);
}
```

#### Returning a Single User

```php
$user = DB::table('users')->where('name', 'John')->first();
```

## Further Reading

For further reading on how to use the Query Builder, please review the [Docs](https://laravel.com/docs/5.0/queries). 