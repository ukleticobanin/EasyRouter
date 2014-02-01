# Start function

(EasyRouter >= 0.2.0)

```php
Teddy95\EasyRouter\route::start([ string $base_directory = null [, array $parameters = null [, array $exceptions = null [, bool $load_GET = true ]]]] )
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
	Teddy95\EasyRouter\route::start($base_directory, $parameters, $exceptions);
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

-------------

> Version 0.1 also supports this function, view [README.md v0.1](https://github.com/Teddy95/EasyRouter/blob/v0.1/README.md)
> 
> ### Version 0.1 fix
> 
> Please update to version 0.2.1 if you have not already done so!  
> You can use our [`fix_route.php`](https://gist.github.com/Teddy95/548c8c3e3c9cd4346841) file, so you needn't rewrite your code.
> 
> If you **don't want to update**, there is still an interesting link:
> - [Version 0.1](https://github.com/Teddy95/EasyRouter/tree/v0.1)

-------------
