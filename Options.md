# Options

The option parameter is inside the exception parameter and transform the active $\_GET[$i] to lowercase, uppercase or something else before it will parsed.

### Little example:

```php
<?php
	$basedir = "http://www.yourwebsite.com";
	$params = array("page", "subpage");
	$exceptions = array();
	$exceptions[] = array(
		"param" => "page",
		"exceptions" => array("contributions", "hellostats", "commits"),
		"options" => array(
			"strtolower" => true,
			"additionBefore" => "hello"
		)
	);
	Teddy95\EasyRouter\route::start($basedir, $params, $exceptions);
?>
```

```
http://www.yourwebsite.com/StAtS/test
will generate:
$_GET["page"] = "hellostats"
$_GET["subpage"] = "test"
```

### The options are:

strtolower (bool)  
strtoupper (bool)  
strtotime (bool)  
strtoint (bool)  
inttobinary (bool)  
addition (string)  
additionBefore (string)  
replace (array) [includes: "search" => string, "replace" => string, "ireplace" => bool]  
pregreplace (array) [includes: "pattern" => string, "replace" => string]  

```php
<?php
	$exceptions[] = array(
		"param" => "param",
		"exceptions" => array("exception1", "exception2"),
		"options" => array(
			"strtolower" => false, // default set false
			"strtoupper" => false,
			"strtotime" => false,
			"strtoint" => false,
			"inttobinary" => false,
			"addition" => null, // default set null
			"additionBefore" => null,
			"replace" => array(
				"search" => null,
				"replace" => null,
				"ireplace" => false
				),
			"pregreplace" => array(
				"pattern" => null,
				"replace" => null
				)
		)
	);
?>
```
