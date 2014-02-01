# Installation

> Alternatively you can use our [start_route.php](https://gist.github.com/Teddy95/c931ca04a7db73716042) file!

Move .htaccess from src into the root directory of your website. After that you have to move the EasyRouter.php from src into one directory of your website.

**Important:** The [`.htaccess`](https://github.com/Teddy95/EasyRouter/blob/master/src/.htaccess) file redirects to the `index.php` file, so the code should be written into the `index.php` file! - _Alternatively you can rewrite the [`.htaccess`](https://github.com/Teddy95/EasyRouter/blob/master/src/.htaccess) file!_

Now you must include EasyRouter into your website:

```php
<?php
	include_once('path/to/EasyRouter/EasyRouter.php');
?>
```
