# Get true params function

(EasyRouter >= 0.3.0)

```php
Teddy95\EasyRouter\route::get_true_params()
```

### Return values

Returns an array with normal GET params.

### Little example with parameters and exceptions:

```php
<?php
	$true_get_params = Teddy95\EasyRouter\route::get_true_params();
?>
```

```
http://www.yourwebsite.com/param1/param2?id=5&name=John will generate this:
$true_get_params['id'] = '5'
$true_get_params['name'] = 'user'

http://www.yourwebsite.com/param1?id=5&name=John&page=followers will generate this:
$true_get_params['id'] = '5'
$true_get_params['name'] = 'user'
$true_get_params['page'] = 'followers'
```
