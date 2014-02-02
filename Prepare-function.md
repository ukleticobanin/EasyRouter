# Prepare function

(EasyRouter >= 0.3.0)

```php
Teddy95\EasyRouter\route::prepare( string $prepare_string )
```

```$prepare_string``` = Prepare pattern for the execute function.

### Return values

Returns FALSE on failure.

### Little example with execution:

```php
<?php
	$base_directory = "http://www.yourwebsite.com";
	Teddy95\EasyRouter\route::prepare("{language}/{id}-{page}/{subpage}");
	Teddy95\EasyRouter\route::execute($base_directory); // you must execute the prepare pattern
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
