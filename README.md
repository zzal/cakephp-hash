cakephp-hash
============

**Please note that this package is in alpha develpment phase.**


This package (intended for Laravel 4) gives you the ability to use the great cakePHP’s Hash class into your Laravel 4 projects.

[See cakePHP documentation.](http://book.cakephp.org/2.0/en/core-utility-libraries/hash.html)

## Installation

Install this package through Composer. To do so, edit your project's `composer.json` file to require `zzal/cakephp-hash`.

    "require": {
		"zzal/cakephp-hash": "*"
	}
	
Then, add this inside the "autoload" section of this file:

	"autoload": {
		"classmap": [
			…
		],
        "psr-0": {
        	"CakePHP\\Utility\\": "vendor/zzal/cakephp-hash/Hash"
        }


Finally, use Composer from the Terminal:

    composer install

Basic Usage
===========
As Laravel 4 already have a class named Hash, I suggest that you use the cakePHP Hash class with an alias, like in the following example (routes.php):

```php
use CakePHP\Utility\Hash as ArrayXPath;

Route::get('/', function()
{
	$records = array(
		array(
		    'pages' => array(
		    	array('id' => 1, 'title' => 'One'),
		    	array('id' => 2, 'title' => 'Two'),
		    	array('id' => 3, 'title' => 'Three'),
			)
		)
	);
	
	$result = ArrayXPath::extract($records, '{n}.pages.{n}[id=2]');

	var_dump($result);
});
```

And the result would be:

```php
array(1) {
  [0]=>
  array(2) {
    ["id"]=>
    int(2)
    ["title"]=>
    string(3) "Two"
  }
}
```