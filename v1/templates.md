# Templates

Templates are a relatively new addition to the Framework. All templates should be located in `resources/templates` within the plugin. 

Templates are designed to be used for the front-end view of the website and contain all of the logic you'd use to display them. They allow for the user to copy them to their own theme file under whatever child folder you specify in the `plugin.config.php`. For example, a template such as `resources/templates/view.php` would be copied to `theme/getbilly/view.php`.

The framework will prioritise the loading of the theme template rather than the resource template, making this useful to add custom styling and options.

## Usage

#### Specifying a Template

```php
<?php

namespace MyPlugin\Controllers;

use MyPlugin\Template;

class FrontController 
{
    public function view()
    {
        return Template::load('filename.php');
    }
}
```