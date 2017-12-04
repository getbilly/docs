# Eloquent

The Eloquent ORM included with framework provides a beautiful, simple [ActiveRecord](https://en.wikipedia.org/wiki/Active_record_pattern) implementation for working with your database. Each database table has a corresponding "Model" which is used to interact with that table.

## Basic Usage

To get started, create an Eloquent model. Models live in the `app/Models` directory. All Eloquent models extend `Illuminate\Database\Eloquent\Model`.

#### Defining an Elqouent Model

```php
<?php

namespace MyPlugin\Models;

use Illuminate\Database\Eloquent\Model;

class User extends Model {
    protected $table = 'my_users';
}
```

## Using Models

Once a model is defined, you are ready to start retrieving and creating records in your table. Note that you will need to place `updated_at` and `created_at` columns on your table by default. If you do not wish to have these columns automatically maintained, set the `$timestamps` property on your model to `false`.

#### Retrieving All Records

```php
$users = User::all();
```

#### Retrieving A Record By Primary Key

```php
$user = User::find(1);

var_dump($user->name);
```

#### Querying Using Eloquent Models

```php
$users = User::where('votes', '>', 100)->take(10)->get();

foreach ($users as $user)
{
    var_dump($user->name);
}
```

#### Creating a New Record

```php
$user = User::create(['name' => 'John']);
```

#### Updating a Retrieved Model

To update a model, you may retrieve it, change an attribute, and use the `save` method:

```php
$user = User::find(1);
$user->email = 'john@foo.com';
$user->save();
```

## Relationships

#### Defining A One To One Relation

A one-to-one relationship is a very basic relation. For example, a `User` model might have one `Phone`. We can define this relation in Eloquent:

```php
class User extends Model {
    public function phone()
    {
        return $this->hasOne('App\Phone');
    }
}
```

The first argument passed to the `hasOne` method is the name of the related model. Once the relationship is defined, we may retrieve it using Eloquent's dynamic properties:

```php
$phone = User::find(1)->phone;
```

Note: this performs to lookups to the database.


## Further Reading

There are many other things you can do with Eloquent in the framework, such as defining more relationships, where clauses, etc. It's recommended you have a look at the [Eloquent Docs](https://laravel.com/docs/5.0/eloquent).