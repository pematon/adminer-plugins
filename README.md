Plugins for Adminer
===================

Usefull plugins for Adminer database tool (http://www.adminer.org/).

- [AdminerJsonPreview](https://github.com/pematon/adminer-plugins#adminerjsonpreview)
- [AdminerSimpleMenu](https://github.com/pematon/adminer-plugins#adminersimplemenu)
- [How to use](https://github.com/pematon/adminer-plugins#how-to-use)

You can also try our [**touch-friendly theme**](https://github.com/pematon/adminer-theme) or our custom Adminer configuration in [**all-in-one bundle**](https://github.com/pematon/adminer-custom).

## AdminerJsonPreview

Displays JSON data as a table.

<img src="http://pematon.github.io/screenshots/json-preview.png" width="728px" />

## AdminerSimpleMenu

Displays only one prefered action in table list.
Get rid of schizophrenic decisions between selecting data and showing table structure. Optimize your workflow!

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

3. Create index.php file and [configure plugins](http://www.adminer.org/plugins/#use).

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
