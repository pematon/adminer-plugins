Plugins for Adminer
===================

Usefull plugins for Adminer database tool (http://www.adminer.org/).

## Plugins

### AdminerJsonPreview

Displays JSON data preview as a table.

<img src="http://pematon.github.io/screenshots/json-table.png" width="400px" />

## How to use

1. [Download](http://www.adminer.org/#download) and install Adminer tool.

2. Download plugins you want and place them to plugins folder.

File structure will be:
```
- plugins
	- AdminerJsonPreview.php
	- ...
- adminer.php
```

3. Create index.php file and [configure plugins](www.adminer.org/plugins/#use).

```php
<?php

	function adminer_object()
	{
		// required to run any plugin
		include_once "./plugins/plugin.php";

		// autoloader
		foreach (glob("plugins/*.php") as $filename) {
			include_once "./$filename";
		}

		$plugins = array(
			// specify enabled plugins here
			new AdminerTheme(),
		);

		return new AdminerPlugin($plugins);
	}

	// include original Adminer or Adminer Editor
	include "./adminer.php";
```

Final file structure will be:
```
- plugins
	- AdminerJsonPreview.php
	- ...
	- plugin.php
- adminer.php
- index.php
```

## All-in-one
You can try our custom configuration in all-in-one bundle: [github.com/pematon/adminer-custom](https://github.com/pematon/adminer-custom)
