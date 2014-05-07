(EasyRouter >= 0.5.1)

```php
Teddy95\EasyRouter\route::get_active_path([ bool $relative = false ] )
```

```$relative``` = Set true, to get the relative path.

### Return values

Returns the active path on success or FALSE on failure.

### Little example:

```php
<?php
	// Our script works in http://www.yourwebsite.com/website
	$active_path_absolute = Teddy95\EasyRouter\route::get_active_path();
	$active_path_relative = Teddy95\EasyRouter\route::get_active_path(true);
	echo $active_path_absolute;
	echo "<br />";
	echo $active_path_relative;
?>
```

```
http://www.yourwebsite.com/website/first-param/second-param will generate this:
$active_path_absolute = "http://www.yourwebsite.com/website/"
$active_path_relative = "../../"
```

***

(EasyRouter == 0.5.0)

```php
Teddy95\EasyRouter\route::get_active_path()
```

### Return values

Returns the active path on success or FALSE on failure.

### Little example:

```php
<?php
	// Our script works in http://www.yourwebsite.com/website
	$active_path = Teddy95\EasyRouter\route::get_active_path();
	echo $active_path;
?>
```

```
http://www.yourwebsite.com/website/first-param/second-param will generate this:
$active_path = "http://www.yourwebsite.com/website/"
```
