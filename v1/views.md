# Views

Views are used to render PHP and Content to the browser, they are used to abstract the templace and html away from Controllers and keep things in a clean, logical order.

The framework uses __Twig__ as a templating engine. All views created utilise this, and it's recommended for the administration and non-changeable front end elements. This is to abstract PHP and functionality from the view and keep it contained to the controller.

To learn more, it is recommend having a look through the [Twig Documentation](http://twig.sensiolabs.org/documentation) to understand the capabilities.

## Creating a View

Views are stored in the `resources/views` directory. You can update this location if you wish by editing the `plugin.config.php`, however, it is recommended you do not.

Below is an example of a twig file.

```html
<div class="wrap">
  <ul id="navigation">
  {% for item in navigation %}
    <li>
	  <a href=""></a>
	</li>
  {% endfor %}
  </ul>

  {{ content }}
</div>
```

This view requires to data sources, navigation and content to render the page properly.

## Passing Data 

To make data accessible in a view, we need to pass it when we call it. In our controller we’d do something like the following.

```php
<?php 
namsepace MyPlugin\Controllers;

use Billy\Framework\View as View;

class AdminController
{
	public function renderPage()
	{
		$navigation = [
			[
				'caption' => 'Home',
				'href'    => '/'
			],[
				'caption' => 'About',
				'href'    => '/about'
			]
		];
		
		$content = 'Hello World';
		
		return View::render('example.twig', [
			'navigation' => $navigation,
			'content'    => $content
		]);
	}
}
```