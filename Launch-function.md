# Launch function

(EasyRouter >= 0.4.0)

> You can use this function instead of the start or execute function!

```php
Teddy95\EasyRouter\route::launch([ string $base_directory = null [, array $parameters = null [, array $exceptions = null [, bool $load_GET = true ]]]] )
```

```$base_directory``` = URL to the root-directory of your website.

```$parameters``` = Names of parameters in the URI.

```$exceptions``` = Exceptions for parameters. If a value of a parameter not a value of an exception for this parameter, the parameter will be ignored.

```$load_GET``` = True -> Params will be loaded in the `$_GET` array.

### Return values

Returns an array with the uri-params on success or FALSE on failure.

### Little example with parameters and exceptions:

```php
<?php
	$base_directory = "http://www.yourwebsite.com";
	$parameters = array("language", "page");
	$exceptions = array();
	$exceptions[]= array(
		"param" => "language",
		"exceptions" => array("en", "de")
		);
	Teddy95\EasyRouter\route::launch($base_directory, $parameters, $exceptions);
?>
```

```
http://www.yourwebsite.com/en/user will generate this:
$_GET['language'] = 'en'
$_GET['page'] = 'user'

http://www.yourwebsite.com/user/en will generate this:
$_GET['page'] = 'user'
$_GET[1] = 'en'

http://www.yourwebsite.com/en will generate this:
$_GET['language'] = 'en'

http://www.yourwebsite.com/user will generate this:
$_GET['page'] = 'user'

http://www.yourwebsite.com/de/user?tab=contributions will generate this:
$_GET['language'] = 'de'
$_GET['page'] = 'user'
$_GET['tab'] = 'contributions'
```

### Little example with prepare pattern:

```php
<?php
	$base_directory = "http://www.yourwebsite.com";
	Teddy95\EasyRouter\route::prepare("{language}/{id}-{page}/{subpage}");
	Teddy95\EasyRouter\route::launch($base_directory);
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
