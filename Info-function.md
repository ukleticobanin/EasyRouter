# Info function

(EasyRouter >= 0.2.0)

```php
Teddy95\EasyRouter\route::info()
```

### Return values

Returns an array with information about EasyRouter.

### Little example:

```php
<?php
	$information = Teddy95\EasyRouter\route::info();
	print_r($information);
?>
```

```
Array
(
    [author] => Andre Sieverding
    [license] => MIT http://opensource.org/licenses/MIT
    [version] => 0.2
    [website] => http://www.andre-sieverding.de
    [github] => https://github.com/Teddy95
    [src] => https://github.com/Teddy95/EasyRouter
)
```