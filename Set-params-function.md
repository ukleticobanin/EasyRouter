# Set params function

(EasyRouter >= 0.4.0)

```php
Teddy95\EasyRouter\route::set_basedir( string $parameters )
```

```$parameters``` = Names of parameters in the URI.

### Little example:

```php
<?php
	Teddy95\EasyRouter\route::set_params(array('page', 'subpage'));
	Teddy95\EasyRouter\route::launch();
	
	/**
	 * instead of:
	 *
	 * $parameters = array('page', 'subpage');
	 * Teddy95\EasyRouter\route::launch(null, $parameters);
	 */
?>
```
