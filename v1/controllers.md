# Controllers

Controllers are often used to group related request handling logic into a class. Controllers are stored within the `app/Controllers` folder.

## Basic Controller

Below is an example of a basic controller setup within Billy.

```php
<?php 

namespace MyPlugin\Controllers;

use MyPlugin\User;

class UserController
{
	public function index() 
	{
		return User::find(1);
	}
}
```