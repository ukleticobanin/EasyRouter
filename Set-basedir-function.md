# Set basedir function

(EasyRouter >= 0.4.0)

```php
Teddy95\EasyRouter\route::set_basedir( string $base_directory )
```

```$base_directory``` = URL to the root-directory of your website.

### Little example:

```php
<?php
	Teddy95\EasyRouter\route::set_basedir("http://www.yourwebsite.com");
	Teddy95\EasyRouter\route::launch();
	
	/**
	 * instead of:
	 *
	 * $base_directory = "http://www.yourwebsite.com";
	 * Teddy95\EasyRouter\route::launch($base_directory);
	 */
?>
```
