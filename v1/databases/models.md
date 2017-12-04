# Models

In the Eloquent docs we explain how to create new Models. Since the framework is built ontop of WordPress it already includes some out of the box models that you can use in your workflow for each WordPress table.

These are

- `Billy\Framework\Models\Comment;`
- `Billy\Framework\Models\CommentMeta;`
- `Billy\Framework\Models\Option;`
- `Billy\Framework\Models\Post;`
- `Billy\Framework\Models\PostMeta;`
- `Billy\Framework\Models\Taxonomy;`
- `Billy\Framework\Models\Term;`

If you wish, these can be used throughout your plugin as such.

```php
<?php namespace MyPlugin\Controllers;

use Billy\Framework\Models\Post;

class PostController {

    /**
     * Show the post for the given id.
     */
    public function showPost($id)
    {
        $post = Post::find($id);

        return View::render('post/single.twig', [
	        'post' => $post
	    ]);
    }
}
```