# Set exceptions function

(EasyRouter >= 0.4.0)

```php
Teddy95\EasyRouter\route::set_exceptions( string $exceptions )
```

```$exceptions``` = Exceptions for parameters. If a value of a parameter not a value of an exception for this parameter, the parameter will be ignored.

### Little example:

```php
<?php
	Teddy95\EasyRouter\route::set_exceptions(array(array("param" => "language", "exceptions" => array("en", "de"))));
	Teddy95\EasyRouter\route::launch();
	
	/**
	 * instead of:
	 *
	 * $exceptions = array(array("param" => "language", "exceptions" => array("en", "de")));
	 * Teddy95\EasyRouter\route::launch(null, null, $exceptions);
	 */
?>
```
