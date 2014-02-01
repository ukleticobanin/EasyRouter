# Execute function

(EasyRouter >= 0.3.0)

```php
Teddy95\EasyRouter\route::execute([ string $base_directory = null [, bool $load_GET = true ]] )
```

```$base_directory``` = URL to the root-directory of your website.

```$load_GET``` = True -> Params will be loaded in the `$_GET` array.

### Return values

Returns an array with the uri-params on success or FALSE on failure.

### Little example with prepare pattern:

```php
<?php
	$base_directory = "http://www.yourwebsite.com";
	Teddy95\EasyRouter\route::prepare("{language}/{id}-{page}/{subpage}"); // before you execute the routing system, you have to prepare the route pattern
	Teddy95\EasyRouter\route::execute($base_directory);
?>
```

```
http://www.yourwebsite.com/en/21-customers/new will generate this:
$_GET['language'] = 'en'
$_GET['id'] = '21'
$_GET['page'] = 'customers'
$_GET['subpage'] = 'new'

http://www.yourwebsite.com/de/21-customers will generate this:
$_GET['language'] = 'de'
$_GET['id'] = '21'
$_GET['page'] = 'customers'

http://www.yourwebsite.com/en/21-customers/new/param1/param2 will generate this:
$_GET['language'] = 'en'
$_GET['id'] = '21'
$_GET['page'] = 'customers'
$_GET['subpage'] = 'new'
$_GET[4] = 'param1'
$_GET[5] = 'param2'
```
