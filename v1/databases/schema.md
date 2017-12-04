# Schema Builder

Databases are created using the Capsule class which is included in the framework by Default. This will allow us to provide updates to the databases based on a set of PHP statements. 

We can both create, update and delete databases using the Schema builder and therefore it provides us a powerful toolset. 

Typically, we'll call the Schema functions within our `app\activate.php` and `app/deactivate.php` to ensure that any of the changes are made when using the plugin.

## Basic Usage 

#### Creating Tables

```php
use Illuminate\Database\Capsule\Manager as Capsule;

Capsule::schema()->create('orders', function($table)
{
    $table->increments('id');
    $table->string('title');
});
```

#### Dropping Tables

```php
use Illuminate\Database\Capsule\Manager as Capsule;

Capsule::schema()->dropIfExists('orders');
```

## Further Reading

For more information on what is available, and how to work with the creation and update of tables, please read the [Schema](https://laravel.com/docs/5.0/schema) docs.