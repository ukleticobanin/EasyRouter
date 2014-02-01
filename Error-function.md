# Error function

(EasyRouter >= 0.3.0)

```php
Teddy95\EasyRouter\route::error( string $href [, int $params = null ] )
```

```$href``` = URI to an error document. (404, 500, etc.)

```$params``` = Number of allowed parameters in the URI.

### Return values

Returns FALSE on failure.

### Little example with prepare and execute:

```php
<?php
	Teddy95\EasyRouter\route::prepare("{language}/{id}-{page}/{subpage}");
	Teddy95\EasyRouter\route::execute();
	Teddy95\EasyRouter\route::error("http://www.yourwebsite.com/404.html");
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

http://www.yourwebsite.com/en/21-customers/new/param1/param2 will ridirect you to your error document.
```

### Another little example with prepare and execute:

```php
<?php
	Teddy95\EasyRouter\route::prepare("{language}/{id}-{page}/{subpage}");
	Teddy95\EasyRouter\route::execute();
	Teddy95\EasyRouter\route::error("http://www.yourwebsite.com/404.html", 2);
?>
```

```
http://www.yourwebsite.com/en/21-customers will generate this:
$_GET['language'] = 'en'
$_GET['id'] = '21'
$_GET['page'] = 'customers'

http://www.yourwebsite.com/de will generate this:
$_GET['language'] = 'de'

http://www.yourwebsite.com/en/21-customers/new will ridirect you to your error document.
```
