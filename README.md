Yii 2 [IcoFont](http://icofont.com) Asset Bundle
==============================
This extension provides a assets bundle with IcoFont for Yii framework 2.0 applications and helper to use icons.

Installation
------------

The preferred way to install this extension is through [composer](https://getcomposer.org/).

Either run

```bash
composer require "lo/yii2-icofont:*"
```

or add

```
"lo/yii2-icofont": "*",
```

to the `require` section of your `composer.json` file.

Usage
-----

In view

```php
lo\icofont\IcoFontAsset::register($this);

```

or as dependency in your main application asset bundle

```php
class AppAsset extends AssetBundle
{
	// ...

	public $depends = [
		// ...
		'lo\icofont\IcoFontAsset'
	];
}

```

## Helper examples

```php
use lo\icofont\IH; // IH = IcoHelper

// normal use
echo IH::icon('home'); // <i class="icofont icofont-home"></i>

// shortcut
echo IH::i('home'); // <i class="icofont icofont-home"></i>

// icon with additional attributes
echo FA::icon(
    'arrow-left', 
    ['class' => 'big', 'data-role' => 'arrow']
); // <i class="big icofont icofont-arrow-left" data-role="arrow"></i>

// icon in button
echo Html::submitButton(
    Yii::t('app', '{icon} Save', ['icon' => FA::icon('check')])
); // <button type="submit"><i class="icofont icofont-check"></i> Save</button>

// icon with additional methods
echo FA::icon('arrow-right')->pullLeft();   // <i class="icofont icofont-arrow-right pull-left"></i>
echo FA::icon('arrow-right')->pullRight();  // <i class="icofont icofont-arrow-right pull-right"></i>

// autocomplete icons name in IDE
echo IH::icon(FA::_MAGIC);
echo IH::icon(FA::_ARROW_RIGHT);
```

## License

**loveorigami/yii2-icofont** is released under the MIT License. See the bundled `LICENSE.md` for details.